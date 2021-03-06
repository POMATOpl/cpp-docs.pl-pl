---
description: 'Dowiedz się więcej na temat: Klasa CFileTime'
title: Klasa CFileTime
ms.date: 10/18/2018
f1_keywords:
- CFileTime
- ATLTIME/ATL::CFileTime
- ATLTIME/ATL::CFileTime::CFileTime
- ATLTIME/ATL::CFileTime::GetCurrentTime
- ATLTIME/ATL::CFileTime::GetTime
- ATLTIME/ATL::CFileTime::LocalToUTC
- ATLTIME/ATL::CFileTime::SetTime
- ATLTIME/ATL::CFileTime::UTCToLocal
- ATLTIME/ATL::CFileTime::Day
- ATLTIME/ATL::CFileTime::Hour
- ATLTIME/ATL::CFileTime::Millisecond
- ATLTIME/ATL::CFileTime::Minute
- ATLTIME/ATL::CFileTime::Second
- ATLTIME/ATL::CFileTime::Week
helpviewer_keywords:
- CFileTime class
- shared classes, CFileTime
ms.assetid: 1a358a65-1383-4124-b0d4-59b026e6860f
ms.openlocfilehash: 95b46c188be60da787612a30ebff161a4ecf5966
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166853"
---
# <a name="cfiletime-class"></a>Klasa CFileTime

Ta klasa udostępnia metody zarządzania wartościami daty i godziny skojarzonych z plikiem.

## <a name="syntax"></a>Składnia

```
class CFileTime :  public FILETIME
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CFileTime::CFileTime](#cfiletime)|Konstruktor.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CFileTime::GetCurrentTime](#getcurrenttime)|Wywołaj tę funkcję statyczną, aby pobrać `CFileTime` obiekt, który reprezentuje bieżącą datę i godzinę systemową.|
|[CFileTime:: GetTime](#gettime)|Wywołaj tę metodę, aby pobrać godzinę z `CFileTime` obiektu.|
|[CFileTime::LocalToUTC](#localtoutc)|Wywołaj tę metodę, aby skonwertować czas lokalnego pliku do czasu pliku na podstawie uniwersalnego czasu koordynowanego (UTC).|
|[CFileTime:: SetTime](#settime)|Wywołaj tę metodę, aby ustawić datę i godzinę przechowywane przez `CFileTime` obiekt.|
|[CFileTime::UTCToLocal](#utctolocal)|Wywołaj tę metodę, aby przekonwertować czas na podstawie uniwersalnego czasu koordynowanego (UTC) na czas pliku lokalnego.|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CFileTime:: operator-](#operator_-)|Ten operator jest używany do wykonywania odejmowania `CFileTime` `CFileTimeSpan` obiektu lub.|
|[CFileTime:: operator! =](#operator_neq)|Ten operator porównuje dwa `CFileTime` obiekty pod kątem nierówności.|
|[CFileTime:: operator +](#operator_add)|Ten operator służy do wykonywania dodawania do `CFileTimeSpan` obiektu.|
|[CFileTime:: operator + =](#operator_add_eq)|Ten operator służy do wykonywania dodawania do `CFileTimeSpan` obiektu i przypisywania wyniku do bieżącego obiektu.|
|[CFileTime:: operator &lt;](#operator_lt)|Ten operator porównuje dwa `CFileTime` obiekty, aby określić, że są one mniejsze.|
|[CFileTime:: operator &lt;=](#operator_lt_eq)|Ten operator porównuje dwa `CFileTime` obiekty, aby określić równość lub mniejszą.|
|[CFileTime:: operator =](#operator_eq)|Operator przypisania.|
|[CFileTime:: operator-=](#operator_-_eq)|Ten operator służy do wykonywania odejmowania `CFileTimeSpan` obiektu i przypisywania wyniku do bieżącego obiektu.|
|[CFileTime:: operator = =](#operator_eq_eq)|Ten operator porównuje dwa `CFileTime` obiekty pod kątem równości.|
|[CFileTime:: operator &gt;](#operator_gt)|Ten operator porównuje dwa `CFileTime` obiekty w celu określenia większego.|
|[CFileTime:: operator &gt;=](#operator_gt_eq)|Ten operator porównuje dwa `CFileTime` obiekty, aby określić równość lub większą.|

### <a name="public-constants"></a>Stałe publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CFileTime::D AY](#day)|Statyczny element członkowski danych przechowujący liczbę interwałów 100-nanosekund, które składają się na jeden dzień.|
|[CFileTime:: Hour](#hour)|Statyczny element członkowski danych przechowujący liczbę interwałów 100-nanosekund, które składają się na jedną godzinę.|
|[CFileTime:: milisekundy](#millisecond)|Statyczny element członkowski danych przechowujący liczbę interwałów 100-nanosekund, które składają się na jedną milisekundę.|
|[CFileTime:: minuta](#minute)|Statyczny element członkowski danych przechowujący liczbę interwałów 100-nanosekund, które składają się na jedną minutę.|
|[CFileTime:: Second](#second)|Statyczny element członkowski danych przechowujący liczbę interwałów 100-nanosekund, które składają się na jedną sekundę.|
|[CFileTime:: tydzień](#week)|Statyczny element członkowski danych przechowujący liczbę interwałów 100-nanosekund, które składają się z jednego tygodnia.|

## <a name="remarks"></a>Uwagi

Ta klasa udostępnia metody zarządzania wartościami daty i godziny skojarzonych z tworzeniem, dostępem i modyfikacją plików. Metody i dane tej klasy są często używane w połączeniu z `CFileTimeSpan` obiektami, które zajmują się względnymi wartościami czasu.

Wartość daty i godziny jest przechowywana jako wartość 64-bitowa reprezentująca liczbę interwałów 100-nanosekund od 1 stycznia 1601. Jest to format uniwersalnego czasu koordynowanego (UTC).

Następujące statyczne zmienne składowe const są udostępniane w celu uproszczenia obliczeń:

|Zmienna członkowska|Liczba interwałów 100-nanosekund|
|---------------------|-----------------------------------------|
|Milisekund|10 000|
|Second|Milisekundy \* 1 000|
|Minuta|Drugi \* 60|
|Godzina|Minuta \* 60|
|Dzień|Godzina \* 24|
|Tydzień|Dzień \* 7|

**Uwaga** Nie wszystkie systemy plików mogą rejestrować i czas ostatniego dostępu, a nie wszystkie systemy plików rejestruje je w taki sam sposób. Na przykład w systemie plików systemu Windows NT FAT czas utworzenia ma rozdzielczość 10 milisekund, godzina zapisu ma rozdzielczość 2 sekund, a czas dostępu to 1 dzień (Data dostępu). W systemie plików NTFS czas dostępu ma rozdzielczość 1 godzina. Ponadto system plików FAT rejestruje czasy na dysku w czasie lokalnym, ale system plików NTFS rejestruje czasy na dysku w formacie UTC. Aby uzyskać więcej informacji, zobacz [godziny pliku](/windows/win32/SysInfo/file-times).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`FILETIME`

`CFileTime`

## <a name="requirements"></a>Wymagania

**Nagłówek:** atltime. h

## <a name="cfiletimecfiletime"></a><a name="cfiletime"></a> CFileTime::CFileTime

Konstruktor.

```
CFileTime() throw();
CFileTime(const FILETIME& ft) throw();
CFileTime(ULONGLONG nTime) throw();
```

### <a name="parameters"></a>Parametry

*stóp*<br/>
Struktura [FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime) .

*nTime*<br/>
Data i godzina wyrażona jako wartość 64-bitowa.

### <a name="remarks"></a>Uwagi

`CFileTime`Obiekt można utworzyć przy użyciu istniejącej daty i godziny ze `FILETIME` struktury lub wyrażonej jako wartość 64-bitowa (w formatach czasu lokalnego lub uniwersalnego czasu koordynowanego (UTC). Domyślny konstruktor ustawia czas na 0.

## <a name="cfiletimeday"></a><a name="day"></a> CFileTime::D AY

Statyczny element członkowski danych przechowujący liczbę interwałów 100-nanosekund, które składają się na jeden dzień.

```
static const ULONGLONG Day = Hour* 24;
```

### <a name="example"></a>Przykład

Zobacz przykład dla [CFileTime:: milisekund](#millisecond).

## <a name="cfiletimegetcurrenttime"></a><a name="getcurrenttime"></a> CFileTime::GetCurrentTime

Wywołaj tę funkcję statyczną, aby pobrać `CFileTime` obiekt, który reprezentuje bieżącą datę i godzinę systemową.

```
static CFileTime GetCurrentTime() throw();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca bieżącą datę i godzinę systemową w formacie uniwersalnego czasu koordynowanego (UTC).

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCFiles#41](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_1.cpp)]

## <a name="cfiletimegettime"></a><a name="gettime"></a> CFileTime:: GetTime

Wywołaj tę metodę, aby pobrać godzinę z `CFileTime` obiektu.

```
ULONGLONG GetTime() const throw();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca datę i godzinę jako liczbę 64-bitową, która może być w formacie UTC (Local lub Coordinated Universal Time).

## <a name="cfiletimehour"></a><a name="hour"></a> CFileTime:: Hour

Statyczny element członkowski danych przechowujący liczbę interwałów 100-nanosekund, które składają się na jedną godzinę.

```
static const ULONGLONG Hour = Minute* 60;
```

### <a name="example"></a>Przykład

Zobacz przykład dla [CFileTime:: milisekund](#millisecond).

## <a name="cfiletimelocaltoutc"></a><a name="localtoutc"></a> CFileTime::LocalToUTC

Wywołaj tę metodę, aby skonwertować czas lokalnego pliku do czasu pliku na podstawie uniwersalnego czasu koordynowanego (UTC).

```
CFileTime LocalToUTC() const throw();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca `CFileTime` obiekt zawierający godzinę w formacie UTC.

### <a name="example"></a>Przykład

Zobacz przykład dla [CFileTime:: UTCToLocal](#utctolocal).

## <a name="cfiletimemillisecond"></a><a name="millisecond"></a> CFileTime:: milisekundy

Statyczny element członkowski danych przechowujący liczbę interwałów 100-nanosekund, które składają się na jedną milisekundę.

```
static const ULONGLONG Millisecond = 10000;
```

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCFiles#44](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_2.cpp)]

## <a name="cfiletimeminute"></a><a name="minute"></a> CFileTime:: minuta

Statyczny element członkowski danych przechowujący liczbę interwałów 100-nanosekund, które składają się na jedną minutę.

```
static const ULONGLONG Minute = Second* 60;
```

### <a name="example"></a>Przykład

Zobacz przykład dla [CFileTime:: milisekund](#millisecond).

## <a name="cfiletimeoperator--"></a><a name="operator_-"></a> CFileTime:: operator-

Ten operator jest używany do wykonywania odejmowania `CFileTime` `CFileTimeSpan` obiektu lub.

```
CFileTime operator-(CFileTimeSpan span) const throw();
CFileTimeSpan operator-(CFileTime ft) const throw();
```

### <a name="parameters"></a>Parametry

*span*<br/>
Obiekt `CFileTimeSpan`.

*stóp*<br/>
Obiekt `CFileTime`.

### <a name="return-value"></a>Wartość zwracana

Zwraca `CFileTime` obiekt lub `CFileTimeSpan` obiekt reprezentujący wynik różnicy czasu między dwoma obiektami.

## <a name="cfiletimeoperator-"></a><a name="operator_neq"></a> CFileTime:: operator! =

Ten operator porównuje dwa `CFileTime` obiekty pod kątem nierówności.

```
bool operator!=(CFileTime ft) const throw();
```

### <a name="parameters"></a>Parametry

*stóp*<br/>
`CFileTime`Obiekt, który ma zostać porównany.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość TRUE, jeśli porównywany element nie jest równy `CFileTime` obiektowi, w przeciwnym razie false.

## <a name="cfiletimeoperator-"></a><a name="operator_add"></a> CFileTime:: operator +

Ten operator służy do wykonywania dodawania do `CFileTimeSpan` obiektu.

```
CFileTime operator+(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parametry

*span*<br/>
Obiekt `CFileTimeSpan`.

### <a name="return-value"></a>Wartość zwracana

Zwraca `CFileTime` obiekt reprezentujący wynik oryginalnego czasu powiększony o czas względny.

## <a name="cfiletimeoperator-"></a><a name="operator_add_eq"></a> CFileTime:: operator + =

Ten operator służy do wykonywania dodawania do `CFileTimeSpan` obiektu i przypisywania wyniku do bieżącego obiektu.

```
CFileTime& operator+=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>Parametry

*span*<br/>
Obiekt `CFileTimeSpan`.

### <a name="return-value"></a>Wartość zwracana

Zwraca zaktualizowany `CFileTime` obiekt, reprezentujący wynik pierwotnego czasu powiększony o czas względny.

## <a name="cfiletimeoperator-lt"></a><a name="operator_lt"></a> CFileTime:: operator &lt;

Ten operator porównuje dwa `CFileTime` obiekty, aby określić, że są one mniejsze.

```
bool operator<(CFileTime ft) const throw();
```

### <a name="parameters"></a>Parametry

*stóp*<br/>
`CFileTime`Obiekt, który ma zostać porównany.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość TRUE, jeśli pierwszy obiekt jest mniejszy (wcześniej w czasie) niż drugi, w przeciwnym razie FALSE.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCFiles#43](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_3.cpp)]

## <a name="cfiletimeoperator-lt"></a><a name="operator_lt_eq"></a> CFileTime:: operator &lt;=

Ten operator porównuje dwa `CFileTime` obiekty, aby określić równość lub mniejszą.

```
bool operator<=(CFileTime ft) const throw();
```

### <a name="parameters"></a>Parametry

*stóp*<br/>
`CFileTime`Obiekt, który ma zostać porównany.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość TRUE, jeśli pierwszy obiekt jest mniejszy niż (wcześniej w czasie) lub równy drugiemu, w przeciwnym razie FALSE.

## <a name="cfiletimeoperator-"></a><a name="operator_eq"></a> CFileTime:: operator =

Operator przypisania.

```
CFileTime& operator=(const FILETIME& ft) throw();
```

### <a name="parameters"></a>Parametry

*stóp*<br/>
`CFileTime`Obiekt zawierający nową godzinę i datę.

### <a name="return-value"></a>Wartość zwracana

Zwraca zaktualizowany `CFileTime` obiekt.

## <a name="cfiletimeoperator--"></a><a name="operator_-_eq"></a> CFileTime:: operator-=

Ten operator służy do wykonywania odejmowania `CFileTimeSpan` obiektu i przypisywania wyniku do bieżącego obiektu.

```
CFileTime& operator-=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>Parametry

*span*<br/>
`CFileTimeSpan`Obiekt zawierający względny czas do odjęcia.

### <a name="return-value"></a>Wartość zwracana

Zwraca zaktualizowany `CFileTime` obiekt.

## <a name="cfiletimeoperator-"></a><a name="operator_eq_eq"></a> CFileTime:: operator = =

Ten operator porównuje dwa `CFileTime` obiekty pod kątem równości.

```
bool operator==(CFileTime ft) const throw();
```

### <a name="parameters"></a>Parametry

*stóp*<br/>
`CFileTime`Obiekt do porównania.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość TRUE, jeśli obiekty są równe, w przeciwnym razie FALSE.

## <a name="cfiletimeoperator-gt"></a><a name="operator_gt"></a> CFileTime:: operator &gt;

Ten operator porównuje dwa `CFileTime` obiekty w celu określenia większego.

```
bool operator>(CFileTime ft) const throw();
```

### <a name="parameters"></a>Parametry

*stóp*<br/>
`CFileTime`Obiekt, który ma zostać porównany.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość TRUE, jeśli pierwszy obiekt jest większy niż (później) niż drugi, w przeciwnym razie FALSE.

## <a name="cfiletimeoperator-gt"></a><a name="operator_gt_eq"></a> CFileTime:: operator &gt;=

Ten operator porównuje dwa `CFileTime` obiekty, aby określić równość lub większą.

```
bool operator>=(CFileTime ft) const throw();
```

### <a name="parameters"></a>Parametry

*stóp*<br/>
`CFileTime`Obiekt, który ma zostać porównany.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość TRUE, jeśli pierwszy obiekt jest większy niż (później w czasie) lub równy drugiemu, w przeciwnym razie FALSE.

## <a name="cfiletimesecond"></a><a name="second"></a> CFileTime:: Second

Statyczny element członkowski danych przechowujący liczbę interwałów 100-nanosekund, które składają się na jeden dzień.

```
static const ULONGLONG Second = Millisecond* 1000;
```

### <a name="example"></a>Przykład

Zobacz przykład dla [CFileTime:: milisekund](#millisecond).

## <a name="cfiletimesettime"></a><a name="settime"></a> CFileTime:: SetTime

Wywołaj tę metodę, aby ustawić datę i godzinę przechowywane przez `CFileTime` obiekt.

```cpp
void SetTime(ULONGLONG nTime) throw();
```

### <a name="parameters"></a>Parametry

*nTime*<br/>
Wartość 64-bitowa reprezentująca datę i godzinę w formacie UTC (Local lub Coordinated Universal Time).

## <a name="cfiletimeutctolocal"></a><a name="utctolocal"></a> CFileTime::UTCToLocal

Wywołaj tę metodę, aby przekonwertować czas na podstawie uniwersalnego czasu koordynowanego (UTC) na czas pliku lokalnego.

```
CFileTime UTCToLocal() const throw();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca `CFileTime` obiekt zawierający godzinę w lokalnym formacie godziny pliku.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCFiles#42](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_4.cpp)]

## <a name="cfiletimeweek"></a><a name="week"></a> CFileTime:: tydzień

Statyczny element członkowski danych przechowujący liczbę interwałów 100-nanosekund, które składają się z jednego tygodnia.

```
static const ULONGLONG Week = Day* 7;
```

### <a name="example"></a>Przykład

Zobacz przykład dla [CFileTime:: milisekund](#millisecond).

## <a name="see-also"></a>Zobacz też

[FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime)<br/>
[Klasa CFileTimeSpan](../../atl-mfc-shared/reference/cfiletimespan-class.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy udostępnione ATL/MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)
