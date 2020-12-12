---
description: 'Dowiedz się więcej na temat: Klasa CCmdUI'
title: Klasa CCmdUI
ms.date: 09/06/2019
f1_keywords:
- CCmdUI
- AFXWIN/CCmdUI
- AFXWIN/CCmdUI::ContinueRouting
- AFXWIN/CCmdUI::Enable
- AFXWIN/CCmdUI::SetCheck
- AFXWIN/CCmdUI::SetRadio
- AFXWIN/CCmdUI::SetText
- AFXWIN/CCmdUI::m_nID
- AFXWIN/CCmdUI::m_nIndex
- AFXWIN/CCmdUI::m_pMenu
- AFXWIN/CCmdUI::m_pOther
- AFXWIN/CCmdUI::m_pSubMenu
helpviewer_keywords:
- CCmdUI [MFC], ContinueRouting
- CCmdUI [MFC], Enable
- CCmdUI [MFC], SetCheck
- CCmdUI [MFC], SetRadio
- CCmdUI [MFC], SetText
- CCmdUI [MFC], m_nID
- CCmdUI [MFC], m_nIndex
- CCmdUI [MFC], m_pMenu
- CCmdUI [MFC], m_pOther
- CCmdUI [MFC], m_pSubMenu
ms.assetid: 04eaaaf5-f510-48ab-b425-94665ba24766
ms.openlocfilehash: d868c0dc3c9915f5300f56e5bfa5f1971d4ec3ff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97132993"
---
# <a name="ccmdui-class"></a>Klasa CCmdUI

Jest używany tylko wewnątrz `ON_UPDATE_COMMAND_UI` procedury obsługi w `CCmdTarget` klasie pochodnej.

## <a name="syntax"></a>Składnia

```
class CCmdUI
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CCmdUI:: ContinueRouting](#continuerouting)|Informuje mechanizm routingu poleceń, aby kontynuować kierowanie bieżącego komunikatu do łańcucha programów obsługi.|
|[CCmdUI:: Enable](#enable)|Włącza lub wyłącza element interfejsu użytkownika dla tego polecenia.|
|[CCmdUI:: SetCheck](#setcheck)|Ustawia stan sprawdzania elementu User-Interface dla tego polecenia.|
|[CCmdUI:: SetRadio](#setradio)|Podobnie jak `SetCheck` funkcja członkowska, ale działa w grupach radiowych.|
|[CCmdUI:: SetText](#settext)|Ustawia tekst dla elementu interfejsu użytkownika dla tego polecenia.|

### <a name="public-data-members"></a>Publiczne elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CCmdUI:: m_nID](#m_nid)|Identyfikator obiektu interfejsu użytkownika.|
|[CCmdUI:: m_nIndex](#m_nindex)|Indeks obiektu interfejsu użytkownika.|
|[CCmdUI:: m_pMenu](#m_pmenu)|Wskazuje menu reprezentowane przez `CCmdUI` obiekt.|
|[CCmdUI:: m_pOther](#m_pother)|Wskazuje obiekt okna, który wysłał powiadomienie.|
|[CCmdUI:: m_pSubMenu](#m_psubmenu)|Wskazuje podmenu reprezentowane przez `CCmdUI` obiekt.|

## <a name="remarks"></a>Uwagi

`CCmdUI` nie ma klasy bazowej.

Gdy użytkownik aplikacji pobiera menu, każdy element menu musi wiedzieć, czy powinien być wyświetlany jako włączony czy wyłączony. Obiekt docelowy polecenia menu dostarcza te informacje poprzez implementację procedury obsługi ON_UPDATE_COMMAND_UI. Dla każdego z poleceń interfejsu użytkownika w aplikacji użyj [kreatora klas](mfc-class-wizard.md) lub okna **właściwości** (w **Widok klasy**), aby utworzyć wpis mapy komunikatów i prototyp funkcji dla każdej procedury obsługi.

Po rozłączeniu menu, struktura wyszukuje i wywołuje każdy program obsługi ON_UPDATE_COMMAND_UI, każdy program obsługi wywołuje `CCmdUI` funkcje członkowskie, takie jak `Enable` i `Check` , a następnie odpowiednio wyświetla każdy element menu.

Element menu można zastąpić przyciskiem paska kontrolnego lub innym obiektem polecenia User-Interface bez zmiany kodu w ramach `ON_UPDATE_COMMAND_UI` procedury obsługi.

Poniższa tabela zawiera podsumowanie `CCmdUI` funkcji elementów członkowskich danego efektu w różnych elementach poleceń użytkownika interfejsu.

|Element User-Interface|Włącz|SetCheck|SetRadio|SetText|
|--------------------------|------------|--------------|--------------|-------------|
|Element menu|Włącza lub wyłącza|Sprawdza lub nie sprawdza|Sprawdza przy użyciu kropki|Ustawia tekst elementu|
|Przycisk paska narzędzi|Włącza lub wyłącza|Zaznacza, anuluje zaznaczenia lub nieokreślone|Tak samo jak `SetCheck`|(Nie dotyczy)|
|Okienko pasek stanu|Sprawia, że tekst jest widoczny lub niewidoczny|Ustawia obramowanie wyskakujące lub normalne|Tak samo jak `SetCheck`|Ustawia tekst okienka|
|Normalny przycisk w `CDialogBar`|Włącza lub wyłącza|Sprawdza lub nie sprawdza pola wyboru|Tak samo jak `SetCheck`|Ustawia tekst przycisku|
|Normalna kontrola w `CDialogBar`|Włącza lub wyłącza|(Nie dotyczy)|(Nie dotyczy)|Ustawia tekst okna|

Aby uzyskać więcej informacji na temat używania tej klasy, zobacz [How to Update User-Interface objectss](../../mfc/how-to-update-user-interface-objects.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`CCmdUI`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxwin. h

## <a name="ccmduicontinuerouting"></a><a name="continuerouting"></a> CCmdUI:: ContinueRouting

Wywołaj tę funkcję elementu członkowskiego, aby poinformować mechanizm routingu poleceń, aby kontynuować kierowanie bieżącego komunikatu do łańcucha programów obsługi.

```cpp
void ContinueRouting();
```

### <a name="remarks"></a>Uwagi

Jest to zaawansowana funkcja członkowska, która powinna być używana w połączeniu z obsługą ON_COMMAND_EX, która zwraca wartość FALSE. Aby uzyskać więcej informacji, zobacz [Uwaga techniczna 6](../../mfc/tn006-message-maps.md).

## <a name="ccmduienable"></a><a name="enable"></a> CCmdUI:: Enable

Wywołaj tę funkcję elementu członkowskiego, aby włączyć lub wyłączyć element interfejsu użytkownika dla tego polecenia.

```
virtual void Enable(BOOL bOn = TRUE);
```

### <a name="parameters"></a>Parametry

*bOn*<br/>
Wartość TRUE powoduje włączenie elementu, FAŁSZ, aby go wyłączyć.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCDocView#46](../../mfc/codesnippet/cpp/ccmdui-class_1.cpp)]

[!code-cpp[NVC_MFCDocView#47](../../mfc/codesnippet/cpp/ccmdui-class_2.cpp)]

## <a name="ccmduim_nid"></a><a name="m_nid"></a> CCmdUI:: m_nID

Identyfikator elementu menu, przycisku paska narzędzi lub innego obiektu interfejsu użytkownika reprezentowanego przez `CCmdUI` obiekt.

```
UINT m_nID;
```

## <a name="ccmduim_nindex"></a><a name="m_nindex"></a> CCmdUI:: m_nIndex

Indeks elementu menu, przycisku paska narzędzi lub innego obiektu interfejsu użytkownika reprezentowanego przez `CCmdUI` obiekt.

```
UINT m_nIndex;
```

## <a name="ccmduim_pmenu"></a><a name="m_pmenu"></a> CCmdUI:: m_pMenu

Wskaźnik ( `CMenu` typu) do menu reprezentowanego przez `CCmdUI` obiekt.

```
CMenu* m_pMenu;
```

### <a name="remarks"></a>Uwagi

Wartość NULL, jeśli element nie jest menu.

## <a name="ccmduim_psubmenu"></a><a name="m_psubmenu"></a> CCmdUI:: m_pSubMenu

Wskaźnik (z `CMenu` typu) do podmenu znajdującego się reprezentowane przez `CCmdUI` obiekt.

```
CMenu* m_pSubMenu;
```

### <a name="remarks"></a>Uwagi

Wartość NULL, jeśli element nie jest menu. Jeśli podmenu jest wyskakujące okienko, *m_nID* zawiera identyfikator pierwszego elementu w menu podręcznym. Aby uzyskać więcej informacji, zobacz [Uwaga techniczna 21](../../mfc/tn021-command-and-message-routing.md).

## <a name="ccmduim_pother"></a><a name="m_pother"></a> CCmdUI:: m_pOther

Wskaźnik (typu `CWnd` ) do obiektu okna, takiego jak narzędzie lub pasek stanu, które wysłało powiadomienie.

```
CWnd* m_pOther;
```

### <a name="remarks"></a>Uwagi

Wartość NULL, jeśli element jest menu lub `CWnd` obiektem innym niż.

## <a name="ccmduisetcheck"></a><a name="setcheck"></a> CCmdUI:: SetCheck

Wywołaj tę funkcję elementu członkowskiego, aby ustawić element interfejsu użytkownika dla tego polecenia do odpowiedniego stanu sprawdzania.

```
virtual void SetCheck(int nCheck = 1);
```

### <a name="parameters"></a>Parametry

*nSprawdź*<br/>
Określa stan zaznaczenia do ustawienia. Jeśli 0, Wyewidencjonuj; Jeśli 1, sprawdza; a jeśli 2, ustawia nieokreślony.

### <a name="remarks"></a>Uwagi

Ta funkcja członkowska działa dla elementów menu i przycisków paska narzędzi. Stan nieokreślony ma zastosowanie tylko do przycisków paska narzędzi.

## <a name="ccmduisetradio"></a><a name="setradio"></a> CCmdUI:: SetRadio

Wywołaj tę funkcję elementu członkowskiego, aby ustawić element interfejsu użytkownika dla tego polecenia do odpowiedniego stanu sprawdzania.

```
virtual void SetRadio(BOOL bOn = TRUE);
```

### <a name="parameters"></a>Parametry

*bOn*<br/>
Wartość TRUE powoduje włączenie elementu; w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

Ta funkcja członkowska działa jak `SetCheck` , z tą różnicą, że działa na elementach interfejsu użytkownika działających jako część grupy przycisków radiowych. Po usunięciu zaznaczenia innych elementów w grupie nie jest to automatyczne, chyba że same elementy utrzymują zachowanie grupy radia.

## <a name="ccmduisettext"></a><a name="settext"></a> CCmdUI:: SetText

Wywołaj tę funkcję elementu członkowskiego, aby ustawić tekst elementu interfejsu użytkownika dla tego polecenia.

```
virtual void SetText(LPCTSTR lpszText);
```

### <a name="parameters"></a>Parametry

*lpszText*<br/>
Wskaźnik do ciągu tekstowego.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCDocView#48](../../mfc/codesnippet/cpp/ccmdui-class_3.cpp)]

## <a name="see-also"></a>Zobacz także

[Przykładowy interfejs MDI MFC](../../overview/visual-cpp-samples.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasa CCmdTarget](../../mfc/reference/ccmdtarget-class.md)
