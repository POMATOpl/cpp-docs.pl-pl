---
description: 'Dowiedz się więcej o: klasach udostępnionych przez MFC i ATL'
title: Klasy współdzielone MFC i ATL
ms.date: 11/04/2016
helpviewer_keywords:
- shared classes, classes
ms.assetid: ca8b4b6b-744d-430b-b31f-d5b2f17bf210
ms.openlocfilehash: df196f92b7b16742545a7d82320ef4fe8da77fe2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166788"
---
# <a name="classes-shared-by-mfc-and-atl"></a>Klasy współdzielone MFC i ATL

W poniższej tabeli wymieniono klasy współdzielone między MFC i ATL.

|Klasa|Opis|Plik nagłówka|
|-----------|-----------------|-----------------|
|[CFileTime](../../atl-mfc-shared/reference/cfiletime-class.md)|Zapewnia metody zarządzania wartościami daty i godziny skojarzonych z plikiem.|atltime. h|
|[CFileTimeSpan](../../atl-mfc-shared/reference/cfiletimespan-class.md)|Zapewnia metody zarządzania względnymi wartościami daty i godziny skojarzonych z plikiem.|atltime. h|
|[CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md)|Reprezentuje obiekt String z buforem o stałym znaku.|CStringT. h|
|[Funkcji CImage](../../atl-mfc-shared/reference/cimage-class.md)|Zapewnia obsługę ulepszonej mapy bitowej, w tym możliwość ładowania i zapisywania obrazów w formatach JPEG, GIF, BMP i Portable Network Graphics (PNG).|atlimage. h|
|[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)|Hermetyzuje typ danych daty używany w automatyzacji OLE.|ATLComTime. h|
|[COleDateTimeSpan](../../atl-mfc-shared/reference/coledatetimespan-class.md)|Reprezentuje czas względny, przedział czasu.|ATLComTime. h|
|[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)|Klasa podobna do struktury [punktu](/windows/win32/api/windef/ns-windef-point) systemu Windows, która zawiera również funkcje elementów członkowskich do manipulowania `CPoint` i `POINT` struktur.|atltypes. h|
|[CRect](../../atl-mfc-shared/reference/crect-class.md)|Klasa podobna do struktury Windows [Rect](/windows/win32/api/windef/ns-windef-rect) , która obejmuje również funkcje elementów członkowskich do manipulowania `CRect` obiektami i `RECT` strukturami systemu Windows.|atltypes. h|
|[CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)|Reprezentuje `CSimpleStringT` obiekt.|atlsimpstr. h|
|[CSize](../../atl-mfc-shared/reference/csize-class.md)|Klasa podobna do struktury [rozmiaru](/windows/win32/api/windef/ns-windef-size) systemu Windows, która implementuje względną współrzędną lub położeniu.|atltypes. h|
|[CStrBufT](../../atl-mfc-shared/reference/cstrbuft-class.md)|Umożliwia automatyczne czyszczenie zasobów `GetBuffer` i `ReleaseBuffer` wywoływanie na istniejącym `CStringT` obiekcie.|atlsimpstr. h|
|[CStringData](../../atl-mfc-shared/reference/cstringdata-class.md)|Reprezentuje dane obiektu ciągu.|atlsimpstr. h|
|[CStringT](../../atl-mfc-shared/reference/cstringt-class.md)|Reprezentuje `CStringT` obiekt.|CStringT. h (zależna od MFC) pliku atlstr. h (niezależna od MFC)|
|[CTime](../../atl-mfc-shared/reference/ctime-class.md)|Reprezentuje bezwzględną godzinę i datę.|atltime. h|
|[CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)|Czas, który jest wewnętrznie przechowywany jako liczba sekund w przedziale czasu.|atltime. h|
|[IAtlStringMgr](../../atl-mfc-shared/reference/iatlstringmgr-class.md)|Reprezentuje interfejs `CStringT` Menedżera pamięci.|atlsimpstr. h|

## <a name="see-also"></a>Zobacz też

[Klasy udostępnione ATL/MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)
