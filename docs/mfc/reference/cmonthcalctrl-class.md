---
description: 'Dowiedz się więcej na temat: Klasa CMonthCalCtrl'
title: Klasa CMonthCalCtrl
ms.date: 11/04/2016
f1_keywords:
- CMonthCalCtrl
- AFXDTCTL/CMonthCalCtrl
- AFXDTCTL/CMonthCalCtrl::CMonthCalCtrl
- AFXDTCTL/CMonthCalCtrl::Create
- AFXDTCTL/CMonthCalCtrl::GetCalendarBorder
- AFXDTCTL/CMonthCalCtrl::GetCalendarCount
- AFXDTCTL/CMonthCalCtrl::GetCalendarGridInfo
- AFXDTCTL/CMonthCalCtrl::GetCalID
- AFXDTCTL/CMonthCalCtrl::GetColor
- AFXDTCTL/CMonthCalCtrl::GetCurrentView
- AFXDTCTL/CMonthCalCtrl::GetCurSel
- AFXDTCTL/CMonthCalCtrl::GetFirstDayOfWeek
- AFXDTCTL/CMonthCalCtrl::GetMaxSelCount
- AFXDTCTL/CMonthCalCtrl::GetMaxTodayWidth
- AFXDTCTL/CMonthCalCtrl::GetMinReqRect
- AFXDTCTL/CMonthCalCtrl::GetMonthDelta
- AFXDTCTL/CMonthCalCtrl::GetMonthRange
- AFXDTCTL/CMonthCalCtrl::GetRange
- AFXDTCTL/CMonthCalCtrl::GetSelRange
- AFXDTCTL/CMonthCalCtrl::GetToday
- AFXDTCTL/CMonthCalCtrl::HitTest
- AFXDTCTL/CMonthCalCtrl::IsCenturyView
- AFXDTCTL/CMonthCalCtrl::IsDecadeView
- AFXDTCTL/CMonthCalCtrl::IsMonthView
- AFXDTCTL/CMonthCalCtrl::IsYearView
- AFXDTCTL/CMonthCalCtrl::SetCalendarBorder
- AFXDTCTL/CMonthCalCtrl::SetCalendarBorderDefault
- AFXDTCTL/CMonthCalCtrl::SetCalID
- AFXDTCTL/CMonthCalCtrl::SetCenturyView
- AFXDTCTL/CMonthCalCtrl::SetColor
- AFXDTCTL/CMonthCalCtrl::SetCurrentView
- AFXDTCTL/CMonthCalCtrl::SetCurSel
- AFXDTCTL/CMonthCalCtrl::SetDayState
- AFXDTCTL/CMonthCalCtrl::SetDecadeView
- AFXDTCTL/CMonthCalCtrl::SetFirstDayOfWeek
- AFXDTCTL/CMonthCalCtrl::SetMaxSelCount
- AFXDTCTL/CMonthCalCtrl::SetMonthDelta
- AFXDTCTL/CMonthCalCtrl::SetMonthView
- AFXDTCTL/CMonthCalCtrl::SetRange
- AFXDTCTL/CMonthCalCtrl::SetSelRange
- AFXDTCTL/CMonthCalCtrl::SetToday
- AFXDTCTL/CMonthCalCtrl::SetYearView
- AFXDTCTL/CMonthCalCtrl::SizeMinReq
- AFXDTCTL/CMonthCalCtrl::SizeRectToMin
helpviewer_keywords:
- CMonthCalCtrl [MFC], CMonthCalCtrl
- CMonthCalCtrl [MFC], Create
- CMonthCalCtrl [MFC], GetCalendarBorder
- CMonthCalCtrl [MFC], GetCalendarCount
- CMonthCalCtrl [MFC], GetCalendarGridInfo
- CMonthCalCtrl [MFC], GetCalID
- CMonthCalCtrl [MFC], GetColor
- CMonthCalCtrl [MFC], GetCurrentView
- CMonthCalCtrl [MFC], GetCurSel
- CMonthCalCtrl [MFC], GetFirstDayOfWeek
- CMonthCalCtrl [MFC], GetMaxSelCount
- CMonthCalCtrl [MFC], GetMaxTodayWidth
- CMonthCalCtrl [MFC], GetMinReqRect
- CMonthCalCtrl [MFC], GetMonthDelta
- CMonthCalCtrl [MFC], GetMonthRange
- CMonthCalCtrl [MFC], GetRange
- CMonthCalCtrl [MFC], GetSelRange
- CMonthCalCtrl [MFC], GetToday
- CMonthCalCtrl [MFC], HitTest
- CMonthCalCtrl [MFC], IsCenturyView
- CMonthCalCtrl [MFC], IsDecadeView
- CMonthCalCtrl [MFC], IsMonthView
- CMonthCalCtrl [MFC], IsYearView
- CMonthCalCtrl [MFC], SetCalendarBorder
- CMonthCalCtrl [MFC], SetCalendarBorderDefault
- CMonthCalCtrl [MFC], SetCalID
- CMonthCalCtrl [MFC], SetCenturyView
- CMonthCalCtrl [MFC], SetColor
- CMonthCalCtrl [MFC], SetCurrentView
- CMonthCalCtrl [MFC], SetCurSel
- CMonthCalCtrl [MFC], SetDayState
- CMonthCalCtrl [MFC], SetDecadeView
- CMonthCalCtrl [MFC], SetFirstDayOfWeek
- CMonthCalCtrl [MFC], SetMaxSelCount
- CMonthCalCtrl [MFC], SetMonthDelta
- CMonthCalCtrl [MFC], SetMonthView
- CMonthCalCtrl [MFC], SetRange
- CMonthCalCtrl [MFC], SetSelRange
- CMonthCalCtrl [MFC], SetToday
- CMonthCalCtrl [MFC], SetYearView
- CMonthCalCtrl [MFC], SizeMinReq
- CMonthCalCtrl [MFC], SizeRectToMin
ms.assetid: a42f6bd6-ab5c-4335-82f8-839982fc64a2
ms.openlocfilehash: 4c4c4684167a9c1c569f69f582688b294ac95233
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331598"
---
# <a name="cmonthcalctrl-class"></a>Klasa CMonthCalCtrl

Hermetyzuje funkcjonalność formantu kalendarza miesięcznego.

## <a name="syntax"></a>Składnia

```
class CMonthCalCtrl : public CWnd
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMonthCalCtrl:: CMonthCalCtrl](#cmonthcalctrl)|Konstruuje `CMonthCalCtrl` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMonthCalCtrl:: Create](#create)|Tworzy formant kalendarza miesięcznego i dołącza go do `CMonthCalCtrl` obiektu.|
|[CMonthCalCtrl:: GetCalendarBorder](#getcalendarborder)|Pobiera szerokość obramowania formantu kalendarza bieżącego miesiąca.|
|[CMonthCalCtrl:: GetCalendarCount](#getcalendarcount)|Pobiera liczbę kalendarzy wyświetlanych w formancie kalendarza bieżącego miesiąca.|
|[CMonthCalCtrl:: GetCalendarGridInfo](#getcalendargridinfo)|Pobiera informacje o formancie kalendarza bieżącego miesiąca.|
|[CMonthCalCtrl:: GetCalID](#getcalid)|Pobiera identyfikator kalendarza dla kontrolki kalendarza bieżącego miesiąca.|
|[CMonthCalCtrl:: GetColor](#getcolor)|Pobiera kolor określonego obszaru kontrolki kalendarza miesięcznego.|
|[CMonthCalCtrl:: GetCurrentView](#getcurrentview)|Pobiera widok, który jest aktualnie wyświetlany przez formant kalendarza bieżącego miesiąca.|
|[CMonthCalCtrl:: GetCurSel](#getcursel)|Pobiera czas systemowy wskazany przez aktualnie wybraną datę.|
|[CMonthCalCtrl:: getpierwszydzieńtygodnia](#getfirstdayofweek)|Pobiera pierwszy dzień tygodnia, który ma być wyświetlany w kolumnie z lewej strony kalendarza.|
|[CMonthCalCtrl:: GetMaxSelCount](#getmaxselcount)|Pobiera bieżącą maksymalną liczbę dni, którą można wybrać w kontrolce kalendarza miesięcznego.|
|[CMonthCalCtrl:: GetMaxTodayWidth](#getmaxtodaywidth)|Pobiera maksymalną szerokość ciągu "dzisiaj" dla kontrolki kalendarza bieżącego miesiąca.|
|[CMonthCalCtrl:: GetMinReqRect](#getminreqrect)|Pobiera minimalny rozmiar wymagany do wyświetlenia pełnego miesiąca w kontrolce kalendarza miesięcznego.|
|[CMonthCalCtrl:: GetMonthDelta](#getmonthdelta)|Pobiera szybkość przewijania dla kontrolki kalendarza miesięcznego.|
|[CMonthCalCtrl:: GetMonthRange](#getmonthrange)|Pobiera informacje o dacie reprezentujące górne i niskie limity wyświetlania kalendarza miesięcznego.|
|[CMonthCalCtrl:: GetRange](#getrange)|Pobiera aktualną minimalną i maksymalną datę ustawioną w kontrolce kalendarza miesięcznego.|
|[CMonthCalCtrl:: GetSelRange](#getselrange)|Pobiera informacje o dacie reprezentujące górne i dolne limity zakresu dat aktualnie wybranego przez użytkownika.|
|[CMonthCalCtrl:: getdzisiaj](#gettoday)|Pobiera informacje o dacie dla daty określonej jako "dzisiaj" dla kontrolki kalendarza miesięcznego.|
|[CMonthCalCtrl:: HitTest](#hittest)|Określa, która sekcja kontrolki kalendarza miesięcznego znajduje się w danym punkcie na ekranie.|
|[CMonthCalCtrl:: IsCenturyView](#iscenturyview)|Wskazuje, czy bieżącym widokiem formantu kalendarza bieżącego miesiąca jest widok wieku.|
|[CMonthCalCtrl:: IsDecadeView](#isdecadeview)|Wskazuje, czy bieżącym widokiem formantu kalendarza bieżącego miesiąca jest widok dekady.|
|[CMonthCalCtrl:: IsMonthView](#ismonthview)|Wskazuje, czy bieżącym widokiem formantu kalendarza bieżącego miesiąca jest widok miesiąca.|
|[CMonthCalCtrl:: IsYearView](#isyearview)|Wskazuje, czy bieżącym widokiem formantu kalendarza bieżącego miesiąca jest widok rok.|
|[CMonthCalCtrl:: SetCalendarBorder](#setcalendarborder)|Ustawia szerokość obramowania formantu kalendarza bieżącego miesiąca.|
|[CMonthCalCtrl:: SetCalendarBorderDefault](#setcalendarborderdefault)|Ustawia domyślną szerokość obramowania formantu kalendarza bieżącego miesiąca.|
|[CMonthCalCtrl:: SetCalID](#setcalid)|Ustawia identyfikator kalendarza dla kontrolki kalendarza bieżącego miesiąca.|
|[CMonthCalCtrl:: SetCenturyView](#setcenturyview)|Ustawia kontrolkę kalendarz bieżący miesiąc, aby wyświetlić widok wieku.|
|[CMonthCalCtrl:: SetColor](#setcolor)|Ustawia kolor określonego obszaru kontrolki kalendarza miesięcznego.|
|[CMonthCalCtrl:: SetCurrentView](#setcurrentview)|Ustawia formant kalendarza bieżącego miesiąca do wyświetlania określonego widoku.|
|[CMonthCalCtrl:: SetCurSel](#setcursel)|Ustawia aktualnie wybraną datę dla formantu kalendarza miesięcznego.|
|[CMonthCalCtrl:: SetDayState](#setdaystate)|Ustawia wyświetlaną liczbę dni w kontrolce kalendarza miesięcznego.|
|[CMonthCalCtrl:: SetDecadeView](#setdecadeview)|Ustawia formant kalendarza bieżącego miesiąca na widok dekady.|
|[CMonthCalCtrl:: setpierwszydzieńtygodnia](#setfirstdayofweek)|Ustawia dzień tygodnia, który ma być wyświetlany w kolumnie z lewej strony kalendarza.|
|[CMonthCalCtrl:: SetMaxSelCount](#setmaxselcount)|Ustawia maksymalną liczbę dni, które można wybrać w kontrolce kalendarza miesięcznego.|
|[CMonthCalCtrl:: SetMonthDelta](#setmonthdelta)|Ustawia szybkość przewijania dla kontrolki kalendarza miesięcznego.|
|[CMonthCalCtrl:: SetMonthView](#setmonthview)|Ustawia kontrolkę kalendarz bieżący miesiąc, aby wyświetlić widok miesiąca.|
|[CMonthCalCtrl:: SetRange](#setrange)|Ustawia minimalną i maksymalną dozwoloną liczbę dat dla kontrolki kalendarza miesięcznego.|
|[CMonthCalCtrl:: SetSelRange](#setselrange)|Ustawia zaznaczenie dla kontrolki kalendarza miesięcznego na dany zakres dat.|
|[CMonthCalCtrl:: settoday](#settoday)|Ustawia kontrolkę Calendar dla bieżącego dnia.|
|[CMonthCalCtrl:: SetYearView](#setyearview)|Ustawia bieżącą kontrolkę kalendarza miesięcznego na rok.|
|[CMonthCalCtrl:: SizeMinReq](#sizeminreq)|Odmaluje kontrolkę Kalendarz miesięczny na minimalny, miesięczny rozmiar.|
|[CMonthCalCtrl:: SizeRectToMin](#sizerecttomin)|W przypadku formantu kalendarza bieżącego miesiąca program oblicza najmniejszy prostokąt, który może zawierać wszystkie kalendarze mieszczące się w określonym prostokącie.|

## <a name="remarks"></a>Uwagi

Formant kalendarza miesięcznego udostępnia użytkownikowi prosty interfejs kalendarza, z którego użytkownik może wybrać datę. Użytkownik może zmienić ekran:

- Przewijaj do tyłu i do przodu, od miesiąca do miesiąca.

- Kliknij tekst dzisiaj, aby wyświetlić bieżący dzień (jeśli styl MCS_NOTODAY nie jest używany).

- Pobranie miesiąca lub roku z menu podręcznego.

Kontrolkę kalendarza miesięcznego można dostosować, stosując wiele stylów do obiektu podczas jego tworzenia. Te style są opisane w [stylu kontrolki kalendarza miesięcznego](/windows/win32/Controls/month-calendar-control-styles) w Windows SDK.

Formant kalendarza miesięcznego może wyświetlać więcej niż jeden miesiąc i może wskazywać na dni specjalne (na przykład dni wolne) pogrubioną datę.

Aby uzyskać więcej informacji na temat używania kontrolki kalendarza miesięcznego, zobacz [using CMonthCalCtrl](../../mfc/using-cmonthcalctrl.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CMonthCalCtrl`

## <a name="requirements"></a>Wymagania

**Nagłówek:** AFXDTCTL. h

## <a name="cmonthcalctrlcmonthcalctrl"></a><a name="cmonthcalctrl"></a> CMonthCalCtrl:: CMonthCalCtrl

Konstruuje `CMonthCalCtrl` obiekt.

```
CMonthCalCtrl();
```

### <a name="remarks"></a>Uwagi

Należy wywołać `Create` po utworzeniu obiektu.

## <a name="cmonthcalctrlcreate"></a><a name="create"></a> CMonthCalCtrl:: Create

Tworzy formant kalendarza miesięcznego i dołącza go do `CMonthCalCtrl` obiektu.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);

virtual BOOL Create(
    DWORD dwStyle,
    const POINT& pt,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametry

*dwStyle*<br/>
Określa kombinację stylów systemu Windows stosowanych do kontrolki kalendarza miesięcznego. Aby uzyskać więcej informacji na temat stylów, zobacz [Style kontrolek kalendarza miesięcznego](/windows/win32/Controls/month-calendar-control-styles) w Windows SDK.

*cinania*<br/>
Odwołanie do struktury [prostokąta](/windows/win32/api/windef/ns-windef-rect) . Zawiera położenie i rozmiar kontrolki kalendarza miesięcznego.

*zmiennoprzecinkow*<br/>
Odwołanie do struktury [punktu](/windows/win32/api/windef/ns-windef-point) , która identyfikuje lokalizację kontrolki kalendarza miesięcznego.

*pParentWnd*<br/>
Wskaźnik do obiektu [CWnd](../../mfc/reference/cwnd-class.md) , który jest oknem nadrzędnym formantu kalendarza miesięcznego. Nie może mieć wartości NULL.

*nID*<br/>
Określa identyfikator formantu kalendarza miesięcznego.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli Inicjalizacja zakończyła się pomyślnie; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Utwórz kontrolkę kalendarza miesięcznego w dwóch krokach:

1. Wywołaj [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md) w celu skonstruowania `CMonthCalCtrl` obiektu.

1. Wywołaj tę funkcję elementu członkowskiego, która tworzy formant kalendarza miesięcznego i dołącza go do `CMonthCalCtrl` obiektu.

Po wywołaniu `Create` , są inicjowane typowe formanty. Wersja `Create` wywołania określa, jak ma rozmiar:

- Aby MFC automatycznie zmieniać rozmiar kontrolki na jeden miesiąc, wywołaj przesłonięcie, które używa parametru *pt* .

- Aby samodzielnie zmienić rozmiar kontrolki, wywołaj przesłonięcie tej funkcji, która używa parametru *Rect* .

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFC_CMonthCalCtrl#1](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_1.cpp)]

## <a name="cmonthcalctrlgetcalendarborder"></a><a name="getcalendarborder"></a> CMonthCalCtrl:: GetCalendarBorder

Pobiera szerokość obramowania formantu kalendarza bieżącego miesiąca.

```
int GetCalendarBorder() const;
```

### <a name="return-value"></a>Wartość zwracana

Szerokość obramowania formantu (w pikselach).

### <a name="remarks"></a>Uwagi

Ta metoda wysyła komunikat [MCM_GETCALENDARBORDER](/windows/win32/Controls/mcm-getcalendarborder) , który jest opisany w Windows SDK.

## <a name="cmonthcalctrlgetcalendarcount"></a><a name="getcalendarcount"></a> CMonthCalCtrl:: GetCalendarCount

Pobiera liczbę kalendarzy wyświetlanych w formancie kalendarza bieżącego miesiąca.

```
int GetCalendarCount() const;
```

### <a name="return-value"></a>Wartość zwracana

Liczba kalendarzy aktualnie wyświetlanych w kontrolce kalendarza miesięcznego. Maksymalna dozwolona liczba kalendarzy to 12.

### <a name="remarks"></a>Uwagi

Ta metoda wysyła komunikat [MCM_GETCALENDARCOUNT](/windows/win32/Controls/mcm-getcalendarcount) , który jest opisany w Windows SDK.

## <a name="cmonthcalctrlgetcalendargridinfo"></a><a name="getcalendargridinfo"></a> CMonthCalCtrl:: GetCalendarGridInfo

Pobiera informacje o formancie kalendarza bieżącego miesiąca.

```
BOOL GetCalendarGridInfo(PMCGRIDINFO pmcGridInfo) const;
```

### <a name="parameters"></a>Parametry

*pmcGridInfo*\
określoną Wskaźnik na strukturę [MCGRIDINFO](/windows/win32/api/commctrl/ns-commctrl-mcgridinfo) , która otrzymuje informacje o formancie kalendarza bieżącego miesiąca. Obiekt wywołujący jest odpowiedzialny za przydzielanie i Inicjowanie tej struktury.

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli ta metoda zakończyła się pomyślnie; w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

Ta metoda wysyła komunikat [MCM_GETCALENDARGRIDINFO](/windows/win32/Controls/mcm-getcalendargridinfo) , który jest opisany w Windows SDK.

### <a name="example"></a>Przykład

Poniższy przykład kodu definiuje zmienną, `m_monthCalCtrl` , która jest używana do programistycznego dostępu do kontrolki kalendarza miesięcznego. Ta zmienna jest używana w następnym przykładzie.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>Przykład

Poniższy przykład kodu używa `GetCalendarGridInfo` metody do pobierania daty kalendarzowej wyświetlanej przez formant kalendarza bieżącego miesiąca.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#3](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_3.cpp)]

## <a name="cmonthcalctrlgetcalid"></a><a name="getcalid"></a> CMonthCalCtrl:: GetCalID

Pobiera identyfikator kalendarza dla kontrolki kalendarza bieżącego miesiąca.

```
CALID GetCalID() const;
```

### <a name="return-value"></a>Wartość zwracana

Jedna z stałych [identyfikatora kalendarza](/windows/win32/Intl/calendar-identifiers) .

### <a name="remarks"></a>Uwagi

Identyfikator kalendarza oznacza kalendarz specyficzny dla regionu, taki jak kalendarz gregoriański (zlokalizowany), japoński lub Hidżry. Aplikacja może używać identyfikatora kalendarza, który ma różne funkcje obsługi języka.

Ta metoda wysyła komunikat [MCM_GETCALID](/windows/win32/Controls/mcm-getcalid) , który jest opisany w Windows SDK.

## <a name="cmonthcalctrlgetcolor"></a><a name="getcolor"></a> CMonthCalCtrl:: GetColor

Pobiera kolor obszaru kontrolki kalendarza miesięcznego określonego przez *nRegion*.

```
COLORREF GetColor(int nRegion) const;
```

### <a name="parameters"></a>Parametry

*nRegion*<br/>
Region formantu kalendarza miesięcznego, z którego pobierany jest kolor. Aby uzyskać listę wartości, zobacz *nRegion* parametru [SetColor](#setcolor).

### <a name="return-value"></a>Wartość zwracana

Wartość [COLORREF](/windows/win32/gdi/colorref) określająca kolor skojarzony z częścią kontrolki kalendarza miesięcznego, jeśli zakończyła się pomyślnie. W przeciwnym razie ta funkcja członkowska zwraca wartość-1.

## <a name="cmonthcalctrlgetcurrentview"></a><a name="getcurrentview"></a> CMonthCalCtrl:: GetCurrentView

Pobiera widok, który jest aktualnie wyświetlany przez formant kalendarza bieżącego miesiąca.

```
DWORD GetCurrentView() const;
```

### <a name="return-value"></a>Wartość zwracana

Bieżący widok, który jest wskazywany przez jedną z następujących wartości:

|Wartość|Znaczenie|
|-----------|-------------|
|MCMV_MONTH|Widok miesięczny|
|MCMV_YEAR|Widok roczny|
|MCMV_DECADE|Widok dekady|
|MCMV_CENTURY|Widok wieku|

### <a name="remarks"></a>Uwagi

Ta metoda wysyła komunikat [MCM_GETCURRENTVIEW](/windows/win32/Controls/mcm-getcurrentview) , który jest opisany w Windows SDK.

### <a name="example"></a>Przykład

Poniższy przykład kodu definiuje zmienną, `m_monthCalCtrl` , która jest używana do programistycznego dostępu do kontrolki kalendarza miesięcznego. Ta zmienna jest używana w następnym przykładzie.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>Przykład

Poniższy przykładowy kod przedstawia raporty, które są wyświetlane w widoku kalendarza miesięcznego.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#7](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_4.cpp)]

## <a name="cmonthcalctrlgetcursel"></a><a name="getcursel"></a> CMonthCalCtrl:: GetCurSel

Pobiera czas systemowy wskazany przez aktualnie wybraną datę.

```
BOOL GetCurSel(COleDateTime& refDateTime) const;  BOOL GetCurSel(CTime& refDateTime) const;

BOOL GetCurSel(LPSYSTEMTIME pDateTime) const;
```

### <a name="parameters"></a>Parametry

*refDateTime*<br/>
Odwołanie do obiektu [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) lub obiektu [CTime](../../atl-mfc-shared/reference/ctime-class.md) . Odbiera bieżącą godzinę.

*pDateTime*<br/>
Wskaźnik do struktury [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) , który otrzyma aktualnie wybrane informacje o dacie. Ten parametr musi być prawidłowym adresem i nie może mieć wartości NULL.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; otherwize 0.

### <a name="remarks"></a>Uwagi

Ta funkcja członkowska implementuje zachowanie [MCM_GETCURSEL](/windows/win32/Controls/mcm-getcursel)komunikatu Win32, zgodnie z opisem w Windows SDK.

> [!NOTE]
> Ta funkcja członkowska kończy się niepowodzeniem, jeśli ustawiono MCS_MULTISELECT stylu.

W implementacji MFC `GetCurSel` , można określić użycie, użycie `COleDateTime` `CTime` lub `SYSTEMTIME` strukturę użycie.

## <a name="cmonthcalctrlgetfirstdayofweek"></a><a name="getfirstdayofweek"></a> CMonthCalCtrl:: getpierwszydzieńtygodnia

Pobiera pierwszy dzień tygodnia, który ma być wyświetlany w kolumnie z lewej strony kalendarza.

```
int GetFirstDayOfWeek(BOOL* pbLocal = NULL) const;
```

### <a name="parameters"></a>Parametry

*pbLocal*<br/>
Wskaźnik do wartości LOGICZNEj. Jeśli wartość jest różna od zera, ustawienie kontrolki nie jest zgodne z ustawieniem w panelu sterowania.

### <a name="return-value"></a>Wartość zwracana

Wartość całkowita reprezentująca pierwszy dzień tygodnia. Zobacz **uwagi** , aby uzyskać więcej informacji na temat tego, co reprezentuje te liczby całkowite.

### <a name="remarks"></a>Uwagi

Ta funkcja członkowska implementuje zachowanie [MCM_GETFIRSTDAYOFWEEK](/windows/win32/Controls/mcm-getfirstdayofweek)komunikatu Win32, zgodnie z opisem w Windows SDK. Dni tygodnia są reprezentowane jako liczby całkowite w następujący sposób.

|Wartość|Dzień tygodnia|
|-----------|---------------------|
|0|Monday|
|1|Tuesday|
|2|Środa|
|3|Thursday|
|4|Piątek|
|5|Sobota|
|6|Niedziela|

### <a name="example"></a>Przykład

  Zobacz przykład dla [CMonthCalCtrl:: setpierwszydzieńtygodnia](#setfirstdayofweek).

## <a name="cmonthcalctrlgetmaxselcount"></a><a name="getmaxselcount"></a> CMonthCalCtrl:: GetMaxSelCount

Pobiera bieżącą maksymalną liczbę dni, którą można wybrać w kontrolce kalendarza miesięcznego.

```
int GetMaxSelCount() const;
```

### <a name="return-value"></a>Wartość zwracana

Wartość całkowita reprezentująca łączną liczbę dni, które można wybrać dla kontrolki.

### <a name="remarks"></a>Uwagi

Ta funkcja członkowska implementuje zachowanie [MCM_GETMAXSELCOUNT](/windows/win32/Controls/mcm-getmaxselcount)komunikatu Win32, zgodnie z opisem w Windows SDK. Użyj tej funkcji elementu członkowskiego dla kontrolek z zestawem stylów MCS_MULTISELECT.

### <a name="example"></a>Przykład

  Zobacz przykład dla [CMonthCalCtrl:: SetMaxSelCount](#setmaxselcount).

## <a name="cmonthcalctrlgetmaxtodaywidth"></a><a name="getmaxtodaywidth"></a> CMonthCalCtrl:: GetMaxTodayWidth

Pobiera maksymalną szerokość ciągu "dzisiaj" dla kontrolki kalendarza bieżącego miesiąca.

```
DWORD GetMaxTodayWidth() const;
```

### <a name="return-value"></a>Wartość zwracana

Szerokość ciągu "dzisiaj" (w pikselach).

### <a name="example"></a>Przykład

Poniższy przykład kodu definiuje zmienną, `m_monthCalCtrl` , która jest używana do programistycznego dostępu do kontrolki kalendarza miesięcznego. Ta zmienna jest używana w następnym przykładzie.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>Przykład

Poniższy przykład kodu demonstruje `GetMaxTodayWidth` metodę.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_5.cpp)]

### <a name="remarks"></a>Uwagi

Użytkownik może wrócić do bieżącej daty, klikając ciąg "dzisiaj", który jest wyświetlany w dolnej części kontrolki kalendarza miesięcznego. Ciąg "Today" zawiera tekst etykiety i tekst daty.

Ta metoda wysyła komunikat [MCM_GETMAXTODAYWIDTH](/windows/win32/Controls/mcm-getmaxtodaywidth) , który jest opisany w Windows SDK.

## <a name="cmonthcalctrlgetminreqrect"></a><a name="getminreqrect"></a> CMonthCalCtrl:: GetMinReqRect

Pobiera minimalny rozmiar wymagany do wyświetlenia pełnego miesiąca w kontrolce kalendarza miesięcznego.

```
BOOL GetMinReqRect(RECT* pRect) const;
```

### <a name="parameters"></a>Parametry

*pRect*<br/>
Wskaźnik do struktury [Rect](/windows/win32/api/windef/ns-windef-rect) , który będzie odbierać informacje o prostokątach powiązanych. Ten parametr musi być prawidłowym adresem i nie może mieć wartości NULL.

### <a name="return-value"></a>Wartość zwracana

Jeśli to się powiedzie, ta funkcja członkowska zwraca wartość różną od zera i `lpRect` otrzymuje odpowiednie powiązane informacje. Jeśli to się nie powiedzie, funkcja członkowska zwróci wartość 0.

### <a name="remarks"></a>Uwagi

Ta funkcja członkowska implementuje zachowanie [MCM_GETMINREQRECT](/windows/win32/Controls/mcm-getminreqrect)komunikatu Win32, zgodnie z opisem w Windows SDK.

## <a name="cmonthcalctrlgetmonthdelta"></a><a name="getmonthdelta"></a> CMonthCalCtrl:: GetMonthDelta

Pobiera szybkość przewijania dla kontrolki kalendarza miesięcznego.

```
int GetMonthDelta() const;
```

### <a name="return-value"></a>Wartość zwracana

Szybkość przewijania dla kontrolki kalendarza miesięcznego. Szybkość przewijania to liczba miesięcy, przez jaką formant przesuwa swój ekran, gdy użytkownik kliknie przycisk przewijania jeden raz.

### <a name="remarks"></a>Uwagi

Ta funkcja członkowska implementuje zachowanie [MCM_GETMONTHDELTA](/windows/win32/Controls/mcm-getmonthdelta)komunikatu Win32, zgodnie z opisem w Windows SDK.

## <a name="cmonthcalctrlgetmonthrange"></a><a name="getmonthrange"></a> CMonthCalCtrl:: GetMonthRange

Pobiera informacje o dacie reprezentujące górne i niskie limity wyświetlania kalendarza miesięcznego.

```
int GetMonthRange(
    COleDateTime& refMinRange,
    COleDateTime& refMaxRange,
    DWORD dwFlags) const;

int GetMonthRange(
    CTime& refMinRange,
    CTime& refMaxRange,
    DWORD dwFlags) const;

int GetMonthRange(
    LPSYSTEMTIME pMinRange,
    LPSYSTEMTIME pMaxRange,
    DWORD dwFlags) const;
```

### <a name="parameters"></a>Parametry

*refMinRange*<br/>
Odwołanie do obiektu [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) lub [CTime](../../atl-mfc-shared/reference/ctime-class.md) zawierającego minimalną dozwoloną datę.

*refMaxRange*<br/>
Odwołanie do `COleDateTime` lub `CTime` obiekt zawierający maksymalną dozwoloną datę.

*pMinRange*<br/>
Wskaźnik do struktury [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) zawierającej datę na najniższym końcu zakresu.

*pMaxRange*<br/>
Wskaźnik do `SYSTEMTIME` struktury zawierającej datę z najwyższego końca zakresu.

*flagiDW*<br/>
Wartość określająca zakres limitów zakresu do pobrania. Ta wartość musi być jedną z następujących wartości.

|Wartość|Znaczenie|
|-----------|-------------|
|GMR_DAYSTATE|Uwzględnij poprzednie i końcowe miesiące widocznego zakresu, które są tylko częściowo wyświetlane.|
|GMR_VISIBLE|Uwzględnij tylko te miesiące, które są wyświetlane w całości.|

### <a name="return-value"></a>Wartość zwracana

Liczba całkowita reprezentująca zakres w miesiącach, w której łączone są dwa limity wskazywane przez *refMinRange* i *refMaxRange* w pierwszej i drugiej wersji, lub *pMinRange* i *pMaxRange* w trzeciej wersji.

### <a name="remarks"></a>Uwagi

Ta funkcja członkowska implementuje zachowanie [MCM_GETMONTHRANGE](/windows/win32/Controls/mcm-getmonthrange)komunikatu Win32, zgodnie z opisem w Windows SDK. W implementacji MFC `GetMonthRange` , można określić użycie, użycie `COleDateTime` `CTime` lub `SYSTEMTIME` użycie struktury.

### <a name="example"></a>Przykład

  Zobacz przykład dla [CMonthCalCtrl:: SetDayState](#setdaystate).

## <a name="cmonthcalctrlgetrange"></a><a name="getrange"></a> CMonthCalCtrl:: GetRange

Pobiera aktualną minimalną i maksymalną datę ustawioną w kontrolce kalendarza miesięcznego.

```
DWORD GetRange(
    COleDateTime* pMinRange,
    COleDateTime* pMaxRange) const;

DWORD GetRange(
    CTime* pMinRange,
    CTime* pMaxRange) const;

DWORD GetRange(
    LPSYSTEMTIME pMinRange,
    LPSYSTEMTIME pMaxRange) const;
```

### <a name="parameters"></a>Parametry

*pMinRange*<br/>
Wskaźnik do `COleDateTime` obiektu, `CTime` obiektu lub struktury [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) zawierającej datę na najniższym końcu zakresu.

*pMaxRange*<br/>
Wskaźnik do `COleDateTime` obiektu, `CTime` obiektu lub struktury [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) zawierającej datę z najwyższego końca zakresu.

### <a name="return-value"></a>Wartość zwracana

Wartość DWORD, która może być równa zero (nie są ustawione limity) lub kombinacja następujących wartości, które określają informacje o limicie.

|Wartość|Znaczenie|
|-----------|-------------|
|GDTR_MAX|Ustawiony jest limit maksymalny dla kontrolki; *pMaxRange* jest prawidłowy i zawiera informacje o odpowiednim dniu.|
|GDTR_MIN|Ustawiony jest minimalny limit dla kontrolki; *pMinRange* jest prawidłowy i zawiera informacje o odpowiednim dniu.|

### <a name="remarks"></a>Uwagi

Ta funkcja członkowska implementuje zachowanie [MCM_GETRANGE](/windows/win32/Controls/mcm-getrange)komunikatu Win32, zgodnie z opisem w Windows SDK. W implementacji MFC `GetRange` , można określić użycie, użycie `COleDateTime` `CTime` lub `SYSTEMTIME` strukturę użycie.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFC_CMonthCalCtrl#2](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_6.cpp)]

## <a name="cmonthcalctrlgetselrange"></a><a name="getselrange"></a> CMonthCalCtrl:: GetSelRange

Pobiera informacje o dacie reprezentujące górne i dolne limity zakresu dat aktualnie wybranego przez użytkownika.

```
BOOL GetSelRange(
    COleDateTime& refMinRange,
    COleDateTime& refMaxRange) const;

BOOL GetSelRange(
    CTime& refMinRange,
    CTime& refMaxRange) const;

BOOL GetSelRange(
    LPSYSTEMTIME pMinRange,
    LPSYSTEMTIME pMaxRange) const;
```

### <a name="parameters"></a>Parametry

*refMinRange*<br/>
Odwołanie do obiektu [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) lub [CTime](../../atl-mfc-shared/reference/ctime-class.md) zawierającego minimalną dozwoloną datę.

*refMaxRange*<br/>
Odwołanie do `COleDateTime` lub `CTime` obiekt zawierający maksymalną dozwoloną datę.

*pMinRange*<br/>
Wskaźnik do struktury [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) zawierającej datę na najniższym końcu zakresu.

*pMaxRange*<br/>
Wskaźnik do `SYSTEMTIME` struktury zawierającej datę z najwyższego końca zakresu.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Ta funkcja członkowska implementuje zachowanie [MCM_GETSELRANGE](/windows/win32/Controls/mcm-getselrange)komunikatu Win32, zgodnie z opisem w Windows SDK. `GetSelRange` nie powiedzie się w przypadku zastosowania do kontrolki kalendarza miesięcznego, która nie używa stylu MCS_MULTISELECT.

W implementacji MFC `GetSelRange` , można określić użycie, użycie `COleDateTime` `CTime` lub `SYSTEMTIME` użycie struktury.

## <a name="cmonthcalctrlgettoday"></a><a name="gettoday"></a> CMonthCalCtrl:: getdzisiaj

Pobiera informacje o dacie dla daty określonej jako "dzisiaj" dla kontrolki kalendarza miesięcznego.

```
BOOL GetToday(COleDateTime& refDateTime) const;  BOOL GetToday(COleDateTime& refDateTime) const;

BOOL GetToday(LPSYSTEMTIME pDateTime) const;
```

### <a name="parameters"></a>Parametry

*refDateTime*<br/>
Odwołanie do obiektu [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) lub [CTime](../../atl-mfc-shared/reference/ctime-class.md) wskazujące bieżący dzień.

*pDateTime*<br/>
Wskaźnik do struktury [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) , która będzie otrzymywać informacje o dacie. Ten parametr musi być prawidłowym adresem i nie może mieć wartości NULL.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Ta funkcja członkowska implementuje zachowanie [MCM_GETTODAY](/windows/win32/Controls/mcm-gettoday)komunikatu Win32, zgodnie z opisem w Windows SDK. W implementacji MFC `GetToday` , można określić użycie, użycie `COleDateTime` `CTime` lub `SYSTEMTIME` strukturę użycie.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFC_CMonthCalCtrl#3](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_7.cpp)]

## <a name="cmonthcalctrlhittest"></a><a name="hittest"></a> CMonthCalCtrl:: HitTest

Określa, który formant kalendarza miesięcznego (jeśli istnieje) znajduje się na określonej pozycji.

```
DWORD HitTest(PMCHITTESTINFO pMCHitTest);
```

### <a name="parameters"></a>Parametry

*pMCHitTest*<br/>
Wskaźnik do struktury [MCHITTESTINFO](/windows/win32/api/commctrl/ns-commctrl-mchittestinfo) zawierający punkty testów trafień dla kontrolki kalendarza miesięcznego.

### <a name="return-value"></a>Wartość zwracana

Wartość typu DWORD. Równy elementowi członkowskiemu **uHit** `MCHITTESTINFO` struktury.

### <a name="remarks"></a>Uwagi

`HitTest` używa `MCHITTESTINFO` struktury, która zawiera informacje o teście trafień.

## <a name="cmonthcalctrliscenturyview"></a><a name="iscenturyview"></a> CMonthCalCtrl:: IsCenturyView

Wskazuje, czy bieżącym widokiem formantu kalendarza bieżącego miesiąca jest widok wieku.

```
BOOL IsCenturyView() const;
```

### <a name="return-value"></a>Wartość zwracana

TRUE, jeśli bieżący widok jest widokiem Century; w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

Ta metoda wysyła komunikat [MCM_GETCURRENTVIEW](/windows/win32/Controls/mcm-getcurrentview) , który jest opisany w Windows SDK. Jeśli ten komunikat zwróci MCMV_CENTURY, metoda zwraca wartość TRUE.

## <a name="cmonthcalctrlisdecadeview"></a><a name="isdecadeview"></a> CMonthCalCtrl:: IsDecadeView

Wskazuje, czy bieżącym widokiem formantu kalendarza bieżącego miesiąca jest widok dekady.

```
BOOL IsDecadeView() const;
```

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli bieżący widok jest widokiem dekady; w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

Ta metoda wysyła komunikat [MCM_GETCURRENTVIEW](/windows/win32/Controls/mcm-getcurrentview) , który jest opisany w Windows SDK. Jeśli ten komunikat zwróci MCMV_DECADE, metoda zwraca wartość TRUE.

## <a name="cmonthcalctrlismonthview"></a><a name="ismonthview"></a> CMonthCalCtrl:: IsMonthView

Wskazuje, czy bieżącym widokiem formantu kalendarza bieżącego miesiąca jest widok miesiąca.

```
BOOL IsMonthView() const;
```

### <a name="return-value"></a>Wartość zwracana

Ma wartość TRUE, jeśli bieżący widok jest widokiem miesiąca. w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

Ta metoda wysyła komunikat [MCM_GETCURRENTVIEW](/windows/win32/Controls/mcm-getcurrentview) , który jest opisany w Windows SDK. Jeśli ten komunikat zwróci MCMV_MONTH, metoda zwraca wartość TRUE.

## <a name="cmonthcalctrlisyearview"></a><a name="isyearview"></a> CMonthCalCtrl:: IsYearView

Wskazuje, czy bieżącym widokiem formantu kalendarza bieżącego miesiąca jest widok rok.

```
BOOL IsYearView() const;
```

### <a name="return-value"></a>Wartość zwracana

Ma wartość TRUE, jeśli bieżący widok jest widokiem Year; w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

Ta metoda wysyła komunikat [MCM_GETCURRENTVIEW](/windows/win32/Controls/mcm-getcurrentview) , który jest opisany w Windows SDK. Jeśli ten komunikat zwróci MCMV_YEAR, metoda zwraca wartość TRUE.

## <a name="cmonthcalctrlsetcalendarborder"></a><a name="setcalendarborder"></a> CMonthCalCtrl:: SetCalendarBorder

Ustawia szerokość obramowania formantu kalendarza bieżącego miesiąca.

```cpp
void SetCalendarBorder(int cxyBorder);
```

### <a name="parameters"></a>Parametry

*cxyBorder*\
podczas Szerokość obramowania (w pikselach).

### <a name="remarks"></a>Uwagi

Jeśli ta metoda zakończy się powodzeniem, Szerokość obramowania jest ustawiana na parametr *cxyBorder* . W przeciwnym razie szerokość obramowania jest resetowana do wartości domyślnej, która jest określona przez bieżący [motyw](/windows/win32/Controls/visual-styles-overview), lub zero, jeśli motywy nie są używane.

Ta metoda wysyła komunikat [MCM_SETCALENDARBORDER](/windows/win32/Controls/mcm-setcalendarborder) , który jest opisany w Windows SDK.

### <a name="example"></a>Przykład

Poniższy przykład kodu definiuje zmienną, `m_monthCalCtrl` , która jest używana do programistycznego dostępu do kontrolki kalendarza miesięcznego. Ta zmienna jest używana w następnym przykładzie.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>Przykład

Poniższy przykład kodu ustawia szerokość obramowania kontrolki kalendarza miesięcznego na osiem pikseli. Użyj metody [CMonthCalCtrl:: GetCalendarBorder](#getcalendarborder) , aby określić, czy ta metoda zakończyła się pomyślnie.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#6](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_8.cpp)]

## <a name="cmonthcalctrlsetcalendarborderdefault"></a><a name="setcalendarborderdefault"></a> CMonthCalCtrl:: SetCalendarBorderDefault

Ustawia domyślną szerokość obramowania formantu kalendarza bieżącego miesiąca.

```cpp
void SetCalendarBorderDefault();
```

### <a name="remarks"></a>Uwagi

Szerokość obramowania jest ustawiona na wartość domyślną określoną przez bieżący [motyw](/windows/win32/Controls/visual-styles-overview)lub zero, jeśli motywy nie są używane.

Ta metoda wysyła komunikat [MCM_SETCALENDARBORDER](/windows/win32/Controls/mcm-setcalendarborder) , który jest opisany w Windows SDK.

## <a name="cmonthcalctrlsetcalid"></a><a name="setcalid"></a> CMonthCalCtrl:: SetCalID

Ustawia identyfikator kalendarza dla kontrolki kalendarza bieżącego miesiąca.

```
BOOL SetCalID(CALID calid);
```

### <a name="parameters"></a>Parametry

*calid*\
podczas Jedna z stałych [identyfikatora kalendarza](/windows/win32/Intl/calendar-identifiers) .

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli ta metoda zakończyła się pomyślnie; w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

Identyfikator kalendarza określa kalendarz specyficzny dla regionu, taki jak kalendarz gregoriański (zlokalizowany), japoński lub Hidżry. Użyj `SetCalID` metody, aby wyświetlić kalendarz, który jest określony przez *calid* parametru, jeśli ustawienia regionalne zawierające Kalendarz są zainstalowane na komputerze.

Ta metoda wysyła komunikat [MCM_SETCALID](/windows/win32/Controls/mcm-setcalid) , który jest opisany w Windows SDK.

### <a name="example"></a>Przykład

Poniższy przykład kodu definiuje zmienną, `m_monthCalCtrl` , która jest używana do programistycznego dostępu do kontrolki kalendarza miesięcznego. Ta zmienna jest używana w następnym przykładzie.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>Przykład

Poniższy przykład kodu ustawia formant kalendarza miesięcznego, aby wyświetlić Japoński kalendarz ery Imperatora ERA. `SetCalID`Metoda powiedzie się tylko wtedy, gdy ten kalendarz jest zainstalowany na komputerze.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#4](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_9.cpp)]

## <a name="cmonthcalctrlsetcenturyview"></a><a name="setcenturyview"></a> CMonthCalCtrl:: SetCenturyView

Ustawia kontrolkę kalendarz bieżący miesiąc, aby wyświetlić widok wieku.

```
BOOL SetCenturyView();
```

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli ta metoda zakończyła się pomyślnie; w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

Ta metoda używa metody [CMonthCalCtrl:: SetCurrentView](#setcurrentview) do ustawiania widoku na `MCMV_CENTURY` , który reprezentuje widok wieku.

## <a name="cmonthcalctrlsetcolor"></a><a name="setcolor"></a> CMonthCalCtrl:: SetColor

Ustawia kolor określonego obszaru kontrolki kalendarza miesięcznego.

```
COLORREF SetColor(
    int nRegion,
    COLORREF ref);
```

### <a name="parameters"></a>Parametry

*nRegion*<br/>
Wartość całkowita określająca, który kolor kalendarza ma zostać ustawiony. Może to być jedna z następujących wartości.

|Wartość|Znaczenie|
|-----------|-------------|
|MCSC_BACKGROUND|Kolor tła wyświetlany między miesiącami.|
|MCSC_MONTHBK|Kolor tła wyświetlany w miesiącu.|
|MCSC_TEXT|Kolor używany do wyświetlania tekstu w ciągu miesiąca.|
|MCSC_TITLEBK|Kolor tła wyświetlany w tytule kalendarza.|
|MCSC_TITLETEXT|Kolor używany do wyświetlania tekstu w tytule kalendarza.|
|MCSC_TRAILINGTEXT|Kolor używany do wyświetlania nagłówka i końcowego tekstu. Dni nagłówka i końcowe są dni od poprzedniego i następnego miesiąca, które są wyświetlane w bieżącym kalendarzu.|

*ref*<br/>
Wartość COLORREF dla nowego ustawienia koloru dla określonej części kontrolki kalendarza miesięcznego.

### <a name="return-value"></a>Wartość zwracana

Wartość COLORREF, która reprezentuje poprzednie ustawienie koloru dla określonej części kontrolki kalendarza miesięcznego, jeśli to się powiedzie. W przeciwnym razie ten komunikat zwróci wartość-1.

### <a name="remarks"></a>Uwagi

Ta funkcja członkowska implementuje zachowanie [MCM_SETCOLOR](/windows/win32/Controls/mcm-setcolor)komunikatu Win32, zgodnie z opisem w Windows SDK.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFC_CMonthCalCtrl#4](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_10.cpp)]

## <a name="cmonthcalctrlsetcurrentview"></a><a name="setcurrentview"></a> CMonthCalCtrl:: SetCurrentView

Ustawia formant kalendarza bieżącego miesiąca do wyświetlania określonego widoku.

```
BOOL SetCurrentView(DWORD dwNewView);
```

### <a name="parameters"></a>Parametry

*dwNewView*\
podczas Jedna z następujących wartości, która określa miesięczny, roczny, dekadę lub Century widoku.

- `MCMV_MONTH`: Widok miesięczny
- `MCMV_YEAR`: Widok roczny
- `MCMV_DECADE`: Widok dekady
- `MCMV_CENTURY`: Century — widok

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli ta metoda zakończyła się pomyślnie; w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

Ta metoda wysyła komunikat [MCM_SETCURRENTVIEW](/windows/win32/Controls/mcm-setcurrentview) , który jest opisany w Windows SDK.

## <a name="cmonthcalctrlsetcursel"></a><a name="setcursel"></a> CMonthCalCtrl:: SetCurSel

Ustawia aktualnie wybraną datę dla formantu kalendarza miesięcznego.

```
BOOL SetCurSel(const COleDateTime& refDateTime);
BOOL SetCurSel(const CTime& refDateTime);
BOOL SetCurSel(const LPSYSTEMTIME pDateTime);
```

### <a name="parameters"></a>Parametry

*refDateTime*<br/>
Odwołanie do obiektu [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) lub [CTime](../../atl-mfc-shared/reference/ctime-class.md) wskazującego aktualnie wybrany formant kalendarza miesięcznego.

*pDateTime*<br/>
Wskaźnik do struktury [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) , która zawiera datę, która ma być ustawiona jako bieżący wybór.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Ta funkcja członkowska implementuje zachowanie [MCM_SETCURSEL](/windows/win32/Controls/mcm-setcursel)komunikatu Win32, zgodnie z opisem w Windows SDK. W implementacji MFC `SetCurSel` , można określić użycie, użycie `COleDateTime` `CTime` lub `SYSTEMTIME` strukturę użycie.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFC_CMonthCalCtrl#5](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_11.cpp)]

## <a name="cmonthcalctrlsetdaystate"></a><a name="setdaystate"></a> CMonthCalCtrl:: SetDayState

Ustawia wyświetlaną liczbę dni w kontrolce kalendarza miesięcznego.

```
BOOL SetDayState(
    int nMonths,
    LPMONTHDAYSTATE pStates);
```

### <a name="parameters"></a>Parametry

*nMonths*<br/>
Wartość wskazująca, ile elementów znajduje się w tablicy, do której wskazuje *pStates* .

*pStates*<br/>
Wskaźnik do [MONTHDAYSTATE](/windows/win32/Controls/monthdaystate) tablicy wartości, który definiuje, w jaki sposób formant kalendarza miesięcznego będzie rysowany codziennie na ekranie. Typ danych MONTHDAYSTATE jest polem bitowym, gdzie każdy bit (od 1 do 31) reprezentuje stan dnia w miesiącu. Jeśli bit jest włączony, odpowiedni dzień będzie wyświetlany pogrubiony; w przeciwnym razie będzie wyświetlana bez wyróżniania.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Ta funkcja członkowska implementuje zachowanie [MCM_SETDAYSTATE](/windows/win32/Controls/mcm-setdaystate)komunikatu Win32, zgodnie z opisem w Windows SDK.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFC_CMonthCalCtrl#6](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_12.cpp)]

## <a name="cmonthcalctrlsetdecadeview"></a><a name="setdecadeview"></a> CMonthCalCtrl:: SetDecadeView

Ustawia formant kalendarza bieżącego miesiąca na widok dekady.

```
BOOL SetDecadeView();
```

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli ta metoda zakończyła się pomyślnie; w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

Ta metoda używa metody [CMonthCalCtrl:: SetCurrentView](#setcurrentview) do ustawiania widoku na `MCMV_DECADE` , który reprezentuje widok dekady.

## <a name="cmonthcalctrlsetfirstdayofweek"></a><a name="setfirstdayofweek"></a> CMonthCalCtrl:: setpierwszydzieńtygodnia

Ustawia dzień tygodnia, który ma być wyświetlany w kolumnie z lewej strony kalendarza.

```
BOOL SetFirstDayOfWeek(
    int iDay,
    int* lpnOld = NULL);
```

### <a name="parameters"></a>Parametry

*iDay*<br/>
Wartość całkowita reprezentująca dzień, który ma zostać ustawiony jako pierwszy dzień tygodnia. Ta wartość musi być jedną z numerów dni. Aby uzyskać opis numerów dni, zobacz [getpierwszydzieńtygodnia](#getfirstdayofweek) .

*lpnOld*<br/>
Wskaźnik do liczby całkowitej wskazującej pierwszy dzień tygodnia, który został wcześniej ustawiony.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli poprzedni pierwszy dzień tygodnia ma ustawioną wartość inną niż LOCALE_IFIRSTDAYOFWEEK, która jest dniem wskazanym w ustawieniu panelu sterowania. W przeciwnym razie ta funkcja zwraca wartość 0.

### <a name="remarks"></a>Uwagi

Ta funkcja członkowska implementuje zachowanie [MCM_SETFIRSTDAYOFWEEK](/windows/win32/Controls/mcm-setfirstdayofweek)komunikatu Win32, zgodnie z opisem w Windows SDK.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFC_CMonthCalCtrl#7](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_13.cpp)]

## <a name="cmonthcalctrlsetmaxselcount"></a><a name="setmaxselcount"></a> CMonthCalCtrl:: SetMaxSelCount

Ustawia maksymalną liczbę dni, które można wybrać w kontrolce kalendarza miesięcznego.

```
BOOL SetMaxSelCount(int nMax);
```

### <a name="parameters"></a>Parametry

*Nmaks.*<br/>
Wartość, która będzie reprezentować maksymalną liczbę wybranych dni.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Ta funkcja członkowska implementuje zachowanie [MCM_SETMAXSELCOUNT](/windows/win32/Controls/mcm-setmaxselcount)komunikatu Win32, zgodnie z opisem w Windows SDK.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFC_CMonthCalCtrl#8](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_14.cpp)]

## <a name="cmonthcalctrlsetmonthdelta"></a><a name="setmonthdelta"></a> CMonthCalCtrl:: SetMonthDelta

Ustawia szybkość przewijania dla kontrolki kalendarza miesięcznego.

```
int SetMonthDelta(int iDelta);
```

### <a name="parameters"></a>Parametry

*iDelta*<br/>
Liczba miesięcy, które mają zostać ustawione jako szybkość przewijania kontrolki. Jeśli ta wartość jest równa zero, Delta miesiąca jest resetowana do wartości domyślnej, co oznacza liczbę miesięcy wyświetlanych w formancie.

### <a name="return-value"></a>Wartość zwracana

Poprzednia szybkość przewijania. Jeśli współczynnik przewijania nie został wcześniej ustawiony, wartość zwracana wynosi 0.

### <a name="remarks"></a>Uwagi

Ta funkcja członkowska implementuje zachowanie [MCM_SETMONTHDELTA](/windows/win32/Controls/mcm-setmonthdelta)komunikatu Win32, zgodnie z opisem w Windows SDK.

## <a name="cmonthcalctrlsetmonthview"></a><a name="setmonthview"></a> CMonthCalCtrl:: SetMonthView

Ustawia kontrolkę kalendarz bieżący miesiąc, aby wyświetlić widok miesiąca.

```
BOOL SetMonthView();
```

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli ta metoda zakończyła się pomyślnie; w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

Ta metoda używa metody [CMonthCalCtrl:: SetCurrentView](#setcurrentview) , aby ustawić widok na MCMV_MONTH, który reprezentuje widok miesiąca.

### <a name="example"></a>Przykład

Poniższy przykład kodu definiuje zmienną, `m_monthCalCtrl` , która jest używana do programistycznego dostępu do kontrolki kalendarza miesięcznego. Ta zmienna jest używana w następnym przykładzie.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>Przykład

Poniższy przykład kodu ustawia formant kalendarza miesięcznego, aby wyświetlić widoki miesiąc, rok, dekada i Century.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_15.cpp)]

## <a name="cmonthcalctrlsetrange"></a><a name="setrange"></a> CMonthCalCtrl:: SetRange

Ustawia minimalną i maksymalną dozwoloną datę dla kontrolki kalendarza miesięcznego.

```
BOOL SetRange(
    const COleDateTime* pMinRange,
    const COleDateTime* pMaxRange);

BOOL SetRange(
    const CTime* pMinRange,
    const CTime* pMaxRange);

BOOL SetRange(
    const LPSYSTEMTIME pMinRange,
    const LPSYSTEMTIME pMaxRange);
```

### <a name="parameters"></a>Parametry

*pMinRange*<br/>
Wskaźnik do `COleDateTime` obiektu, `CTime` obiektu lub struktury [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) zawierającej datę na najniższym końcu zakresu.

*pMaxRange*<br/>
Wskaźnik do `COleDateTime` obiektu, `CTime` obiektu lub `SYSTEMTIME` struktury zawierającej datę z najwyższego końca zakresu.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Ta funkcja członkowska implementuje zachowanie [MCM_SETRANGE](/windows/win32/Controls/mcm-setrange)komunikatu Win32, zgodnie z opisem w Windows SDK. W implementacji MFC `SetRange` , można określić użycie, użycie `COleDateTime` `CTime` lub `SYSTEMTIME` użycie struktury.

### <a name="example"></a>Przykład

  Zobacz przykład dla [CMonthCalCtrl:: GetRange](#getrange).

## <a name="cmonthcalctrlsetselrange"></a><a name="setselrange"></a> CMonthCalCtrl:: SetSelRange

Ustawia zaznaczenie dla kontrolki kalendarza miesięcznego na dany zakres dat.

```
BOOL SetSelRange(
    const COleDateTime& pMinRange,
    const COleDateTime& pMaxRange);

BOOL SetSelRange(
    const CTime& pMinRange,
    const CTime& pMaxRange);

BOOL SetSelRange(
    const LPSYSTEMTIME pMinRange,
    const LPSYSTEMTIME pMaxRange);
```

### <a name="parameters"></a>Parametry

*pMinRange*<br/>
Wskaźnik do `COleDateTime` obiektu, `CTime` obiektu lub struktury [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) zawierającej datę na najniższym końcu zakresu.

*pMaxRange*<br/>
Wskaźnik do `COleDateTime` obiektu, `CTime` obiektu lub `SYSTEMTIME` struktury zawierającej datę z najwyższego końca zakresu.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Ta funkcja członkowska implementuje zachowanie [MCM_SETSELRANGE](/windows/win32/Controls/mcm-setselrange)komunikatu Win32, zgodnie z opisem w Windows SDK. W implementacji MFC `SetSelRange` , można określić użycie, użycie `COleDateTime` `CTime` lub `SYSTEMTIME` użycie struktury.

## <a name="cmonthcalctrlsettoday"></a><a name="settoday"></a> CMonthCalCtrl:: settoday

Ustawia kontrolkę Calendar dla bieżącego dnia.

```cpp
void SetToday(const COleDateTime& refDateTime);
void SetToday(const CTime* pDateTime);
void SetToday(const LPSYSTEMTIME pDateTime);
```

### <a name="parameters"></a>Parametry

*refDateTime*<br/>
Odwołanie do obiektu [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) zawierającego bieżącą datę.

*pDateTime*<br/>
W drugiej wersji wskaźnik do obiektu [CTime](../../atl-mfc-shared/reference/ctime-class.md) zawierającego bieżące informacje o dacie. W trzeciej wersji wskaźnik do struktury [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) , która zawiera bieżące informacje o dacie.

### <a name="remarks"></a>Uwagi

Ta funkcja członkowska implementuje zachowanie [MCM_SETTODAY](/windows/win32/Controls/mcm-settoday)komunikatu Win32, zgodnie z opisem w Windows SDK.

### <a name="example"></a>Przykład

  Zobacz przykład dla [CMonthCalCtrl:: GetToday](#gettoday).

## <a name="cmonthcalctrlsetyearview"></a><a name="setyearview"></a> CMonthCalCtrl:: SetYearView

Ustawia bieżącą kontrolkę kalendarza miesięcznego na rok.

```
BOOL SetYearView();
```

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli ta metoda zakończyła się pomyślnie; w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

Ta metoda używa metody [CMonthCalCtrl:: SetCurrentView](#setcurrentview) , aby ustawić widok na MCMV_YEAR, co reprezentuje widok roczny.

## <a name="cmonthcalctrlsizeminreq"></a><a name="sizeminreq"></a> CMonthCalCtrl:: SizeMinReq

Wyświetla kontrolkę kalendarza miesięcznego o minimalnym rozmiarze, który wyświetla jeden miesiąc.

```
BOOL SizeMinReq(BOOL bRepaint = TRUE);
```

### <a name="parameters"></a>Parametry

*bRepaint*<br/>
Określa, czy kontrolka ma być odświeżana. Domyślnie wartość TRUE. W przypadku wartości FALSE nie następuje odświeżenie.

### <a name="return-value"></a>Wartość zwracana

Wartość różna od zera, jeśli rozmiar kontrolki kalendarza miesięcznego ma wartość minimum; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Wywołanie `SizeMinReq` pomyślnie Wyświetla całą kontrolkę kalendarza miesięcznego w kalendarzu o jeden miesiąc.

## <a name="cmonthcalctrlsizerecttomin"></a><a name="sizerecttomin"></a> CMonthCalCtrl:: SizeRectToMin

W przypadku formantu kalendarza bieżącego miesiąca program oblicza najmniejszy prostokąt, który może zawierać wszystkie kalendarze mieszczące się w określonym prostokącie.

```
LPRECT SizeRectToMin(LPRECT lpRect);
```

### <a name="parameters"></a>Parametry

*lpRect*\
podczas Wskaźnik do struktury [prostokąta](/windows/win32/api/windef/ns-windef-rect) , który definiuje prostokąt zawierający żądaną liczbę kalendarzy.

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do struktury [Rect](/windows/win32/api/windef/ns-windef-rect) , który definiuje prostokąt, którego rozmiar jest mniejszy niż lub równy prostokątowi zdefiniowanemu przez parametr *lpRect* .

### <a name="remarks"></a>Uwagi

Ta metoda oblicza, ile kalendarzy mieści się w prostokącie określonym przez parametr *lpRect* , a następnie zwraca najmniejszy prostokąt, który może zawierać tę liczbę kalendarzy. W efekcie ta metoda zmniejsza określony prostokąt, aby dokładnie dopasować żądaną liczbę kalendarzy.

Ta metoda wysyła komunikat [MCM_SIZERECTTOMIN](/windows/win32/Controls/mcm-sizerecttomin) , który jest opisany w Windows SDK.

## <a name="see-also"></a>Zobacz też

[Przykład CMNCTRL1 MFC](../../overview/visual-cpp-samples.md)<br/>
[Klasa CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasa korzystanie CDateTimeCtrl](../../mfc/reference/cdatetimectrl-class.md)
