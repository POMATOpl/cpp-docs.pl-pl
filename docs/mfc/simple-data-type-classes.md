---
description: 'Dowiedz się więcej o: proste klasy typów danych'
title: Proste klasy typów danych
ms.date: 11/04/2016
f1_keywords:
- vc.classes.data
helpviewer_keywords:
- scalar classes [MFC]
- data classes [MFC]
- simple data type classes [MFC]
ms.assetid: 0d591d68-0a33-49e9-8a6d-90c90de5c16a
ms.openlocfilehash: 4ce6e799cc30dddde18a50802e01c872c54d1d3a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216967"
---
# <a name="simple-data-type-classes"></a>Proste klasy typów danych

Poniższe klasy hermetyzują współrzędne rysowania, ciągi znaków i informacje o dacie i godzinie, co pozwala wygodnie korzystać z składni języka C++. Te obiekty są szeroko używane jako parametry do funkcji składowych klas systemu Windows w bibliotece klas. Ponieważ `CPoint` , `CSize` , i `CRect` odpowiada strukturom typu **punkt**, **rozmiar** i **prostokąt** , w Windows SDK można używać obiektów tych klas języka C++ wszędzie tam, gdzie można używać tych struktur języka C. Klasy zapewniają przydatne interfejsy za pomocą ich funkcji Członkowskich. `CStringT` zapewnia bardzo elastyczne ciągi znaków dynamicznych. `CTime`, `COleDateTime` , `CTimeSpan` i `COleTimeSpan` reprezentują wartości daty i godziny. Aby uzyskać więcej informacji na temat tych klas, zobacz [Data i godzina](../atl-mfc-shared/date-and-time.md)artykułu.

Klasy zaczynające się od " `COle` " są hermetyzacją typów danych dostarczanych przez OLE. Te typy danych mogą być używane w programach systemu Windows niezależnie od tego, czy są używane inne funkcje OLE.

[Klasa CStringT](../atl-mfc-shared/reference/cstringt-class.md)<br/>
Zawiera ciągi znaków.

[CTime](../atl-mfc-shared/reference/ctime-class.md)<br/>
Przechowuje bezwzględne wartości czasu i daty.

[COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md)<br/>
Otoka **dla typu automatyzacji** OLE. Reprezentuje wartości daty i godziny.

[CTimeSpan](../atl-mfc-shared/reference/ctimespan-class.md)<br/>
Zawiera względne wartości czasu i daty.

[COleDateTimeSpan](../atl-mfc-shared/reference/coledatetimespan-class.md)<br/>
Przechowuje wartości względne `COleDateTime` , takie jak różnica między dwiema `COleDateTime` wartościami.

[CPoint](../atl-mfc-shared/reference/cpoint-class.md)<br/>
Przechowuje pary współrzędnych (x, y).

[CSize](../atl-mfc-shared/reference/csize-class.md)<br/>
Utrzymuje odległość, położenie względne lub sparowane wartości.

[CRect](../atl-mfc-shared/reference/crect-class.md)<br/>
Utrzymuje współrzędne obszarów prostokątów.

[Korzystanie CImageList](../mfc/reference/cimagelist-class.md)<br/>
Oferuje funkcje listy obrazów systemu Windows. Listy obrazów są używane z kontrolkami list i kontrolkami drzewa. Mogą być również używane do przechowywania i archiwizowania zestawu o takich samych mapach bitowych.

[COleVariant](../mfc/reference/colevariant-class.md)<br/>
Otoka **dla typu automatyzacji** OLE. Dane w **odmianie** s mogą być przechowywane w wielu formatach.

[COleCurrency](../mfc/reference/colecurrency-class.md)<br/>
Otoka dla **waluty** typu automatyzacji OLE, typ arytmetyczny stałej z 15 cyfr przed separatorem dziesiętnym i 4 cyfr po.

> [!NOTE]
> `CRect`, `CSize` i `CPoint` mogą być używane w aplikacjach ATL lub MFC. Ponadto `CStringT` zapewnia `CString` klasy podobnej do biblioteki MFC. Aby uzyskać więcej informacji na temat udostępnionych klas narzędzi, zobacz [udostępnione klasy](../atl-mfc-shared/atl-mfc-shared-classes.md).

## <a name="see-also"></a>Zobacz też

[Przegląd klas](../mfc/class-library-overview.md)
