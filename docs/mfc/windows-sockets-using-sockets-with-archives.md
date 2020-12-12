---
description: 'Dowiedz się więcej na temat: Windows Sockets: używanie gniazd z archiwami'
title: 'Windows Sockets: używanie gniazd z archiwami'
ms.date: 11/04/2016
helpviewer_keywords:
- Windows Sockets [MFC], archives
- sockets [MFC], with archives
- archives [MFC], and Windows Sockets
- CSocket class [MFC], programming model
ms.assetid: 17e71a99-a09e-4e1a-9fda-13d62805c824
ms.openlocfilehash: bd5f239a0fdcee4bf6c6141994c4ca5002bdc6b9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331341"
---
# <a name="windows-sockets-using-sockets-with-archives"></a>Windows Sockets: używanie gniazd z archiwami

W tym artykule opisano [model programowania CSocket](#_core_the_csocket_programming_model). Klasy [CSocket](../mfc/reference/csocket-class.md) udostępniają wsparcie dla gniazda na wyższym poziomie abstrakcji niż w klasie [CAsyncSocket](../mfc/reference/casyncsocket-class.md). `CSocket` używa wersji protokołu serializacji MFC do przekazywania danych do i z obiektu gniazda za pośrednictwem obiektu MFC [CArchive](../mfc/reference/carchive-class.md) . `CSocket` zapewnia blokowanie (podczas zarządzania przetwarzaniem komunikatów systemu Windows w tle) i zapewnia dostęp do programu `CArchive` , który zarządza wieloma aspektami komunikacji, które trzeba wykonać samodzielnie przy użyciu raw API lub klasy `CAsyncSocket` .

> [!TIP]
> Możesz użyć samej klasy `CSocket` , jako bardziej wygodnej wersji `CAsyncSocket` , ale najprostszy model programowania jest używany `CSocket` z `CArchive` obiektem.

Aby uzyskać więcej informacji na temat sposobu działania implementacji gniazd z archiwami, zobacz [Windows Sockets: jak działają gniazda z archiwami](../mfc/windows-sockets-how-sockets-with-archives-work.md). Na przykład kod można znaleźć w temacie [Windows Sockets: Sekwencja operacji](../mfc/windows-sockets-sequence-of-operations.md) i [Windows Sockets: przykład gniazd korzystających z archiwów](../mfc/windows-sockets-example-of-sockets-using-archives.md). Aby uzyskać informacje o niektórych funkcjach, które można uzyskać przez wyjęcie własnych klas z klas Sockets, zobacz [Windows Sockets: pochodne z klas gniazd](../mfc/windows-sockets-deriving-from-socket-classes.md).

> [!NOTE]
> W przypadku pisania programu klienckiego MFC w celu komunikowania się z ustalonymi serwerami (bez MFC) nie należy wysyłać obiektów C++ za pomocą archiwum. Chyba że serwer jest aplikacją MFC, która zrozumie rodzaje obiektów, które chcesz wysłać, nie będzie można odbierać i deserializować obiektów. W przypadku pokrewnego materiału z tematu komunikowania się z aplikacjami nienależącymi do MFC Zobacz również artykuł [Windows Sockets: porządkowanie bajtów](../mfc/windows-sockets-byte-ordering.md).

## <a name="the-csocket-programming-model"></a><a name="_core_the_csocket_programming_model"></a> Model programowania CSocket

Użycie `CSocket` obiektu obejmuje tworzenie i kojarzenie razem kilku obiektów klas MFC. W ogólnej procedurze poniżej każdy krok jest podejmowany zarówno przez gniazdo serwera, jak i gniazdo klienta, z wyjątkiem kroku 3, w którym każdy typ gniazda wymaga innej akcji.

> [!TIP]
> W czasie wykonywania aplikacja serwera zwykle zaczyna być gotowa i "nasłuchuje", gdy aplikacja kliencka wyszukuje połączenie. Jeśli serwer nie jest gotowy, gdy klient próbuje nawiązać połączenie, zazwyczaj aplikacja użytkownika wymaga ponownego nawiązania połączenia później.

#### <a name="to-set-up-communication-between-a-server-socket-and-a-client-socket"></a>Aby skonfigurować komunikację między gniazdem serwera i gniazdem klienta

1. Utwórz obiekt [CSocket](../mfc/reference/csocket-class.md) .

1. Użyj obiektu, aby utworzyć podstawowy uchwyt **gniazda** .

   W przypadku `CSocket` obiektu klienta zazwyczaj należy używać domyślnych parametrów do [utworzenia](../mfc/reference/casyncsocket-class.md#create), chyba że potrzebujesz gniazda datagramu. Dla `CSocket` obiektu serwera należy określić port w `Create` wywołaniu.

    > [!NOTE]
    >  `CArchive` Program nie współpracuje z gniazdami datagramów. Jeśli chcesz użyć `CSocket` dla gniazda datagramu, musisz użyć klasy, `CAsyncSocket` która ma być używana, czyli bez archiwum. Ze względu na to, że datagramy są niezawodne (niegwarantowane i mogą być powtórzone lub z sekwencji), nie są zgodne z serializacji za pomocą archiwum. Oczekuje się, że operacja serializacji zostanie wykonana niezawodnie i w kolejności. Jeśli spróbujesz użyć `CSocket` z `CArchive` obiektem dla datagramu, potwierdzenie MFC zakończy się niepowodzeniem.

1. Jeśli gniazdo jest klientem, wywołaj [CAsyncSocket:: Connect](../mfc/reference/casyncsocket-class.md#connect) , aby połączyć obiekt Socket z gniazdem serwera.

     -lub-

   Jeśli gniazdo jest serwerem, wywołaj [CAsyncSocket:: Listen](../mfc/reference/casyncsocket-class.md#listen) , aby rozpocząć nasłuchiwanie prób połączenia od klienta. Po odebraniu żądania połączenia zaakceptuj je przez wywołanie [CAsyncSocket:: Accept](../mfc/reference/casyncsocket-class.md#accept).

    > [!NOTE]
    >  `Accept`Funkcja członkowska przyjmuje odwołanie do nowego, pustego `CSocket` obiektu jako jego parametru. Należy skonstruować ten obiekt przed wywołaniem `Accept` . Jeśli ten obiekt gniazda wykracza poza zakres, połączenie zostanie zamknięte. Nie wywołuj `Create` dla tego nowego obiektu gniazda.

1. Utwórz obiekt [CSocketFile](../mfc/reference/csocketfile-class.md) , kojarząc `CSocket` z nim obiekt.

1. Utwórz obiekt [CArchive](../mfc/reference/carchive-class.md) do ładowania (otrzymywania) lub zapisywania (wysyłania) danych. Archiwum jest skojarzone z `CSocketFile` obiektem.

   Należy pamiętać, że program nie `CArchive` współpracuje z gniazdami datagramów.

1. Użyj `CArchive` obiektu, aby przekazać dane między gniazdem klienta i serwera.

   Należy pamiętać, że dany `CArchive` obiekt przenosi dane tylko w jednym kierunku: w przypadku ładowania (otrzymywania) lub przechowywania (wysyłania). W niektórych przypadkach zostaną użyte dwa `CArchive` obiekty: jeden do wysyłania danych, drugi do otrzymywania potwierdzeń.

   Po zaakceptowaniu połączenia i skonfigurowaniu archiwum można wykonać takie zadania jak Walidacja haseł.

1. Zniszcz obiekty archiwalne, Socket i Sockets.

    > [!NOTE]
    >  Klasa `CArchive` dostarcza `IsBufferEmpty` funkcję elementu członkowskiego, która jest przeznaczona do użycia z klasą `CSocket` . Jeśli bufor zawiera wiele komunikatów danych, na przykład należy wykonać pętlę do momentu, aż wszystkie z nich zostaną odczytane i bufor zostanie wyczyszczony. W przeciwnym razie Twoje następne powiadomienie o otrzymaniu danych może być nieczasowo opóźnione. Użyj `IsBufferEmpty` , aby upewnić się, że pobierasz wszystkie dane.

Artykuł [Windows Sockets: Sekwencja operacji](../mfc/windows-sockets-sequence-of-operations.md) ilustruje obie strony tego procesu za pomocą przykładowego kodu.

Aby uzyskać więcej informacji, zobacz:

- [Windows Sockets: gniazda strumienia](../mfc/windows-sockets-stream-sockets.md)

- [Windows Sockets: gniazda datagramów](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>Zobacz też

[Windows Sockets w MFC](../mfc/windows-sockets-in-mfc.md)<br/>
[CSocket:: Create](../mfc/reference/csocket-class.md#create)
