---
description: 'Dowiedz się więcej na temat: Klasa CMFCRibbonQuickAccessToolBarDefaultState'
title: Klasa CMFCRibbonQuickAccessToolBarDefaultState
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonQuickAccessToolBarDefaultState
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState::CMFCRibbonQuickAccessToolBarDefaultState
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState::AddCommand
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState::CopyFrom
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState::RemoveAll
helpviewer_keywords:
- CMFCRibbonQuickAccessToolBarDefaultState [MFC], CMFCRibbonQuickAccessToolBarDefaultState
- CMFCRibbonQuickAccessToolBarDefaultState [MFC], AddCommand
- CMFCRibbonQuickAccessToolBarDefaultState [MFC], CopyFrom
- CMFCRibbonQuickAccessToolBarDefaultState [MFC], RemoveAll
ms.assetid: eca99200-b87b-47ba-b2e8-2f3f2444b176
ms.openlocfilehash: d6cd0c32cd8698259de0a78a6a6a7dc42012e92f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321808"
---
# <a name="cmfcribbonquickaccesstoolbardefaultstate-class"></a>Klasa CMFCRibbonQuickAccessToolBarDefaultState

Klasa pomocnika, która zarządza stanem domyślnym dla paska narzędzi Szybki dostęp, który jest ustawiony na pasku wstążki ( [Klasa CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md)).

## <a name="syntax"></a>Składnia

```
class CMFCRibbonQuickAccessToolBarDefaultState
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCRibbonQuickAccessToolBarDefaultState::CMFCRibbonQuickAccessToolBarDefaultState](#cmfcribbonquickaccesstoolbardefaultstate)|Konstruuje `CMFCRibbonQuickAccessToolbarDefaultState` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCRibbonQuickAccessToolBarDefaultState:: Add— polecenie](#addcommand)|Dodaje polecenie do domyślnego stanu paska narzędzi Szybki dostęp. Nie powoduje to zmiany samego paska narzędzi.|
|[CMFCRibbonQuickAccessToolBarDefaultState::CopyFrom](#copyfrom)|Kopiuje właściwości jednego paska narzędzi Szybki dostęp do innego.|
|[CMFCRibbonQuickAccessToolBarDefaultState::](#removeall)|Usuwa wszystkie polecenia z paska narzędzi Szybki dostęp. Nie powoduje to zmiany samego paska narzędzi.|

## <a name="remarks"></a>Uwagi

Po utworzeniu paska narzędzi Szybki dostęp w aplikacji zalecamy ustawienie jego stanu domyślnego przez wywołanie [CMFCRibbonBar:: SetQuickAccessDefaultState](../../mfc/reference/cmfcribbonbar-class.md#setquickaccessdefaultstate). Ten stan domyślny jest przywracany, gdy użytkownik kliknie przycisk **Resetuj** na stronie **Dostosowywanie** w oknie dialogowym **Opcje** aplikacji.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CMFCRibbonQuickAccessToolBarDefaultState](../../mfc/reference/cmfcribbonquickaccesstoolbardefaultstate-class.md)

## <a name="example"></a>Przykład

Poniższy przykład ilustruje sposób konstruowania obiektu `CMFCRibbonQuickAccessToolbarDefaultState` klasy i sposób dodawania polecenia do stanu domyślnego paska narzędzi Szybki dostęp.

[!code-cpp[NVC_MFC_RibbonApp#21](../../mfc/reference/codesnippet/cpp/cmfcribbonquickaccesstoolbardefaultstate-class_1.cpp)]

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxribbonquickaccesstoolbar. h

## <a name="cmfcribbonquickaccesstoolbardefaultstateaddcommand"></a><a name="addcommand"></a> CMFCRibbonQuickAccessToolBarDefaultState:: Add— polecenie

Dodaje polecenie do domyślnego stanu paska narzędzi Szybki dostęp.

```cpp
void AddCommand(
    UINT uiCmd,
    BOOL bIsVisible=TRUE);
```

### <a name="parameters"></a>Parametry

*[in] uiCmd*<br/>
Określa identyfikator polecenia.

*[in] bIsVisible*<br/>
Ustawia widoczność polecenia, gdy pasek narzędzi Szybki dostęp jest w stanie domyślnym.

### <a name="remarks"></a>Uwagi

Dodanie polecenia do CMFCRibbonQuickAccessToolBarDefaultState daje trzy wyniki. Najpierw Każde dodane polecenie jest wyświetlane na liście rozwijanej po prawej stronie paska narzędzi Szybki dostęp. W ten sposób użytkownik może łatwo dodać lub usunąć to polecenie z paska narzędzi Szybki dostęp. Po drugie pasek narzędzi Szybki dostęp jest resetowany, aby pokazać tylko te polecenia, które są wyświetlane jako widoczne w stanie domyślnym, gdy użytkownik kliknie przycisk **Resetuj** w oknie dialogowym **Dostosuj** . Trzeci, jeśli nie został wywołany [CMFCRibbonBar:: SetQuickAccessCommands](../../mfc/reference/cmfcribbonbar-class.md#setquickaccesscommands), pasek narzędzi Szybki dostęp używa widocznych poleceń z tej listy jako domyślnych poleceń widocznych podczas pierwszego uruchomienia aplikacji przez użytkownika. Po dodaniu wszystkich żądanych poleceń Wywołaj [CMFCRibbonBar:: SetQuickAccessDefaultState](../../mfc/reference/cmfcribbonbar-class.md#setquickaccessdefaultstate) , aby ustawić to wystąpienie jako stan domyślny dla paska narzędzi Szybki dostęp na tym pasku wstążki.

## <a name="cmfcribbonquickaccesstoolbardefaultstatecopyfrom"></a><a name="copyfrom"></a> CMFCRibbonQuickAccessToolBarDefaultState::CopyFrom

Kopiuje właściwości jednego paska narzędzi Szybki dostęp do innego.

```cpp
void CopyFrom(const CMFCRibbonQuickAccessToolBarDefaultState& src);
```

### <a name="parameters"></a>Parametry

*src*<br/>
podczas Odwołanie do `CMFCRibbonQuickAccessToolBarDefaultState` obiektu źródłowego do skopiowania.

### <a name="remarks"></a>Uwagi

Ta metoda kopiuje każde polecenie z obiektu źródłowego `CMFCRibbonQuickAccessToolBarDefaultState` do tego obiektu za pomocą metody [CMFCRibbonQuickAccessToolBarDefaultState:: AddCommand](#addcommand) .

## <a name="cmfcribbonquickaccesstoolbardefaultstatecmfcribbonquickaccesstoolbardefaultstate"></a><a name="cmfcribbonquickaccesstoolbardefaultstate"></a> CMFCRibbonQuickAccessToolBarDefaultState::CMFCRibbonQuickAccessToolBarDefaultState

Tworzy obiekt domyślnego stanu paska narzędzi Szybki dostęp.

```
CMFCRibbonQuickAccessToolBarDefaultState();
```

### <a name="remarks"></a>Uwagi

Domyślnie lista poleceń, które zawiera nowe wystąpienie elementu [CMFRibbonQuickAccessToolBarDefaultState](../../mfc/reference/cmfcribbonquickaccesstoolbardefaultstate-class.md) , jest pusta.

## <a name="cmfcribbonquickaccesstoolbardefaultstateremoveall"></a><a name="removeall"></a> CMFCRibbonQuickAccessToolBarDefaultState::

Czyści listę poleceń domyślnych na pasku narzędzi Szybki dostęp.

```cpp
void RemoveAll();
```

### <a name="remarks"></a>Uwagi

Ta funkcja usuwa z tego wystąpienia wszystkie polecenia, które zostały dodane przez poprzednie wywołanie [CMFCRibbonQuickAccessToolBarDefaultState:: AddCommand](#addcommand) .

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md)
