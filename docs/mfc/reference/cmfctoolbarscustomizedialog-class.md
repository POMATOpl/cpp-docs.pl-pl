---
description: 'Dowiedz się więcej na temat: Klasa CMFCToolBarsCustomizeDialog'
title: Klasa CMFCToolBarsCustomizeDialog
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarsCustomizeDialog
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::CMFCToolBarsCustomizeDialog
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::FillAllCommandsList
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::FillCategoriesComboBox
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::FillCategoriesListBox
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::GetCommandName
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::GetCountInCategory
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::GetFlags
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::OnInitDialog
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::PostNcDestroy
helpviewer_keywords:
- CMFCToolBarsCustomizeDialog [MFC], CMFCToolBarsCustomizeDialog
- CMFCToolBarsCustomizeDialog [MFC], FillAllCommandsList
- CMFCToolBarsCustomizeDialog [MFC], FillCategoriesComboBox
- CMFCToolBarsCustomizeDialog [MFC], FillCategoriesListBox
- CMFCToolBarsCustomizeDialog [MFC], GetCommandName
- CMFCToolBarsCustomizeDialog [MFC], GetCountInCategory
- CMFCToolBarsCustomizeDialog [MFC], GetFlags
- CMFCToolBarsCustomizeDialog [MFC], OnInitDialog
- CMFCToolBarsCustomizeDialog [MFC], PostNcDestroy
ms.assetid: 78e2cddd-4f13-4097-afc3-1ad646a113f1
ms.openlocfilehash: d05e94f614510c264e5916404abeeb6dfc4bea9a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143458"
---
# <a name="cmfctoolbarscustomizedialog-class"></a>Klasa CMFCToolBarsCustomizeDialog

Niemodalne okno dialogowe karty ( [Klasa CPropertySheet](../../mfc/reference/cpropertysheet-class.md)), które umożliwia użytkownikowi Dostosowywanie pasków narzędzi, menu, skrótów klawiaturowych, narzędzi zdefiniowanych przez użytkownika i stylów wizualnych w aplikacji. Zazwyczaj użytkownik uzyskuje dostęp do tego okna dialogowego, wybierając opcję **Dostosuj** w menu **Narzędzia** .

Okno dialogowe **Dostosowywanie** ma sześć kart: **polecenia**, **paski narzędzi**, **Narzędzia**, **Klawiatura**, **menu** i **Opcje**.

## <a name="syntax"></a>Składnia

```
class CMFCToolBarsCustomizeDialog : public CPropertySheet
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCToolBarsCustomizeDialog::CMFCToolBarsCustomizeDialog](#cmfctoolbarscustomizedialog)|Konstruuje `CMFCToolBarsCustomizeDialog` obiekt.|
|`CMFCToolBarsCustomizeDialog::~CMFCToolBarsCustomizeDialog`|Destruktor.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCToolBarsCustomizeDialog:: AddButton](#addbutton)|Wstawia przycisk paska narzędzi do listy poleceń na stronie **poleceń**|
|[CMFCToolBarsCustomizeDialog:: Add— menu](#addmenu)|Ładuje menu z zasobów i wywołań [CMFCToolBarsCustomizeDialog:: AddMenuCommands](#addmenucommands) , aby dodać to menu do listy poleceń na stronie **poleceń** .|
|[CMFCToolBarsCustomizeDialog::AddMenuCommands](#addmenucommands)|Ładuje menu z zasobów i wywołań [CMFCToolBarsCustomizeDialog:: AddMenuCommands](#addmenucommands) , aby dodać to menu do listy poleceń na stronie **poleceń** .|
|[CMFCToolBarsCustomizeDialog:: AddToolBar](#addtoolbar)|Ładuje pasek narzędzi z zasobów. Następnie dla każdego polecenia w menu wywołuje metodę [CMFCToolBarsCustomizeDialog:: AddButton](#addbutton) , aby wstawić przycisk na liście poleceń na stronie **poleceń** pod określoną kategorią.|
|[CMFCToolBarsCustomizeDialog:: Create](#create)|Wyświetla okno dialogowe **dostosowywania** .|
|`CMFCToolBarsCustomizeDialog::EnableTools`|Zarezerwowane do użytku w przyszłości.|
|[CMFCToolBarsCustomizeDialog::EnableUserDefinedToolbars](#enableuserdefinedtoolbars)|Włącza lub wyłącza tworzenie nowych pasków narzędzi przy użyciu okna dialogowego **Dostosowywanie** .|
|[CMFCToolBarsCustomizeDialog::FillAllCommandsList](#fillallcommandslist)|Wypełnia podany `CListBox` obiekt za pomocą poleceń w kategorii **wszystkie polecenia** .|
|[CMFCToolBarsCustomizeDialog::FillCategoriesComboBox](#fillcategoriescombobox)|Wypełnia podany `CComboBox` obiekt nazwą każdej kategorii poleceń w oknie dialogowym **Dostosowywanie** .|
|[CMFCToolBarsCustomizeDialog::FillCategoriesListBox](#fillcategorieslistbox)|Wypełnia podany `CListBox` obiekt nazwą każdej kategorii poleceń w oknie dialogowym **Dostosowywanie** .|
|[CMFCToolBarsCustomizeDialog:: getcommandname](#getcommandname)|Pobiera nazwę skojarzoną z danym IDENTYFIKATORem polecenia.|
|[CMFCToolBarsCustomizeDialog::GetCountInCategory](#getcountincategory)|Pobiera liczbę elementów z dostarczonej listy, które mają daną etykietę tekstową.|
|[CMFCToolBarsCustomizeDialog:: GetFlags](#getflags)|Pobiera zestaw flag, które mają wpływ na zachowanie okna dialogowego.|
|`CMFCToolBarsCustomizeDialog::GetThisClass`|Używane przez platformę do uzyskania wskaźnika do obiektu [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) , który jest skojarzony z tym typem klasy.|
|[CMFCToolBarsCustomizeDialog::OnEditToolbarMenuImage](#onedittoolbarmenuimage)|Uruchamia Edytor obrazów, dzięki czemu użytkownik może dostosować przycisk paska narzędzi lub ikonę elementu menu.|
|[CMFCToolBarsCustomizeDialog:: OnInitDialog](#oninitdialog)|Przesłania do inicjowania arkusza właściwości rozszerzonego. (Przesłania [CPropertySheet:: OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog).)|
|[CMFCToolBarsCustomizeDialog::P ostNcDestroy](#postncdestroy)|Wywoływane przez platformę po zniszczeniu okna. (Przesłania `CPropertySheet::PostNcDestroy`).|
|[CMFCToolBarsCustomizeDialog::RemoveButton](#removebutton)|Usuwa przycisk o określonym IDENTYFIKATORze polecenia z określonej kategorii lub we wszystkich kategoriach.|
|[CMFCToolBarsCustomizeDialog::RenameCategory](#renamecategory)|Zmienia nazwę kategorii w polu listy kategorii na karcie **polecenia** .|
|[CMFCToolBarsCustomizeDialog::ReplaceButton](#replacebutton)|Zastępuje przycisk na liście poleceń na karcie **polecenia** nowym obiektem przycisku paska narzędzi.|
|[CMFCToolBarsCustomizeDialog::SetUserCategory](#setusercategory)|Dodaje kategorię do listy kategorii, które będą wyświetlane na karcie **polecenia** .|

### <a name="protected-methods"></a>Metody chronione

|Nazwa|Opis|
|----------|-----------------|
|[CMFCToolBarsCustomizeDialog::CheckToolsValidity](#checktoolsvalidity)|Wywoływane przez platformę, aby określić, czy lista narzędzi zdefiniowanych przez użytkownika jest prawidłowa.|
|[CMFCToolBarsCustomizeDialog::OnAfterChangeTool](#onafterchangetool)|Wywoływane przez platformę, gdy zmienią się właściwości narzędzia zdefiniowanego przez użytkownika.|
|[CMFCToolBarsCustomizeDialog::OnAssignKey](#onassignkey)|Określa, czy do akcji można przypisać określony skrót klawiaturowy.|
|[CMFCToolBarsCustomizeDialog::OnBeforeChangeTool](#onbeforechangetool)|Określa, czy można zmienić narzędzie zdefiniowane przez użytkownika.|
|[CMFCToolBarsCustomizeDialog::OnInitToolsPage](#oninittoolspage)|Wywoływane przez platformę, gdy użytkownik wybierze żądaną kartę **Narzędzia** .|

## <a name="remarks"></a>Uwagi

Aby wyświetlić okno dialogowe **Dostosowywanie** , Utwórz `CMFCToolBarsCustomizeDialog` obiekt i Wywołaj metodę [CMFCToolBarsCustomizeDialog:: Create](#create) .

Gdy okno dialogowe **Dostosowywanie** jest aktywne, aplikacja działa w trybie specjalnym, który ogranicza użytkownika do dostosowywania zadań.

## <a name="example"></a>Przykład

Poniższy przykład ilustruje sposób użycia różnych metod w `CMFCToolBarsCustomizeDialog` klasie. W przykładzie pokazano, jak zastąpić przycisk paska narzędzi w polu listy poleceń na stronie **polecenia** , włączyć tworzenie nowych pasków narzędzi przy użyciu okna dialogowego **Dostosowywanie** i wyświetlić okno dialogowe **dostosowywania** . Ten fragment kodu jest częścią [przykładu demonstracyjnego](../../overview/visual-cpp-samples.md)dla programu IE.

[!code-cpp[NVC_MFC_IEDemo#4](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CPropertySheet](../../mfc/reference/cpropertysheet-class.md)

`CMFCToolBarsCustomizeDialog`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxToolBarsCustomizeDialog. h

## <a name="cmfctoolbarscustomizedialogaddbutton"></a><a name="addbutton"></a> CMFCToolBarsCustomizeDialog:: AddButton

Wstawia przycisk paska narzędzi do listy poleceń na stronie **poleceń** .

```cpp
void AddButton(
    UINT uiCategoryId,
    const CMFCToolBarButton& button,
    int iInsertBefore=-1);

void AddButton(
    LPCTSTR lpszCategory,
    const CMFCToolBarButton& button,
    int iInsertBefore=-1);
```

### <a name="parameters"></a>Parametry

*uiCategoryId*<br/>
podczas Określa identyfikator kategorii, do której ma zostać wstawiony przycisk.

*przycisk*<br/>
podczas Określa przycisk do wstawienia.

*iInsertBefore*<br/>
podczas Określa indeks (liczony od zera) przycisku paska narzędzi, przed którym zostanie wstawiony przycisk.

*lpszCategory*<br/>
podczas Określa ciąg kategorii, aby wstawić przycisk.

### <a name="remarks"></a>Uwagi

`AddButton`Metoda ignoruje przyciski, które mają standardowe identyfikatory poleceń (takie jak ID_FILE_MRU_FILE1), polecenia, które są niedozwolone (zobacz [CMFCToolBar:: IsCommandPermitted](../../mfc/reference/cmfctoolbar-class.md#iscommandpermitted)) i fikcyjne przyciski.

Ta metoda tworzy nowy obiekt tego samego typu co `button` (zazwyczaj [Klasa CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)) przy użyciu klasy środowiska uruchomieniowego przycisku. Następnie wywołuje [CMFCToolBarButton:: CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom) w celu skopiowania elementów członkowskich danych przycisku i Wstawia kopię do określonej kategorii.

Gdy nowy przycisk zostanie wstawiony, otrzymuje `OnAddToCustomizePage` powiadomienie.

Jeśli `iInsertBefore` jest-1, przycisk jest dołączany do listy kategorii; w przeciwnym razie jest wstawiany przed elementem o określonym indeksie.

### <a name="example"></a>Przykład

Poniższy przykład ilustruje sposób użycia `AddButton` metody `CMFCToolBarsCustomizeDialog` klasy. Ten fragment kodu jest częścią [próbki suwaka](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_Slider#1](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_2.cpp)]

## <a name="cmfctoolbarscustomizedialogaddmenu"></a><a name="addmenu"></a> CMFCToolBarsCustomizeDialog:: Add— menu

Ładuje menu z zasobów i wywołań [CMFCToolBarsCustomizeDialog:: AddMenuCommands](#addmenucommands) , aby dodać to menu do listy poleceń na stronie **poleceń** .

```
BOOL AddMenu(UINT uiMenuResId);
```

### <a name="parameters"></a>Parametry

*uiMenuResId*<br/>
podczas Określa identyfikator zasobu menu do załadowania.

### <a name="return-value"></a>Wartość zwracana

Wartość TRUE, jeśli menu zostało dodane pomyślnie; w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

W wywołaniu `AddMenuCommands` , *bPopup* ma wartość false. W związku z tym Metoda ta nie dodaje elementów menu zawierających podmenu do listy poleceń. Ta metoda powoduje dodanie elementów menu w podmenu do listy poleceń.

## <a name="cmfctoolbarscustomizedialogaddmenucommands"></a><a name="addmenucommands"></a> CMFCToolBarsCustomizeDialog::AddMenuCommands

Dodaje elementy do listy poleceń na stronie **polecenia** , aby reprezentować wszystkie elementy w określonym menu.

```cpp
void AddMenuCommands(
    const CMenu* pMenu,
    BOOL bPopup,
    LPCTSTR lpszCategory=NULL,
    LPCTSTR lpszMenuPath=NULL);
```

### <a name="parameters"></a>Parametry

*pMenu*<br/>
podczas Wskaźnik do obiektu CMenu, który ma zostać dodany.

*bPopup*<br/>
podczas Określa, czy elementy menu podręcznego mają być wstawiane do listy poleceń.

*lpszCategory*<br/>
podczas Nazwa kategorii, w której ma zostać wstawione menu.

*lpszMenuPath*<br/>
podczas Prefiks, który jest dodawany do nazwy, gdy polecenie jest wyświetlane na liście **wszystkie kategorie** .

### <a name="remarks"></a>Uwagi

`AddMenuCommands`Metoda pętle dla wszystkich elementów menu *pMenu*. Dla każdego elementu menu, który nie zawiera podmenu, ta metoda tworzy obiekt [klasy CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) i wywołuje metodę [CMFCToolBarsCustomizeDialog:: AddButton](#addbutton) , aby dodać element menu jako przycisk paska narzędzi do listy poleceń na stronie **poleceń** . Separatory są ignorowane w tym procesie.

Jeśli *bPopup* ma wartość true, dla każdego elementu menu, który zawiera podmenu, ta metoda tworzy obiekt [klasy CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md) i wstawia go do listy poleceń przez wywołanie `AddButton` . W przeciwnym razie elementy menu zawierające podmenu nie są wyświetlane na liście poleceń. W obu przypadkach, gdy `AddMenuCommands` napotka element menu z podmenu, wywołuje samo cyklicznie, przekazując wskaźnik do podmenu jako parametr *pMenu* i dołączając etykietę podmenu do *lpszMenuPath*.

## <a name="cmfctoolbarscustomizedialogaddtoolbar"></a><a name="addtoolbar"></a> CMFCToolBarsCustomizeDialog:: AddToolBar

Ładuje pasek narzędzi z zasobów. Następnie dla każdego polecenia w menu wywołuje metodę [CMFCToolBarsCustomizeDialog:: AddButton](#addbutton) , aby wstawić przycisk na liście poleceń na stronie **poleceń** pod określoną kategorią.

```
BOOL AddToolBar(
    UINT uiCategoryId,
    UINT uiToolbarResId);

BOOL AddToolBar(
    LPCTSTR lpszCategory,
    UINT uiToolbarResId);
```

### <a name="parameters"></a>Parametry

*uiCategoryId*<br/>
podczas Określa identyfikator zasobu kategorii, do którego ma zostać dodany pasek narzędzi.

*uiToolbarResId*<br/>
podczas Określa identyfikator zasobu paska narzędzi, którego polecenia są wstawiane do listy poleceń.

*lpszCategory*<br/>
podczas Określa nazwę kategorii, do której ma zostać dodany pasek narzędzi.

### <a name="return-value"></a>Wartość zwracana

Ma wartość TRUE, jeśli metoda zakończy się pomyślnie. w przeciwnym razie FALSE.

### <a name="example"></a>Przykład

Poniższy przykład ilustruje sposób użycia `AddToolBar` metody w `CMFCToolBarsCustomizeDialog` klasie. Ten fragment kodu jest częścią [przykładu Notatnika programu Word](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_WordPad#11](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_3.cpp)]

### <a name="remarks"></a>Uwagi

Formant, który jest używany do reprezentowania każdego polecenia, jest obiektem [klasy CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) . Po dodaniu paska narzędzi można zastąpić przycisk kontrolką typu pochodnego, wywołując [CMFCToolBarsCustomizeDialog:: ReplaceButton](#replacebutton).

## <a name="cmfctoolbarscustomizedialogchecktoolsvalidity"></a><a name="checktoolsvalidity"></a> CMFCToolBarsCustomizeDialog::CheckToolsValidity

Weryfikuje ważność listy narzędzi użytkownika.

```
virtual BOOL CheckToolsValidity(const CObList& lstTools);
```

### <a name="parameters"></a>Parametry

*lstTools*<br/>
podczas Lista narzędzi zdefiniowanych przez użytkownika do sprawdzenia.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość PRAWDA, jeśli lista narzędzi zdefiniowanych przez użytkownika jest prawidłowa; w przeciwnym razie FALSE. Domyślna implementacja zawsze zwraca wartość TRUE.

### <a name="remarks"></a>Uwagi

Struktura wywołuje tę metodę, aby sprawdzić poprawność obiektów, które reprezentują narzędzia zdefiniowane przez użytkownika zwrócone przez [CMFCToolBarsCustomizeDialog:: CheckToolsValidity](#checktoolsvalidity).

Zastąp `CheckToolsValidity` metodę klasą pochodną od, `CMFCToolBarsCustomizeDialog`  Jeśli chcesz sprawdzić poprawność narzędzi użytkownika przed zamknięciem okna dialogowego. Jeśli ta metoda zwróci wartość FALSE, gdy użytkownik kliknie przycisk **Zamknij** w prawym górnym rogu okna dialogowego lub przycisk zatytułowany **Zamknij** w prawym dolnym rogu okna dialogowego, w oknie dialogowym zostanie wyświetlona karta **Narzędzia** zamiast zamykania. Jeśli ta metoda zwróci wartość FALSE, gdy użytkownik kliknie kartę, aby opuścić ją z karty **Narzędzia** , nawigacja nie występuje. Należy wyświetlić odpowiednie okno komunikatu, aby poinformować użytkownika o problemie, który spowodował niepowodzenie walidacji.

## <a name="cmfctoolbarscustomizedialogcmfctoolbarscustomizedialog"></a><a name="cmfctoolbarscustomizedialog"></a> CMFCToolBarsCustomizeDialog::CMFCToolBarsCustomizeDialog

Konstruuje `CMFCToolBarsCustomizeDialog` obiekt.

```
CMFCToolBarsCustomizeDialog(
    CFrameWnd* pWndParentFrame,
    BOOL bAutoSetFromMenus = FALSE,
    UINT uiFlags = (AFX_CUSTOMIZE_MENU_SHADOWS | AFX_CUSTOMIZE_TEXT_LABELS | AFX_CUSTOMIZE_MENU_ANIMATIONS | AFX_CUSTOMIZE_NOHELP),
    CList <CRuntimeClass*, CRuntimeClass*>* p listCustomPages = NULL);
```

### <a name="parameters"></a>Parametry

*pWndParentFrame*<br/>
podczas Wskaźnik do ramki nadrzędnej. Ten parametr nie może mieć wartości NULL.

*bAutoSetFromMenus*<br/>
podczas Wartość logiczna określająca, czy dodać polecenia menu z wszystkich menu do listy poleceń na stronie **poleceń** . Jeśli ten parametr ma wartość TRUE, polecenia menu są dodawane. W przeciwnym razie polecenia menu nie są dodawane.

*uiFlags*<br/>
podczas Kombinacja flag mających wpływ na zachowanie okna dialogowego. Ten parametr może mieć co najmniej jedną z następujących wartości:

- AFX_CUSTOMIZE_MENU_SHADOWS

- AFX_CUSTOMIZE_TEXT_LABELS

- AFX_CUSTOMIZE_MENU_ANIMATIONS

- AFX_CUSTOMIZE_NOHELP

- AFX_CUSTOMIZE_CONTEXT_HELP

- AFX_CUSTOMIZE_NOTOOLS

- AFX_CUSTOMIZE_MENUAMPERS

- AFX_CUSTOMIZE_NO_LARGE_ICONS

*plistCustomPages*<br/>
podczas Wskaźnik do listy `CRuntimeClass` obiektów, które określają dodatkowe strony niestandardowe.

### <a name="remarks"></a>Uwagi

*PlistCustomPages* parametr odwołuje się do listy `CRuntimeClass` obiektów, które określają dodatkowe strony niestandardowe. Konstruktor dodaje więcej stron do okna dialogowego za pomocą metody [CRuntimeClass:: CreateObject](../../mfc/reference/cruntimeclass-structure.md#createobject) . Zobacz przykład CustomPages, aby dodać więcej stron do okna dialogowego **Dostosowywanie** .

Aby uzyskać więcej informacji na temat wartości, które można przekazać w parametrze *uiFlags* , zobacz [CMFCToolBarsCustomizeDialog:: GetFlags](#getflags).

### <a name="example"></a>Przykład

Poniższy przykład ilustruje sposób konstruowania obiektu `CMFCToolBarsCustomizeDialog` klasy. Ten fragment kodu jest częścią [przykładu stron niestandardowych](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_CustomPages#3](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_4.cpp)]

## <a name="cmfctoolbarscustomizedialogcreate"></a><a name="create"></a> CMFCToolBarsCustomizeDialog:: Create

Wyświetla okno dialogowe **dostosowywania** .

```
virtual BOOL Create();
```

### <a name="return-value"></a>Wartość zwracana

Ma wartość TRUE, jeśli arkusz właściwości dostosowania został utworzony pomyślnie. w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

Wywołaj `Create` metodę dopiero po całkowitym zainicjowaniu klasy.

## <a name="cmfctoolbarscustomizedialogenableuserdefinedtoolbars"></a><a name="enableuserdefinedtoolbars"></a> CMFCToolBarsCustomizeDialog::EnableUserDefinedToolbars

Włącza lub wyłącza tworzenie nowych pasków narzędzi przy użyciu okna dialogowego **Dostosowywanie** .

```cpp
void EnableUserDefinedToolbars(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametry

*bEnable*<br/>
podczas PRAWDA, aby włączyć paski narzędzi zdefiniowane przez użytkownika; Wartość FALSE powoduje wyłączenie pasków narzędzi.

### <a name="remarks"></a>Uwagi

Jeśli *bEnable* ma wartość true, przyciski **New**, **Rename** i **delete** są wyświetlane na stronie **paski narzędzi** .

Domyślnie, lub jeśli *bEnable* ma wartość false, te przyciski nie są wyświetlane, a użytkownik nie może definiować nowych pasków narzędzi.

## <a name="cmfctoolbarscustomizedialogfillallcommandslist"></a><a name="fillallcommandslist"></a> CMFCToolBarsCustomizeDialog::FillAllCommandsList

Wypełnia podany `CListBox` obiekt za pomocą poleceń w kategorii **wszystkie polecenia** .

```
virtual void FillAllCommandsList(CListBox& wndListOfCommands) const;
```

### <a name="parameters"></a>Parametry

*wndListOfCommands*<br/>
określoną Odwołanie do `CListBox` obiektu do wypełnienia.

### <a name="remarks"></a>Uwagi

Kategoria **wszystkie polecenia** zawiera polecenia wszystkich kategorii. Metoda [CMFCToolBarsCustomizeDialog:: AddButton](#addbutton) dodaje polecenie skojarzone z udostępnionym przyciskiem do kategorii **wszystkie polecenia** .

Ta metoda czyści zawartość podanego `CListBox` obiektu przed wypełnieniem go za pomocą poleceń w kategorii **wszystkie polecenia** .

`CMFCMousePropertyPage`Klasa używa tej metody do wypełnienia pola listy zdarzeń dwukrotnego kliknięcia.

## <a name="cmfctoolbarscustomizedialogfillcategoriescombobox"></a><a name="fillcategoriescombobox"></a> CMFCToolBarsCustomizeDialog::FillCategoriesComboBox

Wypełnia podany `CComboBox` obiekt nazwą każdej kategorii poleceń w oknie dialogowym **Dostosowywanie** .

```cpp
void FillCategoriesComboBox(
    CComboBox& wndCategory,
    BOOL bAddEmpty = TRUE) const;
```

### <a name="parameters"></a>Parametry

*wndCategory*<br/>
określoną Odwołanie do `CComboBox` obiektu do wypełnienia.

*bAddEmpty*<br/>
podczas Wartość logiczna określająca, czy dodać kategorie do pola kombi, które nie ma poleceń. Jeśli ten parametr ma wartość TRUE, do pola kombi dodawane są puste kategorie. W przeciwnym razie puste kategorie nie są dodawane.

### <a name="remarks"></a>Uwagi

Ta metoda jest taka sama jak Metoda [CMFCToolBarsCustomizeDialog:: FillCategoriesListBox](#fillcategorieslistbox) , z tą różnicą, że ta metoda działa z `CComboBox` obiektem.

Ta metoda nie czyści zawartości `CComboBox` obiektu przed jego wypełnieniem. Gwarantuje, że Kategoria **wszystkie polecenia** jest ostatnim elementem w polu kombi.

Nowe kategorie poleceń można dodać za pomocą metody [CMFCToolBarsCustomizeDialog:: AddButton](#addbutton) . Można zmienić nazwę istniejącej kategorii za pomocą metody [CMFCToolBarsCustomizeDialog:: RenameCategory](#renamecategory) .

`CMFCToolBarsKeyboardPropertyPage`Klasy i `CMFCKeyMapDialog` używają tej metody do kategoryzowania mapowań klawiatury.

## <a name="cmfctoolbarscustomizedialogfillcategorieslistbox"></a><a name="fillcategorieslistbox"></a> CMFCToolBarsCustomizeDialog::FillCategoriesListBox

Wypełnia podany `CListBox` obiekt nazwą każdej kategorii poleceń w oknie dialogowym **Dostosowywanie** .

```cpp
void FillCategoriesListBox(
    CListBox& wndCategory,
    BOOL bAddEmpty = TRUE) const;
```

### <a name="parameters"></a>Parametry

*wndCategory*<br/>
określoną Odwołanie do `CListBox` obiektu do wypełnienia.

*bAddEmpty*<br/>
podczas Wartość logiczna określająca, czy dodać kategorie do pola listy, które nie mają poleceń. Jeśli ten parametr ma wartość TRUE, do pola listy dodawane są puste kategorie. W przeciwnym razie puste kategorie nie są dodawane.

### <a name="remarks"></a>Uwagi

Ta metoda jest taka sama jak Metoda [CMFCToolBarsCustomizeDialog:: FillCategoriesComboBox](#fillcategoriescombobox) , z tą różnicą, że ta metoda działa z `CListBox` obiektem.

Ta metoda nie czyści zawartości `CListBox` obiektu przed jego wypełnieniem. Gwarantuje, że Kategoria **wszystkie polecenia** jest ostatnim elementem w polu listy.

Nowe kategorie poleceń można dodać za pomocą metody [CMFCToolBarsCustomizeDialog:: AddButton](#addbutton) . Można zmienić nazwę istniejącej kategorii za pomocą metody [CMFCToolBarsCustomizeDialog:: RenameCategory](#renamecategory) .

`CMFCToolBarsCommandsPropertyPage`Klasa używa tej metody do wyświetlania listy poleceń skojarzonych z poszczególnymi kategoriami poleceń.

## <a name="cmfctoolbarscustomizedialoggetcommandname"></a><a name="getcommandname"></a> CMFCToolBarsCustomizeDialog:: getcommandname

Pobiera nazwę skojarzoną z danym IDENTYFIKATORem polecenia.

```
LPCTSTR GetCommandName(UINT uiCmd) const;
```

### <a name="parameters"></a>Parametry

*uiCmd*<br/>
podczas Identyfikator polecenia do pobrania.

### <a name="return-value"></a>Wartość zwracana

Nazwa, która jest skojarzona z danym IDENTYFIKATORem polecenia lub ma wartość NULL, jeśli polecenie nie istnieje.

## <a name="cmfctoolbarscustomizedialoggetcountincategory"></a><a name="getcountincategory"></a> CMFCToolBarsCustomizeDialog::GetCountInCategory

Pobiera liczbę elementów z dostarczonej listy, które mają daną etykietę tekstową.

```
int GetCountInCategory(
    LPCTSTR lpszItemName,
    const CObList& lstCommands) const;
```

### <a name="parameters"></a>Parametry

*lpszItemName*<br/>
podczas Etykieta tekstowa do dopasowania.

*lstCommands*<br/>
podczas Odwołanie do listy zawierającej `CMFCToolBarButton` obiekty.

### <a name="return-value"></a>Wartość zwracana

Liczba elementów na podanej liście, których etykieta tekstowa jest równa *lpszItemName*.

### <a name="remarks"></a>Uwagi

Każdy element na liście obiektów podanej musi być typu `CMFCToolBarButton` . Ta metoda porównuje *lpszItemName* z elementem członkowskim danych [CMFCToolBarButton:: m_strText](../../mfc/reference/cmfctoolbarbutton-class.md#m_strtext) .

## <a name="cmfctoolbarscustomizedialoggetflags"></a><a name="getflags"></a> CMFCToolBarsCustomizeDialog:: GetFlags

Pobiera zestaw flag, które mają wpływ na zachowanie okna dialogowego.

```
UINT GetFlags() const;
```

### <a name="return-value"></a>Wartość zwracana

Zestaw flag, które mają wpływ na zachowanie okna dialogowego.

### <a name="remarks"></a>Uwagi

Ta metoda pobiera wartość parametru *uiFlags* , który jest przesyłany do konstruktora. Zwracana wartość może być jedną z następujących wartości:

|Nazwa|Opis|
|-|-|
|AFX_CUSTOMIZE_MENU_SHADOWS|Zezwala użytkownikowi na określenie wyglądu w tle menu.  |
|AFX_CUSTOMIZE_TEXT_LABELS|Umożliwia użytkownikowi określenie, czy etykiety tekstowe są wyświetlane pod obrazami przycisków paska narzędzi.  |
|AFX_CUSTOMIZE_MENU_ANIMATIONS|Zezwala użytkownikowi na określenie stylu animacji menu.  |
|AFX_CUSTOMIZE_NOHELP|Usuwa przycisk Pomoc w oknie dialogowym dostosowywania.  |
|AFX_CUSTOMIZE_CONTEXT_HELP|Włącza styl wizualizacji WS_EX_CONTEXTHELP.  |
|AFX_CUSTOMIZE_NOTOOLS|Usuwa stronę **Narzędzia** z okna dialogowego Dostosowywanie. Ta flaga jest prawidłowa, jeśli aplikacja używa `CUserToolsManager` klasy.  |
|AFX_CUSTOMIZE_MENUAMPERS|Zezwala na podpisy przycisków, aby zawierały znak handlowego "i" **&** .  |
|AFX_CUSTOMIZE_NO_LARGE_ICONS|Usuwa opcję **dużych ikon** z okna dialogowego Dostosowywanie.  |

Aby uzyskać więcej informacji na temat WS_EX_CONTEXTHELP stylu wizualizacji, zobacz [Rozszerzone style okien](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles).

## <a name="cmfctoolbarscustomizedialogonafterchangetool"></a><a name="onafterchangetool"></a> CMFCToolBarsCustomizeDialog::OnAfterChangeTool

Reaguje na zmianę w narzędziu użytkownika natychmiast po jej wystąpieniu.

```
virtual void OnAfterChangeTool(CUserTool* pSelTool);
```

### <a name="parameters"></a>Parametry

*pSelTool*<br/>
[in. out] Wskaźnik do obiektu narzędzia użytkownika, który został zmieniony.

### <a name="remarks"></a>Uwagi

Ta metoda jest wywoływana przez platformę, gdy użytkownik zmienia właściwości narzędzia zdefiniowanego przez użytkownika. Domyślna implementacja nie robi nic. Zastąp tę metodę w klasie pochodzącej od `CMFCToolBarsCustomizeDialog`  , aby wykonać przetwarzanie po wystąpieniu zmiany w narzędziu użytkownika.

## <a name="cmfctoolbarscustomizedialogonassignkey"></a><a name="onassignkey"></a> CMFCToolBarsCustomizeDialog::OnAssignKey

Weryfikuje skróty klawiaturowe w miarę ich definiowania przez użytkownika.

```
virtual BOOL OnAssignKey(ACCEL* pAccel);
```

### <a name="parameters"></a>Parametry

*pAccel*<br/>
[in. out] Wskaźnik do proponowanej przypisania klawiatury, który jest wyrażony jako struktura [akceleracja](/windows/win32/api/winuser/ns-winuser-accel) .

### <a name="return-value"></a>Wartość zwracana

Ma wartość TRUE, jeśli można przypisać klucz lub wartość FALSE, jeśli nie można przypisać klucza. Domyślna implementacja zawsze zwraca wartość TRUE.

### <a name="remarks"></a>Uwagi

Zastąp tę metodę w klasie pochodnej, aby wykonać dodatkowe przetwarzanie, gdy użytkownik przypisze nowy skrót klawiaturowy lub aby sprawdzić, czy skróty klawiaturowe są zdefiniowane przez użytkownika. Aby zapobiec przypisaniu skrótu, zwróć wartość FALSE. Należy również wyświetlić okno komunikatu lub w inny sposób poinformować użytkownika o przyczynie odrzucenia skrótu klawiaturowego.

## <a name="cmfctoolbarscustomizedialogonbeforechangetool"></a><a name="onbeforechangetool"></a> CMFCToolBarsCustomizeDialog::OnBeforeChangeTool

Wykonuje niestandardowe przetwarzanie w przypadku zmiany w narzędziu użytkownika, gdy użytkownik zamierza zastosować zmianę.

```
virtual void OnBeforeChangeTool(CUserTool* pSelTool);
```

### <a name="parameters"></a>Parametry

*pSelTool*<br/>
[in. out] Wskaźnik do obiektu narzędzia użytkownika, który ma zostać zastąpiony.

### <a name="remarks"></a>Uwagi

Ta metoda jest wywoływana przez platformę, gdy właściwości narzędzia zdefiniowanego przez użytkownika zostaną zmienione. Domyślna implementacja nie robi nic. Zastąp `OnBeforeChangeTool` metodę w klasie pochodnej `CMFCToolBarsCustomizeDialog`  , jeśli chcesz przeprowadzić przetwarzanie przed wprowadzeniem zmiany w narzędziu użytkownika, na przykład zwalniając zasoby używane przez *pSelTool* .

## <a name="cmfctoolbarscustomizedialogonedittoolbarmenuimage"></a><a name="onedittoolbarmenuimage"></a> CMFCToolBarsCustomizeDialog::OnEditToolbarMenuImage

Uruchamia Edytor obrazów, dzięki czemu użytkownik może dostosować przycisk paska narzędzi lub ikonę elementu menu.

```
virtual BOOL OnEditToolbarMenuImage(
    CWnd* pWndParent,
    CBitmap& bitmap,
    int nBitsPerPixel);
```

### <a name="parameters"></a>Parametry

*pWndParent*<br/>
podczas Wskaźnik do okna nadrzędnego.

*mapy*<br/>
podczas Odwołanie do obiektu mapy bitowej, który ma być edytowany.

*nBitsPerPixel*<br/>
podczas Rozdzielczość koloru mapy bitowej w bitach na piksel.

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli zmiana jest zatwierdzana; w przeciwnym razie FALSE. Domyślna implementacja Wyświetla okno dialogowe i zwraca wartość PRAWDA, jeśli użytkownik kliknie przycisk **OK**, lub wartość FAŁSZ, jeśli użytkownik kliknie przycisk **Anuluj** lub **Zamknij** .

### <a name="remarks"></a>Uwagi

Ta metoda jest wywoływana przez platformę, gdy użytkownik uruchamia edytora obrazu. Domyślna implementacja Wyświetla okno dialogowe [Klasa CMFCImageEditorDialog](../../mfc/reference/cmfcimageeditordialog-class.md) . Przesłoń `OnEditToolbarMenuImage` w klasie pochodnej, aby użyć niestandardowego edytora obrazów.

## <a name="cmfctoolbarscustomizedialogoninitdialog"></a><a name="oninitdialog"></a> CMFCToolBarsCustomizeDialog:: OnInitDialog

Przesłania do inicjowania arkusza właściwości rozszerzonego.

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>Wartość zwracana

Wynik wywołania metody [CPropertySheet:: OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog) .

### <a name="remarks"></a>Uwagi

Ta metoda rozszerza implementację klasy bazowej, [CPropertySheet:: OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog), wyświetlając przycisk **Close** , przez upewnienie się, że okno dialogowe pasuje do bieżącego rozmiaru ekranu i przez przeniesienie przycisku **Pomoc** do lewego dolnego rogu okna dialogowego.

## <a name="cmfctoolbarscustomizedialogoninittoolspage"></a><a name="oninittoolspage"></a> CMFCToolBarsCustomizeDialog::OnInitToolsPage

Obsługuje powiadomienie z platformy, która zostanie zainicjowana na stronie **Narzędzia** .

```
virtual void OnInitToolsPage();
```

### <a name="remarks"></a>Uwagi

Domyślna implementacja nie robi nic. Zastąp tę metodę w klasie pochodnej, aby przetworzyć to powiadomienie.

## <a name="cmfctoolbarscustomizedialogpostncdestroy"></a><a name="postncdestroy"></a> CMFCToolBarsCustomizeDialog::P ostNcDestroy

Wywoływane przez platformę po zniszczeniu okna.

```
virtual void PostNcDestroy();
```

### <a name="remarks"></a>Uwagi

Ta metoda rozszerza implementację klasy bazowej, `CPropertySheet::PostNcDestroy` przez przywrócenie aplikacji do poprzedniego trybu.

Metoda [CMFCToolBarsCustomizeDialog:: Create](#create) umieszcza aplikację w trybie specjalnym, który ogranicza użytkownika do dostosowywania zadań.

## <a name="cmfctoolbarscustomizedialogremovebutton"></a><a name="removebutton"></a> CMFCToolBarsCustomizeDialog::RemoveButton

Usuwa przycisk o określonym IDENTYFIKATORze polecenia z określonej kategorii lub we wszystkich kategoriach.

```
int RemoveButton(
    UINT uiCategoryId,
    UINT uiCmdId);

int RemoveButton(
    LPCTSTR lpszCategory,
    UINT uiCmdId);
```

### <a name="parameters"></a>Parametry

*uiCategoryId*<br/>
podczas Określa identyfikator kategorii, z którego ma zostać usunięty przycisk.

*uiCmdId*<br/>
podczas Określa identyfikator polecenia przycisku.

*lpszCategory*<br/>
podczas Określa nazwę kategorii, z której ma zostać usunięty przycisk.

### <a name="return-value"></a>Wartość zwracana

Indeks (liczony od zera) przycisku usuniętego lub-1, jeśli określony identyfikator polecenia nie został znaleziony w określonej kategorii. Jeśli *uiCategoryId* wynosi-1, wartość zwracana wynosi 0.

### <a name="remarks"></a>Uwagi

Aby usunąć przycisk ze wszystkich kategorii, wywołaj pierwsze Przeciążenie tej metody i ustaw *uiCategoryId* na-1.

## <a name="cmfctoolbarscustomizedialogrenamecategory"></a><a name="renamecategory"></a> CMFCToolBarsCustomizeDialog::RenameCategory

Zmienia nazwę kategorii w polu listy kategorii na stronie **polecenia** .

```
BOOL RenameCategory(
    LPCTSTR lpszCategoryOld,
    LPCTSTR lpszCategoryNew);
```

### <a name="parameters"></a>Parametry

*lpszCategoryOld*<br/>
podczas Nazwa kategorii do zmiany.

*lpszCategoryNew*<br/>
podczas Nazwa nowej kategorii.

### <a name="return-value"></a>Wartość zwracana

Ma wartość TRUE, jeśli metoda zakończyła się pomyślnie. w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

Nazwa kategorii musi być unikatowa.

## <a name="cmfctoolbarscustomizedialogreplacebutton"></a><a name="replacebutton"></a> CMFCToolBarsCustomizeDialog::ReplaceButton

Zastępuje przycisk paska narzędzi w polu listy poleceń na stronie **polecenia** .

```cpp
void ReplaceButton(
    UINT uiCmd,
    const CMFCToolBarButton& button);
```

### <a name="parameters"></a>Parametry

*uiCmd*<br/>
podczas Określa polecenie, które ma zostać zastąpione.

*przycisk*<br/>
podczas **`const`** Odwołanie do obiektu przycisku paska narzędzi, który zastępuje stary przycisk.

### <a name="remarks"></a>Uwagi

Gdy [CMFCToolBarsCustomizeDialog:: AddMenu](#addmenu), [CMFCToolBarsCustomizeDialog:: AddMenuCommands](#addmenucommands)lub [CMFCToolBarsCustomizeDialog:: AddToolBar](#addtoolbar) dodaje polecenie do strony **Commands** , to polecenie jest w postaci obiektu [klasy CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) (lub obiektu [klasy CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md) dla elementu menu zawierającego podmenu dodane przez `AddMenuCommands` ). Struktura wywołuje również te trzy metody, aby automatycznie dodawać polecenia. Jeśli chcesz, aby polecenie było reprezentowane przez typ pochodny, wywołaj `ReplaceButton` i Przekaż na przycisk typu pochodnego.

### <a name="example"></a>Przykład

Poniższy przykład ilustruje sposób użycia `ReplaceButton` metody w `CMFCToolBarsCustomizeDialog` klasie. Ten fragment kodu jest częścią [przykładu demonstracyjnego Visual Studio](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_VisualStudioDemo#34](../../mfc/codesnippet/cpp/cmfctoolbarscustomizedialog-class_5.cpp)]

## <a name="cmfctoolbarscustomizedialogsetusercategory"></a><a name="setusercategory"></a> CMFCToolBarsCustomizeDialog::SetUserCategory

Określa, która kategoria na liście kategorii na stronie **poleceń** jest kategorią użytkownika. Musisz wywołać tę funkcję przed wywołaniem [CMFCToolBarsCustomizeDialog:: Create](#create).

```
BOOL SetUserCategory(LPCTSTR lpszCategory);
```

### <a name="parameters"></a>Parametry

*lpszCategory*<br/>
podczas Nazwa kategorii.

### <a name="return-value"></a>Wartość zwracana

Ma wartość TRUE, jeśli metoda zakończy się pomyślnie. w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

Ustawienie kategorii użytkownika nie jest obecnie używane przez platformę.

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CPropertySheet](../../mfc/reference/cpropertysheet-class.md)
