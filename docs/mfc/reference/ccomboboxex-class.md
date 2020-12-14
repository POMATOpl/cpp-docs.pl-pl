---
description: 'Dowiedz się więcej na temat: Klasa korzystanie CComboBoxEx'
title: Klasa korzystanie CComboBoxEx
ms.date: 11/04/2016
f1_keywords:
- CComboBoxEx
- AFXCMN/CComboBoxEx
- AFXCMN/CComboBoxEx::CComboBoxEx
- AFXCMN/CComboBoxEx::Create
- AFXCMN/CComboBoxEx::CreateEx
- AFXCMN/CComboBoxEx::DeleteItem
- AFXCMN/CComboBoxEx::GetComboBoxCtrl
- AFXCMN/CComboBoxEx::GetEditCtrl
- AFXCMN/CComboBoxEx::GetExtendedStyle
- AFXCMN/CComboBoxEx::GetImageList
- AFXCMN/CComboBoxEx::GetItem
- AFXCMN/CComboBoxEx::HasEditChanged
- AFXCMN/CComboBoxEx::InsertItem
- AFXCMN/CComboBoxEx::SetExtendedStyle
- AFXCMN/CComboBoxEx::SetImageList
- AFXCMN/CComboBoxEx::SetItem
- AFXCMN/CComboBoxEx::SetWindowTheme
helpviewer_keywords:
- CComboBoxEx [MFC], CComboBoxEx
- CComboBoxEx [MFC], Create
- CComboBoxEx [MFC], CreateEx
- CComboBoxEx [MFC], DeleteItem
- CComboBoxEx [MFC], GetComboBoxCtrl
- CComboBoxEx [MFC], GetEditCtrl
- CComboBoxEx [MFC], GetExtendedStyle
- CComboBoxEx [MFC], GetImageList
- CComboBoxEx [MFC], GetItem
- CComboBoxEx [MFC], HasEditChanged
- CComboBoxEx [MFC], InsertItem
- CComboBoxEx [MFC], SetExtendedStyle
- CComboBoxEx [MFC], SetImageList
- CComboBoxEx [MFC], SetItem
- CComboBoxEx [MFC], SetWindowTheme
ms.assetid: 33ca960a-2409-478c-84a4-a2ee8ecfe8f7
ms.openlocfilehash: 6d5b8a520fe62cbc60883370ec92abe4d978b5bf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265522"
---
# <a name="ccomboboxex-class"></a>Klasa korzystanie CComboBoxEx

Rozszerza formant pola kombi, dostarczając obsługę list obrazów.

## <a name="syntax"></a>Składnia

```
class CComboBoxEx : public CComboBox
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[Korzystanie CComboBoxEx:: Korzystanie CComboBoxEx](#ccomboboxex)|Konstruuje `CComboBoxEx` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[Korzystanie CComboBoxEx:: Create](#create)|Tworzy pole kombi i dołącza je do `CComboBoxEx` obiektu.|
|[Korzystanie CComboBoxEx:: CreateEx](#createex)|Tworzy pole kombi z określonymi stylami rozszerzonymi systemu Windows i dołącza je do `ComboBoxEx` obiektu.|
|[Korzystanie CComboBoxEx::D eleteItem](#deleteitem)|Usuwa element z `ComboBoxEx` formantu.|
|[Korzystanie CComboBoxEx:: GetComboBoxCtrl](#getcomboboxctrl)|Pobiera wskaźnik do formantu podrzędnego pola kombi.|
|[Korzystanie CComboBoxEx:: GetEditCtrl](#geteditctrl)|Pobiera uchwyt do części kontrolki edycji `ComboBoxEx` kontrolki.|
|[Korzystanie CComboBoxEx:: getextendeds](#getextendedstyle)|Pobiera rozszerzone style, które są używane dla `ComboBoxEx` kontrolki.|
|[Korzystanie CComboBoxEx:: GetImageList](#getimagelist)|Pobiera wskaźnik do listy obrazów przypisanej do `ComboBoxEx` kontrolki.|
|[Korzystanie CComboBoxEx:: GetItem](#getitem)|Pobiera informacje o elemencie dla danego `ComboBoxEx` elementu.|
|[Korzystanie CComboBoxEx:: HasEditChanged](#haseditchanged)|Określa, czy użytkownik zmienił zawartość `ComboBoxEx` kontrolki edycji, wpisując ciąg.|
|[Korzystanie CComboBoxEx:: InsertItem](#insertitem)|Wstawia nowy element w `ComboBoxEx` kontrolce.|
|[Korzystanie CComboBoxEx:: setextended](#setextendedstyle)|Ustawia style rozszerzone wewnątrz `ComboBoxEx` kontrolki.|
|[Korzystanie CComboBoxEx:: SetImageList](#setimagelist)|Ustawia listę obrazów dla `ComboBoxEx` kontrolki.|
|[Korzystanie CComboBoxEx:: SetItem](#setitem)|Ustawia atrybuty dla elementu w `ComboBoxEx` kontrolce.|
|[Korzystanie CComboBoxEx:: SetWindowTheme](#setwindowtheme)|Ustawia styl wizualizacji rozszerzonej kontrolki pola kombi.|

## <a name="remarks"></a>Uwagi

Za pomocą `CComboBoxEx` do tworzenia kontrolek pola kombi nie jest już konieczne implementowanie własnego kodu rysowania obrazu. Zamiast tego użyj polecenia, `CComboBoxEx` Aby uzyskać dostęp do obrazów z listy obrazów.

## <a name="image-list-support"></a>Obsługa listy obrazów

W standardowym polu kombi właściciel pola kombi jest odpowiedzialny za Rysowanie obrazu przez utworzenie pola kombi jako formantu rysowania przez właściciela. Gdy używasz `CComboBoxEx` , nie musisz ustawiać stylów rysowania CBS_OWNERDRAWFIXED i CBS_HASSTRINGS, ponieważ są one implikowane. W przeciwnym razie musisz napisać kod, aby wykonać operacje rysowania. `CComboBoxEx`Kontrolka obsługuje maksymalnie trzy obrazy na element: jeden dla wybranego stanu, jeden dla niezaznaczonego stanu i jeden dla obrazu nakładki.

## <a name="styles"></a>Style

`CComboBoxEx` obsługuje style CBS_SIMPLE, CBS_DROPDOWN, CBS_DROPDOWNLIST i WS_CHILD. Wszystkie inne style przenoszone podczas tworzenia okna są ignorowane przez formant. Po utworzeniu okna można podać inne style pola kombi, wywołując `CComboBoxEx` funkcję elementu członkowskiego [setextended](#setextendedstyle). Za pomocą tych stylów można:

- Ustaw wyszukiwanie ciągów na liście, aby uwzględniać wielkość liter.

- Utwórz kontrolkę pole kombi, która używa ukośnika ("/"), ukośnika odwrotnego (" \\ ") i kropki (".") jako ograniczników wyrazów. Pozwala to użytkownikom na przechodzenie z programu Word do programu Word przy użyciu skrótu klawiaturowego CTRL + STRZAŁKA.

- Ustaw kontrolkę pole kombi na wyświetlaną lub niewyświetlaną obrazu. Jeśli obraz nie jest wyświetlany, pole kombi może usunąć wcięcie tekstu, które posłuży do obrazu.

- Utwórz formant wąskiego pola kombi, w tym jego rozmiar, tak aby zawierał szersze pole kombi.

Te flagi stylu są opisane w dalszej [postaci przy użyciu korzystanie CComboBoxEx](../../mfc/using-ccomboboxex.md).

## <a name="item-retention-and-callback-item-attributes"></a>Przechowywanie elementów i atrybuty elementu wywołania zwrotnego

Informacje o elementach, takie jak indeksy dla elementów i obrazów, wartości wcięć i ciągi tekstowe, są przechowywane w strukturze Win32 [COMBOBOXEXITEM](/windows/win32/api/commctrl/ns-commctrl-comboboxexitemw), zgodnie z opisem w Windows SDK. Struktura zawiera również elementy członkowskie, które odnoszą się do flag wywołania zwrotnego.

Aby uzyskać szczegółowe omówienie pojęć, zobacz [using korzystanie CComboBoxEx](../../mfc/using-ccomboboxex.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CComboBox](../../mfc/reference/ccombobox-class.md)

`CComboBoxEx`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxcmn. h

## <a name="ccomboboxexccomboboxex"></a><a name="ccomboboxex"></a> Korzystanie CComboBoxEx:: Korzystanie CComboBoxEx

Wywołaj tę funkcję elementu członkowskiego, aby utworzyć `CComboBoxEx` obiekt.

```
CComboBoxEx();
```

## <a name="ccomboboxexcreate"></a><a name="create"></a> Korzystanie CComboBoxEx:: Create

Tworzy pole kombi i dołącza je do `CComboBoxEx` obiektu.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametry

*dwStyle*<br/>
Określa kombinację stylów pól kombi zastosowanych do pola kombi. Zobacz **uwagi** poniżej, aby uzyskać więcej informacji na temat stylów.

*cinania*<br/>
Odwołanie do obiektu [CRect](../../atl-mfc-shared/reference/crect-class.md) lub struktury [Rect](/windows/win32/api/windef/ns-windef-rect) , który jest pozycją i rozmiarem pola kombi.

*pParentWnd*<br/>
Wskaźnik do obiektu [CWnd](../../mfc/reference/cwnd-class.md) , który jest oknem nadrzędnym pola kombi (zwykle a `CDialog` ). Nie może mieć wartości NULL.

*nID*<br/>
Określa identyfikator kontrolki pola kombi.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli obiekt został utworzony pomyślnie; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Utwórz `CComboBoxEx` obiekt w dwóch krokach:

1. Wywołaj [Korzystanie CComboBoxEx](#ccomboboxex) w celu skonstruowania `CComboBoxEx` obiektu.

1. Wywołaj tę funkcję elementu członkowskiego, co spowoduje utworzenie rozszerzonego pola kombi systemu Windows i dołączenie go do `CComboBoxEx` obiektu.

Podczas wywoływania `Create` , MFC inicjuje formanty standardowe.

Po utworzeniu pola kombi można określić dowolne lub wszystkie następujące style pola kombi:

- CBS_SIMPLE

- CBS_DROPDOWN

- CBS_DROPDOWNLIST

- CBS_AUTOHSCROLL

- WS_CHILD

Wszystkie inne style przenoszone podczas tworzenia okna zostaną zignorowane. `ComboBoxEx`Kontrolka obsługuje również rozszerzone style, które udostępniają dodatkowe funkcje. Te [Style są opisane w Windows SDK](/windows/win32/Controls/comboboxex-control-extended-styles). Ustaw te style, wywołując metodę [setextended](#setextendedstyle).

Jeśli chcesz użyć rozszerzonych stylów systemu Windows z kontrolką, wywołaj [CreateEx](#createex) zamiast `Create` .

## <a name="ccomboboxexcreateex"></a><a name="createex"></a> Korzystanie CComboBoxEx:: CreateEx

Wywołaj tę funkcję, aby utworzyć kontrolkę rozszerzonego pola kombi (okno podrzędne) i skojarzyć ją z `CComboBoxEx` obiektem.

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
Styl kontrolki pola kombi. Aby uzyskać listę stylów, zobacz temat [Tworzenie](#create) .

*cinania*<br/>
Odwołanie do struktury [Rect](/windows/win32/api/windef/ns-windef-rect) opisujące rozmiar i położenie okna, które ma zostać utworzone, we współrzędnych klienta *pParentWnd*.

*pParentWnd*<br/>
Wskaźnik do okna, które jest elementem nadrzędnym formantu.

*nID*<br/>
Identyfikator okna podrzędnego kontrolki.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Użyj `CreateEx` zamiast `Create` , aby zastosować rozszerzone style systemu Windows, określone przez **WS_EX_** wstępny styl systemu Windows.

`CreateEx` tworzy formant przy użyciu rozszerzonych stylów systemu Windows określonych przez *dwExStyle*. Należy ustawić style rozszerzone charakterystyczne dla rozszerzonej kontrolki pola kombi przy użyciu metody [setextended](#setextendedstyle). Na przykład użyj, `CreateEx` Aby ustawić takie style jako WS_EX_CONTEXTHELP, ale użyć `SetExtendedStyle` do ustawienia takich stylów jako CBES_EX_CASESENSITIVE. Aby uzyskać więcej informacji, zobacz Style opisane w temacie [ComboBoxEx Control style rozszerzone](/windows/win32/Controls/comboboxex-control-extended-styles) w Windows SDK.

## <a name="ccomboboxexdeleteitem"></a><a name="deleteitem"></a> Korzystanie CComboBoxEx::D eleteItem

Usuwa element z `ComboBoxEx` formantu.

```
int DeleteItem(int iIndex);
```

### <a name="parameters"></a>Parametry

*iIndex*<br/>
Indeks elementu, który ma zostać usunięty (liczony od zera).

### <a name="return-value"></a>Wartość zwracana

Liczba pozostałych elementów w formancie. Jeśli *IIndex* jest nieprawidłowy, funkcja zwraca CB_ERR.

### <a name="remarks"></a>Uwagi

Ta funkcja członkowska implementuje funkcjonalność [CBEM_DELETEITEM](/windows/win32/Controls/cbem-deleteitem)komunikatu, zgodnie z opisem w Windows SDK. Po wywołaniu DeleteItem komunikat [WM_NOTIFY](/windows/win32/controls/wm-notify) z powiadomieniem CBEN_DELETEITEM zostanie wysłany do okna nadrzędnego.

## <a name="ccomboboxexgetcomboboxctrl"></a><a name="getcomboboxctrl"></a> Korzystanie CComboBoxEx:: GetComboBoxCtrl

Wywołaj tę funkcję elementu członkowskiego, aby uzyskać wskaźnik do kontrolki pola kombi w obrębie `CComboBoxEx` obiektu.

```
CComboBox* GetComboBoxCtrl();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do `CComboBox` obiektu.

### <a name="remarks"></a>Uwagi

`CComboBoxEx`Kontrolka składa się z okna nadrzędnego, które hermetyzuje `CComboBox` .

`CComboBox`Obiekt wskazywany przez wartość zwracaną jest obiektem tymczasowym i jest niszczony podczas następnego czasu bezczynności przetwarzania.

## <a name="ccomboboxexgeteditctrl"></a><a name="geteditctrl"></a> Korzystanie CComboBoxEx:: GetEditCtrl

Wywołaj tę funkcję elementu członkowskiego, aby uzyskać wskaźnik do kontrolki edycji pola kombi.

```
CEdit* GetEditCtrl();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do obiektu [CEdit](../../mfc/reference/cedit-class.md) .

### <a name="remarks"></a>Uwagi

`CComboBoxEx`Kontrolka używa pola edycji podczas tworzenia z stylem CBS_DROPDOWN.

`CEdit`Obiekt wskazywany przez wartość zwracaną jest obiektem tymczasowym i jest niszczony podczas następnego czasu bezczynności przetwarzania.

## <a name="ccomboboxexgetextendedstyle"></a><a name="getextendedstyle"></a> Korzystanie CComboBoxEx:: getextendeds

Wywołaj tę funkcję elementu członkowskiego, aby uzyskać style rozszerzone używane dla `CComboBoxEx` kontrolki.

```
DWORD GetExtendedStyle() const;
```

### <a name="return-value"></a>Wartość zwracana

Wartość DWORD, która zawiera rozszerzone style, które są używane dla kontrolki pole kombi.

### <a name="remarks"></a>Uwagi

Aby uzyskać więcej informacji o tych stylach, zobacz [ComboBoxEx Control extended style](/windows/win32/Controls/comboboxex-control-extended-styles) w Windows SDK.

## <a name="ccomboboxexgetimagelist"></a><a name="getimagelist"></a> Korzystanie CComboBoxEx:: GetImageList

Wywołaj tę funkcję elementu członkowskiego, aby uzyskać wskaźnik do listy obrazów używanej przez `CComboBoxEx` kontrolkę.

```
CImageList* GetImageList() const;
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do obiektu [Korzystanie CImageList](../../mfc/reference/cimagelist-class.md) . Jeśli to się nie powiedzie, funkcja członkowska zwraca wartość NULL.

### <a name="remarks"></a>Uwagi

`CImageList`Obiekt wskazywany przez wartość zwracaną jest obiektem tymczasowym i jest niszczony podczas następnego czasu bezczynności przetwarzania.

## <a name="ccomboboxexgetitem"></a><a name="getitem"></a> Korzystanie CComboBoxEx:: GetItem

Pobiera informacje o elemencie dla danego `ComboBoxEx` elementu.

```
BOOL GetItem(COMBOBOXEXITEM* pCBItem);
```

### <a name="parameters"></a>Parametry

*pCBItem*<br/>
Wskaźnik do struktury [COMBOBOXEXITEM](/windows/win32/api/commctrl/ns-commctrl-comboboxexitemw) , która będzie odbierać informacje o elemencie.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli operacja zakończyła się pomyślnie; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Ta funkcja członkowska implementuje funkcjonalność [CBEM_GETITEM](/windows/win32/Controls/cbem-getitem)komunikatu, zgodnie z opisem w Windows SDK.

## <a name="ccomboboxexhaseditchanged"></a><a name="haseditchanged"></a> Korzystanie CComboBoxEx:: HasEditChanged

Określa, czy użytkownik zmienił zawartość `ComboBoxEx` kontrolki edycji, wpisując ciąg.

```
BOOL HasEditChanged();
```

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli użytkownik wpisze pole edycji kontrolki; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Ta funkcja członkowska implementuje funkcjonalność [CBEM_HASEDITCHANGED](/windows/win32/Controls/cbem-haseditchanged)komunikatu, zgodnie z opisem w Windows SDK.

## <a name="ccomboboxexinsertitem"></a><a name="insertitem"></a> Korzystanie CComboBoxEx:: InsertItem

Wstawia nowy element w `ComboBoxEx` kontrolce.

```
int InsertItem(const COMBOBOXEXITEM* pCBItem);
```

### <a name="parameters"></a>Parametry

*pCBItem*<br/>
Wskaźnik do struktury [COMBOBOXEXITEM](/windows/win32/api/commctrl/ns-commctrl-comboboxexitemw) , która będzie odbierać informacje o elemencie. Ta struktura zawiera wartości flag wywołania zwrotnego dla elementu.

### <a name="return-value"></a>Wartość zwracana

Indeks, w którym wstawiono nowy element w przypadku powodzenia; w przeciwnym razie-1.

### <a name="remarks"></a>Uwagi

Po wywołaniu `InsertItem` , komunikat [WM_NOTIFY](/windows/win32/controls/wm-notify) z powiadomieniem [CBEN_INSERTITEM](/windows/win32/Controls/cben-insertitem) zostanie wysłany do okna nadrzędnego.

## <a name="ccomboboxexsetextendedstyle"></a><a name="setextendedstyle"></a> Korzystanie CComboBoxEx:: setextended

Wywołaj tę funkcję elementu członkowskiego, aby ustawić style rozszerzone używane dla rozszerzonej kontrolki pola kombi.

```
DWORD SetExtendedStyle(
    DWORD dwExMask,
    DWORD dwExStyles);
```

### <a name="parameters"></a>Parametry

*dwExMask*<br/>
Wartość DWORD wskazująca, których stylów w *dwExStyles* mają dotyczyć. Tylko style rozszerzone w *dwExMask* zostaną zmienione. Wszystkie inne style będą utrzymywane w postaci, w jakiej jest. Jeśli ten parametr ma wartość zero, wpłynie to na wszystkie style w *dwExStyles* .

*dwExStyles*<br/>
Wartość DWORD, która zawiera rozszerzone style kontrolki pola kombi do ustawienia dla kontrolki.

### <a name="return-value"></a>Wartość zwracana

Wartość DWORD, która zawiera style rozszerzone wcześniej używane dla formantu.

### <a name="remarks"></a>Uwagi

Aby uzyskać więcej informacji o tych stylach, zobacz [ComboBoxEx Control extended style](/windows/win32/Controls/comboboxex-control-extended-styles) w Windows SDK.

Aby utworzyć rozszerzoną kontrolkę pola kombi z rozszerzonymi stylami systemu Windows, użyj [CreateEx](#createex).

## <a name="ccomboboxexsetimagelist"></a><a name="setimagelist"></a> Korzystanie CComboBoxEx:: SetImageList

Ustawia listę obrazów dla `ComboBoxEx` kontrolki.

```
CImageList* SetImageList(CImageList* pImageList);
```

### <a name="parameters"></a>Parametry

*pImageList*<br/>
Wskaźnik do `CImageList` obiektu zawierającego obrazy, które mają być używane z `CComboBoxEx` kontrolką.

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do obiektu [Korzystanie CImageList](../../mfc/reference/cimagelist-class.md) zawierającego obrazy używane wcześniej przez `CComboBoxEx` formant. Wartość NULL, jeśli nie ustawiono wcześniej listy obrazów.

### <a name="remarks"></a>Uwagi

Ta funkcja członkowska implementuje funkcjonalność [CBEM_SETIMAGELIST](/windows/win32/Controls/cbem-setimagelist)komunikatu, zgodnie z opisem w Windows SDK. Jeśli zmienisz wysokość domyślnej kontrolki edycji, wywołaj funkcję Win32 [SetWindowPos](/windows/win32/api/winuser/nf-winuser-setwindowpos) , aby zmienić rozmiar kontrolki po wywołaniu `SetImageList` lub nie będzie wyświetlana prawidłowo.

`CImageList`Obiekt wskazywany przez wartość zwracaną jest obiektem tymczasowym i jest niszczony podczas następnego czasu bezczynności przetwarzania.

## <a name="ccomboboxexsetitem"></a><a name="setitem"></a> Korzystanie CComboBoxEx:: SetItem

Ustawia atrybuty dla elementu w `ComboBoxEx` kontrolce.

```
BOOL SetItem(const COMBOBOXEXITEM* pCBItem);
```

### <a name="parameters"></a>Parametry

*pCBItem*<br/>
Wskaźnik do struktury [COMBOBOXEXITEM](/windows/win32/api/commctrl/ns-commctrl-comboboxexitemw) , która będzie odbierać informacje o elemencie.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli operacja zakończyła się pomyślnie; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Ta funkcja członkowska implementuje funkcjonalność [CBEM_SETITEM](/windows/win32/Controls/cbem-setitem)komunikatu, zgodnie z opisem w Windows SDK.

## <a name="ccomboboxexsetwindowtheme"></a><a name="setwindowtheme"></a> Korzystanie CComboBoxEx:: SetWindowTheme

Ustawia styl wizualizacji rozszerzonej kontrolki pola kombi.

```
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```

### <a name="parameters"></a>Parametry

*pszSubAppName*<br/>
Wskaźnik do ciągu Unicode, który zawiera rozszerzony styl wizualny pola kombi do ustawienia.

### <a name="return-value"></a>Wartość zwracana

Wartość zwracana nie jest używana.

### <a name="remarks"></a>Uwagi

Ta funkcja członkowska emuluje funkcjonalność komunikatu [CBEM_SETWINDOWTHEME](/windows/win32/Controls/cbem-setwindowtheme) , zgodnie z opisem w Windows SDK.

## <a name="see-also"></a>Zobacz też

[Przykład MFCIE MFC](../../overview/visual-cpp-samples.md)<br/>
[Klasa CComboBox](../../mfc/reference/ccombobox-class.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasa CComboBox](../../mfc/reference/ccombobox-class.md)
