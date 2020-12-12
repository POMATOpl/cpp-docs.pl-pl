---
description: 'Dowiedz się więcej na temat: Klasa CSocketFile'
title: Klasa CSocketFile
ms.date: 11/04/2016
f1_keywords:
- CSocketFile
- AFXSOCK/CSocketFile
- AFXSOCK/CSocketFile::CSocketFile
helpviewer_keywords:
- CSocketFile [MFC], CSocketFile
ms.assetid: 7924c098-5f72-40d6-989d-42800a47958f
ms.openlocfilehash: 4ca484545e11502a11acf5f27b00ee2df49fc9d6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318653"
---
# <a name="csocketfile-class"></a>Klasa CSocketFile

`CFile`Obiekt służący do wysyłania i otrzymywania danych przez sieć za pośrednictwem usługi Windows Sockets.

## <a name="syntax"></a>Składnia

```
class CSocketFile : public CFile
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CSocketFile::CSocketFile](#csocketfile)|Konstruuje `CSocketFile` obiekt.|

## <a name="remarks"></a>Uwagi

W `CSocketFile` tym celu można dołączyć obiekt do `CSocket` obiektu. Można również, i zwykle, dołączyć `CSocketFile` obiekt do `CArchive` obiektu, aby uprościć wysyłanie i otrzymywanie danych przy użyciu serializacji MFC.

Aby serializować (wysłać) dane, należy wstawić je do archiwum, które wywołuje `CSocketFile` funkcje członkowskie do zapisu danych do `CSocket` obiektu. Aby deserializować (odebrać) dane, Wyodrębnij z archiwum. Powoduje to, że archiwum wywołuje `CSocketFile` funkcje członkowskie, aby odczytywać dane z `CSocket` obiektu.

> [!TIP]
> Oprócz użycia `CSocketFile` zgodnie z opisem w tym miejscu można użyć go jako autonomicznego obiektu pliku, tak jak w przypadku `CFile` , jego klasy bazowej. Można go również używać `CSocketFile` z wszystkimi funkcjami serializacji MFC opartymi na archiwum. Ponieważ `CSocketFile` program nie obsługuje wszystkich `CFile` funkcji, niektóre domyślne funkcje serializacji MFC nie są zgodne z programem `CSocketFile` . Jest to szczególnie prawdziwe w `CEditView` klasie. Nie należy próbować serializować `CEditView` danych za pośrednictwem `CArchive` obiektu dołączonego do `CSocketFile` obiektu za pomocą `CEditView::SerializeRaw` ; `CEditView::Serialize` zamiast tego należy użyć. `SerializeRaw`Funkcja oczekuje, że obiekt pliku ma funkcje, takie jak `Seek` , które `CSocketFile` nie ma.

W przypadku korzystania `CArchive` z programu z programem `CSocketFile` i `CSocket` można napotkać sytuację, w której `CSocket::Receive` wprowadzana jest pętla (przez `PumpMessages(FD_READ)` ), czekając na żądaną ilość bajtów. Wynika to z faktu, że usługa Windows Sockets zezwala tylko na jedno wywołanie odbierania na FD_READ powiadomienia, ale `CSocketFile` i `CSocket` zezwala na wiele wywołań odbierania na FD_READ. Jeśli otrzymasz FD_READ, gdy nie ma danych do odczytania, aplikacja zawiesza się. Jeśli nie otrzymasz kolejnej FD_READ, aplikacja przestanie komunikować się za pośrednictwem gniazda.

Ten problem można rozwiązać w następujący sposób. W `OnReceive` metodzie klasy Socket Wywołaj `CAsyncSocket::IOCtl(FIONREAD, ...)` przed wywołaniem `Serialize` metody klasy wiadomości, gdy oczekiwane dane, które mają zostać odczytane z gniazda, przekraczają rozmiar jednego pakietu TCP (maksymalna jednostka transmisji nośnika sieciowego, zwykle co najmniej 1096 bajtów). Jeśli rozmiar dostępnych danych jest mniejszy niż jest to konieczne, poczekaj na odebranie wszystkich danych, a następnie uruchom operację odczytu.

W poniższym przykładzie `m_dwExpected` jest przybliżona liczba bajtów, które użytkownik oczekuje na otrzymanie. Przyjęto założenie, że deklarujesz go w innym miejscu w kodzie.

[!code-cpp[NVC_MFCSocketThread#4](../../mfc/reference/codesnippet/cpp/csocketfile-class_1.cpp)]

Aby uzyskać więcej informacji, zobacz [Windows Sockets w MFC](../../mfc/windows-sockets-in-mfc.md), [Windows Sockets: używanie gniazd z archiwami](../../mfc/windows-sockets-using-sockets-with-archives.md), a także [interfejsu API Windows Sockets 2](/windows/win32/WinSock/windows-sockets-start-page-2).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

`CSocketFile`

## <a name="requirements"></a>Wymagania

**Nagłówek:** AfxSock. h

## <a name="csocketfilecsocketfile"></a><a name="csocketfile"></a> CSocketFile::CSocketFile

Konstruuje `CSocketFile` obiekt.

```
explicit CSocketFile(
    CSocket* pSocket,
    BOOL bArchiveCompatible = TRUE);
```

### <a name="parameters"></a>Parametry

*pSocket*<br/>
Gniazdo do dołączenia do `CSocketFile` obiektu.

*bArchiveCompatible*<br/>
Określa, czy obiekt pliku jest używany z `CArchive` obiektem. Należy przekazać wartość FALSE tylko wtedy, gdy obiekt ma być używany `CSocketFile` w sposób autonomiczny, jak w przypadku obiektu autonomicznego `CFile` z pewnymi ograniczeniami. Ta flaga zmienia sposób, w jaki `CArchive` obiekt dołączony do `CSocketFile` obiektu zarządza jego buforem do odczytu.

### <a name="remarks"></a>Uwagi

Destruktor obiektu odkojarzy się z obiektem gniazda, gdy obiekt wykracza poza zakres lub został usunięty.

> [!NOTE]
> `CSocketFile`Można również użyć jako pliku (z ograniczeniami) bez `CArchive` obiektu. Domyślnie `CSocketFile` parametr *bArchiveCompatible* konstruktora ma wartość true. Określa, że obiekt pliku jest używany z archiwum. Aby użyć obiektu pliku bez archiwum, w parametrze *bArchiveCompatible* należy przekazać wartość false.

W trybie "zgodne z archiwum" `CSocketFile` obiekt zapewnia lepszą wydajność i zmniejsza zagrożenie "zakleszczenie". Zakleszczenie występuje, gdy zarówno gniazdo wysyłające, jak i przejmujące czekają na siebie lub dla typowego zasobu. Taka sytuacja może wystąpić, jeśli `CArchive` obiekt działał w sposób, w `CSocketFile` jaki działa, z `CFile` obiektem. W programie `CFile` archiwum może założyć, że jeśli odbierze mniejszą liczbę bajtów niż zażądano, osiągnięto koniec pliku.

`CSocketFile`Dane są jednak oparte na komunikatach; bufor może zawierać wiele komunikatów, więc otrzymanie mniejszej liczby bajtów nie oznacza końca pliku. Aplikacja nie jest blokowana w tym przypadku, ponieważ może w tym przypadku `CFile` , i może kontynuować odczytywanie komunikatów z bufora do momentu, gdy bufor jest pusty. Funkcja [CArchive:: IsBufferEmpty](../../mfc/reference/carchive-class.md#isbufferempty) jest przydatna do monitorowania stanu buforu Archiwum w takich przypadkach.

Aby uzyskać więcej informacji o używaniu programu `CSocketFile` , zobacz artykuł [Windows Sockets: używanie gniazd z archiwami](../../mfc/windows-sockets-using-sockets-with-archives.md) i [Windows Sockets: przykład gniazd korzystających z archiwów](../../mfc/windows-sockets-example-of-sockets-using-archives.md).

## <a name="see-also"></a>Zobacz też

[Klasa CFile](../../mfc/reference/cfile-class.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasa CAsyncSocket](../../mfc/reference/casyncsocket-class.md)<br/>
[Klasa CSocket](../../mfc/reference/csocket-class.md)
