---
description: 'Dowiedz się więcej na temat: Klasa korzystanie CSpinButtonCtrl'
title: Klasa korzystanie CSpinButtonCtrl
ms.date: 11/04/2016
f1_keywords:
- CSpinButtonCtrl
- AFXCMN/CSpinButtonCtrl
- AFXCMN/CSpinButtonCtrl::CSpinButtonCtrl
- AFXCMN/CSpinButtonCtrl::Create
- AFXCMN/CSpinButtonCtrl::CreateEx
- AFXCMN/CSpinButtonCtrl::GetAccel
- AFXCMN/CSpinButtonCtrl::GetBase
- AFXCMN/CSpinButtonCtrl::GetBuddy
- AFXCMN/CSpinButtonCtrl::GetPos
- AFXCMN/CSpinButtonCtrl::GetRange
- AFXCMN/CSpinButtonCtrl::SetAccel
- AFXCMN/CSpinButtonCtrl::SetBase
- AFXCMN/CSpinButtonCtrl::SetBuddy
- AFXCMN/CSpinButtonCtrl::SetPos
- AFXCMN/CSpinButtonCtrl::SetRange
helpviewer_keywords:
- CSpinButtonCtrl [MFC], CSpinButtonCtrl
- CSpinButtonCtrl [MFC], Create
- CSpinButtonCtrl [MFC], CreateEx
- CSpinButtonCtrl [MFC], GetAccel
- CSpinButtonCtrl [MFC], GetBase
- CSpinButtonCtrl [MFC], GetBuddy
- CSpinButtonCtrl [MFC], GetPos
- CSpinButtonCtrl [MFC], GetRange
- CSpinButtonCtrl [MFC], SetAccel
- CSpinButtonCtrl [MFC], SetBase
- CSpinButtonCtrl [MFC], SetBuddy
- CSpinButtonCtrl [MFC], SetPos
- CSpinButtonCtrl [MFC], SetRange
ms.assetid: 509bfd76-1c5a-4af6-973f-e133c0b87734
ms.openlocfilehash: cfca3d11e4e22cf0fc09025b27400bcefeb0066b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342693"
---
# <a name="cspinbuttonctrl-class"></a>Klasa korzystanie CSpinButtonCtrl

Oferuje funkcje formantu typowego przycisku pokrętła systemu Windows.

## <a name="syntax"></a>Składnia

```
class CSpinButtonCtrl : public CWnd
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[Korzystanie CSpinButtonCtrl:: Korzystanie CSpinButtonCtrl](#cspinbuttonctrl)|Konstruuje `CSpinButtonCtrl` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[Korzystanie CSpinButtonCtrl:: Create](#create)|Tworzy kontrolkę przycisk pokrętła i dołącza ją do `CSpinButtonCtrl` obiektu.|
|[Korzystanie CSpinButtonCtrl:: CreateEx](#createex)|Tworzy kontrolkę przycisku pokrętła z określonymi stylami rozszerzonymi systemu Windows i dołącza je do `CSpinButtonCtrl` obiektu.|
|[Korzystanie CSpinButtonCtrl:: GetAccel](#getaccel)|Pobiera informacje o przyspieszeniu dla kontrolki przycisku pokrętła.|
|[Korzystanie CSpinButtonCtrl:: GetBase](#getbase)|Pobiera bieżącą podstawę dla kontrolki przycisku pokrętła.|
|[Korzystanie CSpinButtonCtrl:: getkolega](#getbuddy)|Pobiera wskaźnik do bieżącego okna partnera.|
|[Korzystanie CSpinButtonCtrl:: GetPos](#getpos)|Pobiera bieżącą pozycję kontrolki przycisku pokrętła.|
|[Korzystanie CSpinButtonCtrl:: GetRange](#getrange)|Pobiera górną i dolną granicę (zakres) dla kontrolki przycisku pokrętła.|
|[Korzystanie CSpinButtonCtrl:: SetAccel](#setaccel)|Ustawia przyspieszenie dla kontrolki przycisku pokrętła.|
|[Korzystanie CSpinButtonCtrl:: setbase](#setbase)|Ustawia podstawę dla kontrolki przycisku pokrętła.|
|[Korzystanie CSpinButtonCtrl:: setkolega](#setbuddy)|Ustawia okno partnera dla kontrolki przycisku pokrętła.|
|[Korzystanie CSpinButtonCtrl:: SetPos](#setpos)|Ustawia bieżącą pozycję dla kontrolki.|
|[Korzystanie CSpinButtonCtrl:: SetRange](#setrange)|Ustawia górną i dolną granicę (zakres) dla kontrolki przycisku pokrętła.|

## <a name="remarks"></a>Uwagi

"Kontrolka przycisku pokrętła" (nazywana również kontrolką w górę) to para przycisków strzałek, które użytkownik może kliknąć, aby zwiększyć lub zmniejszyć wartość, na przykład pozycję przewijania lub liczbę wyświetlaną w formancie pomocnika. Wartość skojarzona z kontrolką przycisku pokrętła jest nazywana jej bieżącym położeniem. Kontrolka przycisku pokrętła jest najczęściej używana z kontrolką towarzyszącą o nazwie "okno kolega".

Ten formant (i w związku z tym `CSpinButtonCtrl` Klasa) jest dostępny tylko dla programów uruchomionych w systemach windows 95/98 i Windows NT w wersji 3,51 lub nowszej.

Do użytkownika, kontrolka przycisku pokrętła i jego okna partnera często wyglądają jak pojedyncza kontrolka. Możesz określić, że Kontrolka przycisku pokrętła ma automatycznie pomieścić się obok okna partnera i automatycznie ustawił podpis okna partnera w bieżącym położeniu. Aby monitować użytkownika o dane liczbowe, można użyć kontrolki przycisku pokrętła z kontrolką edycji.

Kliknięcie strzałki w górę przenosi bieżącą pozycję w dół do wartości maksymalnej, a kliknięcie strzałki w dół przenosi bieżącą pozycję w kierunku minimum. Wartość domyślna to 100, a wartość maksymalna to 0. Za każdym razem, gdy minimalne ustawienie jest większe niż ustawienie maksymalne (na przykład gdy ustawienia domyślne są używane), kliknięcie strzałki w górę zmniejsza wartość pozycji i klika strzałkę w dół.

Kontrolka przycisku pokrętła bez okna partnera działa jako Sortuj uproszczony pasek przewijania. Na przykład kontrolka karta czasami wyświetla kontrolkę przycisk pokrętła, aby umożliwić użytkownikowi przewinięcie dodatkowych kart do widoku.

Aby uzyskać więcej informacji na temat korzystania z programu `CSpinButtonCtrl` , zobacz [kontrolki](../../mfc/controls-mfc.md) i [Używanie korzystanie CSpinButtonCtrl](../../mfc/using-cspinbuttonctrl.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CSpinButtonCtrl`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxcmn. h

## <a name="cspinbuttonctrlcreate"></a><a name="create"></a> Korzystanie CSpinButtonCtrl:: Create

Tworzy kontrolkę przycisk pokrętła i dołącza ją do `CSpinButtonCtrl` obiektu.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametry

*dwStyle*<br/>
Określa styl kontrolki przycisku pokrętła. Zastosuj dowolną kombinację stylów kontrolki przycisku pokrętła do kontrolki. Te style są opisane w [stylach kontrolek w górę](/windows/win32/Controls/up-down-control-styles) w Windows SDK.

*cinania*<br/>
Określa rozmiar i położenie kontrolki przycisku pokrętła. Może być obiektem [CRect](../../atl-mfc-shared/reference/crect-class.md) lub strukturą [Rect](/windows/win32/api/windef/ns-windef-rect)

*pParentWnd*<br/>
Wskaźnik do okna nadrzędnego kontrolki przycisku pokrętła, zwykle a `CDialog` . Nie może mieć wartości NULL.

*nID*<br/>
Określa identyfikator kontrolki przycisku pokrętła.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli Inicjalizacja zakończyła się pomyślnie; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Należy utworzyć `CSpinButtonCtrl` obiekt w dwóch krokach, wywołać konstruktora, a następnie wywołać `Create` , który tworzy formant przycisku pokrętła i dołącza go do `CSpinButtonCtrl` obiektu.

Aby utworzyć kontrolkę przycisk pokrętła z rozszerzonymi stylami okien, należy wywołać [Korzystanie CSpinButtonCtrl:: CreateEx](#createex) zamiast `Create` .

## <a name="cspinbuttonctrlcreateex"></a><a name="createex"></a> Korzystanie CSpinButtonCtrl:: CreateEx

Tworzy kontrolkę (okno podrzędne) i kojarzy ją z `CSpinButtonCtrl` obiektem.

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametry

*dwExStyle*<br/>
Określa rozszerzony styl formantu, który jest tworzony. Aby zapoznać się z listą rozszerzonych stylów systemu Windows, zobacz *dwExStyle* parametru [elementu CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) w Windows SDK.

*dwStyle*<br/>
Określa styl kontrolki przycisku pokrętła. Zastosuj dowolną kombinację stylów kontrolki przycisku pokrętła do kontrolki. Te style są opisane w [stylach kontrolek w górę](/windows/win32/Controls/up-down-control-styles) w Windows SDK.

*cinania*<br/>
Odwołanie do struktury [Rect](/windows/win32/api/windef/ns-windef-rect) opisujące rozmiar i położenie okna, które ma zostać utworzone, we współrzędnych klienta *pParentWnd*.

*pParentWnd*<br/>
Wskaźnik do okna, które jest elementem nadrzędnym formantu.

*nID*<br/>
Identyfikator okna podrzędnego kontrolki.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Użyj `CreateEx` zamiast [tworzenia](#create) , aby zastosować rozszerzone style systemu Windows, które są określone przez WS_EX_ przedniej stylu rozszerzonego systemu Windows.

## <a name="cspinbuttonctrlcspinbuttonctrl"></a><a name="cspinbuttonctrl"></a> Korzystanie CSpinButtonCtrl:: Korzystanie CSpinButtonCtrl

Konstruuje `CSpinButtonCtrl` obiekt.

```
CSpinButtonCtrl();
```

## <a name="cspinbuttonctrlgetaccel"></a><a name="getaccel"></a> Korzystanie CSpinButtonCtrl:: GetAccel

Pobiera informacje o przyspieszeniu dla kontrolki przycisku pokrętła.

```
UINT GetAccel(
    int nAccel,
    UDACCEL* pAccel) const;
```

### <a name="parameters"></a>Parametry

*nAccel*<br/>
Liczba elementów w tablicy określonej przez *pAccel*.

*pAccel*<br/>
Wskaźnik do tablicy struktur [UDACCEL](/windows/win32/api/commctrl/ns-commctrl-udaccel) , które odbierają informacje o przyspieszeniu.

### <a name="return-value"></a>Wartość zwracana

Liczba pobranych struktur akceleratora.

## <a name="cspinbuttonctrlgetbase"></a><a name="getbase"></a> Korzystanie CSpinButtonCtrl:: GetBase

Pobiera bieżącą podstawę dla kontrolki przycisku pokrętła.

```
UINT GetBase() const;
```

### <a name="return-value"></a>Wartość zwracana

Bieżąca wartość podstawowa.

## <a name="cspinbuttonctrlgetbuddy"></a><a name="getbuddy"></a> Korzystanie CSpinButtonCtrl:: getkolega

Pobiera wskaźnik do bieżącego okna partnera.

```
CWnd* GetBuddy() const;
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do bieżącego okna partnera.

## <a name="cspinbuttonctrlgetpos"></a><a name="getpos"></a> Korzystanie CSpinButtonCtrl:: GetPos

Pobiera bieżącą pozycję kontrolki przycisku pokrętła.

```
int GetPos() const;  int GetPos32(LPBOOL lpbError = NULL) const;
```

### <a name="parameters"></a>Parametry

*lpbError*<br/>
Wskaźnik do wartości logicznej, która jest ustawiona na zero w przypadku pomyślnego pobrania lub wartości innej niż zero w przypadku wystąpienia błędu. Jeśli ten parametr ma wartość NULL, błędy nie są zgłaszane.

### <a name="return-value"></a>Wartość zwracana

Pierwsza wersja zwraca 16-bitową bieżącą pozycję w wyrazie z małą kolejnością. Słowo o wysokim porządku jest niezerowe, jeśli wystąpił błąd.

Druga wersja zwraca pozycję 32-bitową.

### <a name="remarks"></a>Uwagi

Gdy przetwarza zwracaną wartość, formant aktualizuje bieżącą pozycję na podstawie podpisu okna partnera. Kontrolka zwraca błąd, jeśli nie ma okna partnera lub jeśli podpis określa nieprawidłową lub poza zakresem.

## <a name="cspinbuttonctrlgetrange"></a><a name="getrange"></a> Korzystanie CSpinButtonCtrl:: GetRange

Pobiera górną i dolną granicę (zakres) dla kontrolki przycisku pokrętła.

```
DWORD GetRange() const;

void GetRange(
    int& lower,
    int& upper) const;

void GetRange32(
    int& lower,
    int &upper) const;
```

### <a name="parameters"></a>Parametry

*dołu*<br/>
Odwołanie do liczby całkowitej, która otrzymuje dolny limit dla kontrolki.

*prawym górnym*<br/>
Odwołanie do liczby całkowitej, która odbiera górny limit dla kontrolki.

### <a name="return-value"></a>Wartość zwracana

Pierwsza wersja zwraca 32-bitową wartość zawierającą górną i dolną granicę. Wyraz o niskiej kolejności jest górnym limitem dla kontrolki, a wysoki jest dolny limit.

### <a name="remarks"></a>Uwagi

Funkcja członkowska `GetRange32` Pobiera zakres kontrolki przycisku pokrętła jako 32-bitową liczbę całkowitą.

## <a name="cspinbuttonctrlsetaccel"></a><a name="setaccel"></a> Korzystanie CSpinButtonCtrl:: SetAccel

Ustawia przyspieszenie dla kontrolki przycisku pokrętła.

```
BOOL SetAccel(
    int nAccel,
    UDACCEL* pAccel);
```

### <a name="parameters"></a>Parametry

*nAccel*<br/>
Liczba struktur [UDACCEL](/windows/win32/api/commctrl/ns-commctrl-udaccel) określonych przez *pAccel*.

*pAccel*<br/>
Wskaźnik do tablicy struktur UDACCEL, które zawierają informacje o przyspieszeniu. Elementy powinny być sortowane w kolejności rosnącej na podstawie `nSec` elementu członkowskiego.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; w przeciwnym razie 0.

## <a name="cspinbuttonctrlsetbase"></a><a name="setbase"></a> Korzystanie CSpinButtonCtrl:: setbase

Ustawia podstawę dla kontrolki przycisku pokrętła.

```
int SetBase(int nBase);
```

### <a name="parameters"></a>Parametry

*nBase*<br/>
Nowa wartość podstawowa dla kontrolki. Może to być 10 dla dziesiętnych lub 16 dla szesnastkowych.

### <a name="return-value"></a>Wartość zwracana

Poprzednia wartość podstawowa, jeśli powiodła się, lub zero, jeśli podano nieprawidłową podstawę.

### <a name="remarks"></a>Uwagi

Wartość podstawowa określa, czy w oknie kolega są wyświetlane liczby w postaci cyfr dziesiętnych lub szesnastkowych. Liczby szesnastkowe są zawsze niepodpisane; cyfry dziesiętne są podpisane.

## <a name="cspinbuttonctrlsetbuddy"></a><a name="setbuddy"></a> Korzystanie CSpinButtonCtrl:: setkolega

Ustawia okno partnera dla kontrolki przycisku pokrętła.

```
CWnd* SetBuddy(CWnd* pWndBuddy);
```

### <a name="parameters"></a>Parametry

*pWndBuddy*<br/>
Wskaźnik do nowego okna partnera.

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do poprzedniego okna partnera.

### <a name="remarks"></a>Uwagi

Kontrolka pokrętła jest prawie zawsze skojarzona z innym oknem, takim jak kontrolka edycji, która wyświetla zawartość. To inne okno nosi nazwę "kolega" kontrolki pokrętła.

## <a name="cspinbuttonctrlsetpos"></a><a name="setpos"></a> Korzystanie CSpinButtonCtrl:: SetPos

Ustawia bieżącą pozycję kontrolki przycisku pokrętła.

```
int SetPos(int nPos);
int SetPos32(int nPos);
```

### <a name="parameters"></a>Parametry

*nPos*<br/>
Nowa pozycja dla kontrolki. Ta wartość musi należeć do zakresu określonego przez górne i dolne limity dla kontrolki.

### <a name="return-value"></a>Wartość zwracana

Poprzednia pozycja (16-bitowa precyzja dla `SetPos` , 32-bitowej precyzji `SetPos32` ).

### <a name="remarks"></a>Uwagi

`SetPos32` ustawia pozycję 32-bitową.

## <a name="cspinbuttonctrlsetrange"></a><a name="setrange"></a> Korzystanie CSpinButtonCtrl:: SetRange

Ustawia górną i dolną granicę (zakres) dla kontrolki przycisku pokrętła.

```cpp
void SetRange(
    short nLower,
    short nUpper);

void SetRange32(
    int nLower,
    int nUpper);
```

### <a name="parameters"></a>Parametry

*nLower* i *nUpper*<br/>
Górny i dolny limit dla kontrolki. Wartość `SetRange` nie może być większa niż UD_MAXVAL ani mniejsza niż UD_MINVAL; Ponadto różnica między tymi dwoma limitami nie może przekroczyć UD_MAXVAL. `SetRange32` nie nakłada żadnych ograniczeń na limity; Użyj dowolnych liczb całkowitych.

### <a name="remarks"></a>Uwagi

Funkcja członkowska `SetRange32` ustawia zakres 32-bitowy dla kontrolki przycisk pokrętła.

> [!NOTE]
> Domyślny zakres dla przycisku pokrętła ma ustawioną wartość równą zero (0) i minimalną wartość 100. Ponieważ wartość maksymalna jest mniejsza niż wartość minimalna, kliknięcie strzałki w górę spowoduje zmniejszenie pozycji, a kliknięcie strzałki w dół spowoduje jej zwiększenie. Użyj `CSpinButtonCtrl::SetRange` , aby dostosować te wartości.

## <a name="see-also"></a>Zobacz też

[Przykład CMNCTRL2 MFC](../../overview/visual-cpp-samples.md)<br/>
[Klasa CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasa korzystanie CSliderCtrl](../../mfc/reference/csliderctrl-class.md)
