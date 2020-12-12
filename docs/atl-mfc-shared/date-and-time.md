---
description: 'Dowiedz się więcej o: Data i godzina'
title: Data i godzina
ms.date: 08/13/2019
helpviewer_keywords:
- time, MFC programming
- time
- MFC, date and time
- dates, MFC
ms.assetid: ecf56dc5-d418-4603-ad3e-af7e205a6403
ms.openlocfilehash: 4a8f2d5c9537f07c5d410361e79bf14a12778bc8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167035"
---
# <a name="date-and-time"></a>Data i godzina

MFC obsługuje kilka różnych sposobów pracy z datami i godzinami:

- Obsługa [typu danych Data](../atl-mfc-shared/date-type.md)automatyzacji. Data obsługuje wartości daty, godziny i daty/godziny. Klasy [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md) i [COleDateTimeSpan](../atl-mfc-shared/reference/coledatetimespan-class.md) hermetyzują tę funkcję. Współpracują z klasą [COleVariant](../mfc/reference/colevariant-class.md) za pomocą obsługi automatyzacji.

- Klasy czasu ogólnego przeznaczenia. Klasy [CTime](../atl-mfc-shared/reference/ctime-class.md) i [CTimeSpan](../atl-mfc-shared/reference/ctimespan-class.md) hermetyzują większość funkcji skojarzonych z biblioteką czasu standardowego ANSI, która jest zadeklarowana w Time. H.

- Obsługa zegara systemowego. W przypadku biblioteki MFC w wersji 3,0 dodano obsługę `CTime` dla systemu Win32 `SYSTEMTIME` i `FILETIME` typów danych.

## <a name="date-and-time-automation-support"></a>Data i godzina: obsługa automatyzacji

Klasa [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md) zapewnia sposób reprezentowania informacji o dacie i godzinie. Zapewnia bardziej szczegółowy stopień szczegółowości i większy zakres niż Klasa [CTime](../atl-mfc-shared/reference/ctime-class.md) . Klasa [COleDateTimeSpan](../atl-mfc-shared/reference/coledatetimespan-class.md) reprezentuje czas, który upłynął, na przykład różnicę między dwoma `COleDateTime` obiektami.

`COleDateTime`Klasy i `COleDateTimeSpan` są przeznaczone do użytku z `COleVariant` klasą. `COleDateTime` i `COleDateTimeSpan` są również przydatne w programowaniu baz danych MFC, ale mogą być używane zawsze, gdy chcesz manipulować wartościami daty i godziny. Chociaż `COleDateTime` Klasa ma większy zakres wartości i bardziej szczegółowy stopień szczegółowości niż `CTime` Klasa, wymaga więcej miejsca do magazynowania na obiekt niż `CTime` . Istnieją również pewne specjalne uwagi podczas pracy z bazowym typem daty. Aby uzyskać więcej informacji na temat implementacji daty, zobacz [Typ daty](../atl-mfc-shared/date-type.md).

`COleDateTime` obiekty mogą służyć do reprezentowania dat z zakresu od 1 stycznia 100 do 31 grudnia 9999. `COleDateTime` obiekty są wartościami zmiennoprzecinkowymi, z przybliżoną rozdzielczością 1 milisekund. `COleDateTime` jest oparty na typie danych Data, zdefiniowanym w dokumentacji MFC w obszarze [COleDateTime:: operator Date](../atl-mfc-shared/reference/coledatetime-class.md#operator_date). Rzeczywista implementacja daty wykracza poza te granice. `COleDateTime`Implementacja nakłada te granice, aby ułatwić pracę z klasą.

`COleDateTime` nie obsługuje dat w postaci juliańskim. W kalendarzu gregoriańskim założono, że w czasie od 1 stycznia 100.

`COleDateTime` ignoruje czas letni (DST). Poniższy przykład kodu porównuje dwie metody obliczania przedziału czasu, który przekracza datę przełączania do czasu letniego: jeden przy użyciu CRT, a drugi przy użyciu `COleDateTime` .

Pierwsza metoda ustawia odpowiednio dwa `CTime` obiekty, *time1* i *time2*, do 5 kwietnia i 6 kwietnia, przy użyciu standardowych struktur typu C `tm` i `time_t` . Kod wyświetla *time1* i *time2* oraz przedział czasu między nimi.

Druga metoda tworzy dwa `COleDateTime` obiekty `oletime1` i `oletime2` i ustawia je na takie same daty, jak *time1* i *time2*. Wyświetla `oletime1` i `oletime2` i odstęp czasu między nimi.

CRT prawidłowo oblicza różnicę wynoszącą 23 godziny. `COleDateTimeSpan` Oblicza różnicę przez 24 godziny.

[!code-cpp[NVC_ATLMFC_Utilities#176](../atl-mfc-shared/codesnippet/cpp/date-and-time-automation-support_1.cpp)]

### <a name="get-the-current-time"></a>Pobierz bieżącą godzinę

Poniższa procedura pokazuje, jak utworzyć `COleDateTime` obiekt i zainicjować go z bieżącą godziną.

#### <a name="to-get-the-current-time"></a>Aby uzyskać bieżącą godzinę

1. Utwórz `COleDateTime` obiekt.

1. Wywołanie `GetCurrentTime` .

   [!code-cpp[NVC_ATLMFC_Utilities#177](../atl-mfc-shared/codesnippet/cpp/current-time-automation-classes_1.cpp)]

### <a name="calculate-elapsed-time"></a>Oblicz czas, który upłynął

Ta procedura pokazuje, jak obliczyć różnicę między dwoma `COleDateTime` obiektami i uzyskać `COleDateTimeSpan` wynik.

#### <a name="to-calculate-elapsed-time"></a>Aby obliczyć czas, który upłynął

1. Utwórz dwa `COleDateTime` obiekty.

1. Ustaw jeden z `COleDateTime` obiektów na bieżącą godzinę.

1. Wykonywanie czasochłonnych zadań.

1. Ustaw inny `COleDateTime` obiekt na bieżącą godzinę.

1. Weź różnicę między nimi dwa razy.

   [!code-cpp[NVC_ATLMFC_Utilities#178](../atl-mfc-shared/codesnippet/cpp/elapsed-time-automation-classes_1.cpp)]

### <a name="format-a-time"></a>Formatowanie czasu

#### <a name="to-format-a-time"></a>Aby sformatować godzinę

Użyj `Format` funkcji member elementu [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md) lub [COleDateTimeSpan](../atl-mfc-shared/reference/coledatetimespan-class.md) , aby utworzyć ciąg znaków reprezentujący godzinę lub czas, który upłynął.

   [!code-cpp[NVC_ATLMFC_Utilities#179](../atl-mfc-shared/codesnippet/cpp/formatting-time-automation-classes_1.cpp)]

Aby uzyskać więcej informacji, zobacz Klasa [COleVariant](../mfc/reference/colevariant-class.md).

## <a name="date-and-time-database-support"></a>Data i godzina: obsługa bazy danych

Począwszy od wersji 4,0, programowanie baz danych MFC używa klas [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md) i [COleDateTimeSpan](../atl-mfc-shared/reference/coledatetimespan-class.md) do reprezentowania danych daty i godziny. Klasy te, również używane w automatyzacji, są wyprowadzane z klasy [COleVariant](../mfc/reference/colevariant-class.md). Zapewniają one lepszą obsługę zarządzania danymi daty i godziny niż [CTime](../atl-mfc-shared/reference/ctime-class.md) i [CTimeSpan](../atl-mfc-shared/reference/ctimespan-class.md).

## <a name="date-and-time-systemtime-support"></a>Data i godzina: obsługa SYSTEMTIME

Klasa [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md) ma konstruktory akceptujące czasy systemu i plików z Win32.

Struktura Win32 `FILETIME` reprezentuje czas jako wartość 64-bitową. Jest to wygodniejszy format magazynu wewnętrznego niż `SYSTEMTIME` Struktura i format używany przez Win32 do reprezentowania czasu tworzenia pliku. Aby uzyskać informacje na temat struktury SYSTEMTIME, zobacz [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime). Aby uzyskać informacje na temat struktury FILETIME, zobacz [FILETIME](/windows/desktop/api/minwinbase/ns-minwinbase-filetime).

## <a name="see-also"></a>Zobacz też

[Pojęcia](../mfc/mfc-concepts.md)\
[Ogólne tematy dotyczące MFC](../mfc/general-mfc-topics.md)
