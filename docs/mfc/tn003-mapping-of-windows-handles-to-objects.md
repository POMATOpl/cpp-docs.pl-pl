---
description: 'Dowiedz się więcej na temat: TN003: mapowanie uchwytów systemu Windows do obiektów'
title: 'TN003: mapowanie uchwytów okien na obiekty'
ms.date: 11/04/2016
f1_keywords:
- vc.mapping
helpviewer_keywords:
- TN003
- handle maps
- Windows handles to objects [MFC]
- mappings [MFC], Windows handles to objects
ms.assetid: fbea9f38-992c-4091-8dbc-f29e288617d6
ms.openlocfilehash: e4a0bfa2315ec2b9d67d884d4fdebe314599f454
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216044"
---
# <a name="tn003-mapping-of-windows-handles-to-objects"></a>TN003: mapowanie uchwytów okien na obiekty

Ta Uwaga opisuje procedury MFC, które obsługują mapowanie uchwytów obiektów systemu Windows do obiektów C++.

## <a name="the-problem"></a>Problem

Obiekty systemu Windows są zwykle reprezentowane przez różne obiekty [uchwytu](/windows/win32/WinProg/windows-data-types) klasy MFC zawijają uchwyty obiektów systemu Windows z obiektami języka C++. Funkcje zawijania uchwytów biblioteki klas MFC pozwalają znaleźć obiekt języka C++, który otacza obiekt systemu Windows, który ma określony uchwyt. Jednak czasami obiekt nie ma obiektu otoki C++ i w tym momencie system tworzy tymczasowy obiekt do działania jako otoka C++.

Obiekty systemu Windows korzystające z map obsługi są następujące:

- HWND ([CWnd](../mfc/reference/cwnd-class.md) i `CWnd` -pochodne klasy)

- UŻYWAJĄCY HDC ([](../mfc/reference/cdc-class.md) `CDC` wyskakujące i pochodne klasy)

- HMENU ([CMenu](../mfc/reference/cmenu-class.md))

- HPEN ([CGdiObject](../mfc/reference/cgdiobject-class.md))

- HBRUSH ( `CGdiObject` )

- HFONT ( `CGdiObject` )

- HBITMAP ( `CGdiObject` )

- HPALETTE ( `CGdiObject` )

- HRGN ( `CGdiObject` )

- HIMAGELIST ([Korzystanie CImageList](../mfc/reference/cimagelist-class.md))

- GNIAZDO ([CSocket](../mfc/reference/csocket-class.md))

Uwzględniając dojście do dowolnego z tych obiektów, można znaleźć obiekt MFC, który zawija uchwyt poprzez wywołanie metody statycznej `FromHandle` . Na przykład, mając Właściwość HWND o nazwie *HWND*, poniższy wiersz zwróci wskaźnik do obiektu `CWnd` , który zawija wartość *HWND*:

```
CWnd::FromHandle(hWnd)
```

Jeśli *Właściwość HWND* nie ma określonego obiektu otoki, jest tworzona tymczasowa, `CWnd` aby otoczyć *Właściwość HWND*. Dzięki temu możliwe jest uzyskanie prawidłowego obiektu C++ z dowolnego uchwytu.

Po utworzeniu obiektu otoki można pobrać jego uchwyt z publicznej zmiennej składowej klasy otoki. W przypadku `CWnd` , *m_hWnd* zawiera właściwość HWND dla tego obiektu.

## <a name="attaching-handles-to-mfc-objects"></a>Dołączanie dojść do obiektów MFC

W przypadku nowo utworzonego obiektu otoki uchwytu i dojścia do obiektu systemu Windows można skojarzyć te dwa, wywołując `Attach` funkcję w tym przykładzie:

```
CWnd myWnd;
myWnd.Attach(hWnd);
```

Oznacza to, że wpis w trwałej mapie kojarzy *myWnd* i *HWND*. Wywołanie `CWnd::FromHandle(hWnd)` zwróci teraz wskaźnik do *myWnd*. Po usunięciu *myWnd* , destruktor automatycznie niszczy *Właściwość HWND* przez wywołanie funkcji [DestroyWindow](/windows/win32/api/winuser/nf-winuser-destroywindow) systemu Windows. Jeśli nie jest to wymagane, *Właściwość HWND* musi być odłączona od *myWnd* przed zniszczeniem *myWnd* (zwykle przy opuszczaniu zakresu, w którym zdefiniowano *myWnd* ). `Detach`Ta metoda.

```
myWnd.Detach();
```

## <a name="more-about-temporary-objects"></a>Więcej informacji o obiektach tymczasowych

Obiekty tymczasowe są tworzone za każdym razem `FromHandle` , gdy zostanie dostarczone dojście, które nie ma jeszcze obiektu otoki. Te obiekty tymczasowe są odłączone od ich uchwytu i usuwane przez `DeleteTempMap` funkcje. Domyślnie [CWinThread:: OnIdle](../mfc/reference/cwinthread-class.md#onidle) automatycznie wywołuje `DeleteTempMap` dla każdej klasy, która obsługuje mapy uchwytów tymczasowych. Oznacza to, że nie można założyć, że wskaźnik do obiektu tymczasowego będzie prawidłowy poza punktem wyjścia z funkcji, w której uzyskano wskaźnik.

## <a name="wrapper-objects-and-multiple-threads"></a>Obiekty otoki i wiele wątków

Zarówno obiekt tymczasowy, jak i trwały są utrzymywane dla każdego wątku. Oznacza to, że jeden wątek nie może uzyskać dostępu do obiektów otoki języka C++ innego wątku, niezależnie od tego, czy jest on tymczasowy, czy trwały.

Aby przekazać te obiekty z jednego wątku do innego, należy zawsze wysyłać je jako ich `HANDLE` typy natywne. Przekazanie obiektu otoki C++ z jednego wątku do innego często spowoduje nieoczekiwane wyniki.

## <a name="see-also"></a>Zobacz też

[Uwagi techniczne według numeru](../mfc/technical-notes-by-number.md)<br/>
[Uwagi techniczne według kategorii](../mfc/technical-notes-by-category.md)
