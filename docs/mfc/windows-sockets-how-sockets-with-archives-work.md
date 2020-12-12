---
description: 'Dowiedz się więcej o programie: Windows Sockets: jak działają gniazda z archiwami'
title: 'Windows Sockets: jak działają gniazda z archiwami'
ms.date: 11/19/2018
helpviewer_keywords:
- Windows Sockets [MFC], synchronous
- sockets [MFC], synchronous operation
- sockets [MFC], with archives
- synchronous state socket
- Windows Sockets [MFC], with archives
- two-state socket object
ms.assetid: d8ae4039-391d-44f0-a19b-558817affcbb
ms.openlocfilehash: 19b24a9942b7405304c9037091266b4535bffbc3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263546"
---
# <a name="windows-sockets-how-sockets-with-archives-work"></a>Windows Sockets: jak działają gniazda z archiwami

W tym artykule wyjaśniono, jak obiekt [CSocket](../mfc/reference/csocket-class.md) , obiekt [CSocketFile](../mfc/reference/csocketfile-class.md) i obiekt [CArchive](../mfc/reference/carchive-class.md) są łączone w celu uproszczenia wysyłania i otrzymywania danych za pomocą gniazda systemu Windows.

Artykuł [Windows Sockets: przykład gniazd korzystających z archiwów](../mfc/windows-sockets-example-of-sockets-using-archives.md) prezentuje `PacketSerialize` funkcję. Obiekt archiwum w `PacketSerialize` przykładzie działa podobnie jak obiekt archiwum przekazaną do funkcji [serializacji](../mfc/reference/cobject-class.md#serialize) MFC. Istotną różnicą jest to, że w przypadku gniazd, archiwum jest dołączane do standardowego obiektu [CFile](../mfc/reference/cfile-class.md) (zwykle skojarzonego z plikiem dysku), ale do `CSocketFile` obiektu. Zamiast nawiązywać połączenia z plikiem dysku, `CSocketFile` obiekt nawiązuje połączenie z `CSocket` obiektem.

`CArchive`Obiekt zarządza buforem. Gdy bufor przechowujący archiwum (wysyłanie) jest zapełniony, skojarzony `CFile` obiekt zapisuje zawartość bufora. Opróżnianie buforu archiwum dołączonego do gniazda jest równoznaczne z wysłaniem komunikatu. Gdy bufor ładowania (otrzymywanie) jest zapełniony, `CFile` obiekt przestaje czytać do momentu, gdy bufor będzie dostępny ponownie.

Klasa `CSocketFile` pochodzi z `CFile` , ale nie obsługuje funkcji składowych [CFile](../mfc/reference/cfile-class.md) , takich jak funkcje pozycjonowania ( `Seek` , `GetLength` , `SetLength` , itd.), funkcje blokowania ( `LockRange` , `UnlockRange` ) lub `GetPosition` funkcji. Wszystkie obiekty [CSocketFile](../mfc/reference/csocketfile-class.md) muszą mieć sekwencję zapisu lub odczytu bajtów do lub z skojarzonego `CSocket` obiektu. Ponieważ plik nie jest uwzględniony, operacje takie jak `Seek` i `GetPosition` nie mają sensu. `CSocketFile` jest pochodną `CFile` , więc zwykle dziedziczy wszystkie te funkcje elementów członkowskich. Aby tego uniknąć, nieobsługiwane `CFile` funkcje członkowskie są zastępowane w programie w `CSocketFile` celu wygenerowania [CNotSupportedException](../mfc/reference/cnotsupportedexception-class.md).

`CSocketFile`Obiekt wywołuje funkcje elementów członkowskich obiektu, `CSocket` Aby wysyłać lub odbierać dane.

Na poniższej ilustracji przedstawiono relacje między tymi obiektami po obu stronach komunikacji.

![CArchive, CSocketFile i CSocket](../mfc/media/vc38ia1.gif "CArchive, CSocketFile i CSocket") <br/>
CArchive, CSocketFile i CSocket

Celem tej pozornej złożoności jest przełączenie Cię z konieczności zarządzania szczegółami gniazda. Utworzysz gniazdo, plik i archiwum, a następnie zaczniesz wysyłać lub odbierać dane, wstawiając je do archiwum lub wyodrębniając je z archiwum. [CArchive](../mfc/reference/carchive-class.md), [CSocketFile](../mfc/reference/csocketfile-class.md)i [CSocket](../mfc/reference/csocket-class.md) zarządzają szczegółami w tle.

`CSocket`Obiekt jest w rzeczywistości obiektem dwustanowym: czasami asynchroniczny (zwykły stan) i czasami synchronicznie. W stanie asynchronicznym gniazdo może odbierać asynchroniczne powiadomienia z platformy. Jednak podczas operacji, takiej jak otrzymywanie lub wysyłanie danych, gniazdo zostanie synchroniczne. Oznacza to, że gniazdo nie będzie otrzymywać powiadomień asynchronicznych, dopóki operacja synchroniczna nie zostanie ukończona. Ponieważ przełącza on tryby, można na przykład wykonać następujące czynności:

[!code-cpp[NVC_MFCSimpleSocket#2](../mfc/codesnippet/cpp/windows-sockets-how-sockets-with-archives-work_1.cpp)]

Jeśli `CSocket` nie zostały zaimplementowane jako obiekt dwustanowy, może być możliwe otrzymywanie dodatkowych powiadomień dotyczących tego samego rodzaju zdarzenia podczas przetwarzania poprzedniego powiadomienia. Na przykład użytkownik może otrzymać `OnReceive` powiadomienie podczas przetwarzania `OnReceive` . W powyższym fragmencie kodu wyodrębnianie `str` z archiwum może prowadzić do rekursji. Przełączanie Stanów `CSocket` uniemożliwia rekursję, uniemożliwiając dodatkowe powiadomienia. Ogólna reguła nie dotyczy powiadomień w ramach powiadomień.

> [!NOTE]
> `CSocketFile`Można również użyć jako pliku (z ograniczeniami) bez `CArchive` obiektu. Domyślnie `CSocketFile` parametr *bArchiveCompatible* konstruktora ma **wartość true**. Określa, że obiekt pliku jest używany z archiwum. Aby użyć obiektu pliku bez archiwum, w parametrze *bArchiveCompatible* należy przekazać **wartość false** .

W trybie "zgodne z archiwum" `CSocketFile` obiekt zapewnia lepszą wydajność i zmniejsza zagrożenie "zakleszczenie". Zakleszczenie występuje, gdy zarówno gniazdo wysyłające, jak i przejmujące czekają na siebie lub oczekują na wspólny zasób. Taka sytuacja może wystąpić, jeśli `CArchive` obiekt działał w sposób, w `CSocketFile` jaki działa, z `CFile` obiektem. W programie `CFile` archiwum może założyć, że jeśli odbierze mniejszą liczbę bajtów niż zażądano, osiągnięto koniec pliku. `CSocketFile`Dane są jednak oparte na komunikatach; bufor może zawierać wiele komunikatów, więc otrzymanie mniejszej liczby bajtów nie oznacza końca pliku. Aplikacja nie jest blokowana w tym przypadku, ponieważ może w tym przypadku `CFile` , i może kontynuować odczytywanie komunikatów z bufora do momentu, gdy bufor jest pusty. Funkcja [IsBufferEmpty](../mfc/reference/carchive-class.md#isbufferempty) w `CArchive` jest przydatna do monitorowania stanu buforu Archiwum w takich przypadkach.

Aby uzyskać więcej informacji, zobacz [Windows Sockets: używanie gniazd z archiwami](../mfc/windows-sockets-using-sockets-with-archives.md)

## <a name="see-also"></a>Zobacz też

[Windows Sockets w MFC](../mfc/windows-sockets-in-mfc.md)<br/>
[CObject:: serializować](../mfc/reference/cobject-class.md#serialize)
