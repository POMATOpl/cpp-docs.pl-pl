---
description: Dowiedz się więcej o strukturze CMFCTabToolTipInfo
title: CMFCTabToolTipInfo, struktura
ms.date: 11/04/2016
f1_keywords:
- CMFCTabToolTipInfo
helpviewer_keywords:
- CMFCTabToolTipInfo struct
ms.assetid: 9c3b3fb9-1497-4d59-932b-0da9348dd5e2
ms.openlocfilehash: ce9e9f4fdbcf367921e7f0559a4d04e66f4303dc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97164071"
---
# <a name="cmfctabtooltipinfo-structure"></a>CMFCTabToolTipInfo, struktura

Ta struktura zawiera informacje o karcie MDI, nad którą użytkownik jest aktywowany.

## <a name="syntax"></a>Składnia

```
struct CMFCTabToolTipInfo
```

## <a name="members"></a>Elementy członkowskie

### <a name="data-members"></a>Elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CMFCTabToolTipInfo:: m_nTabIndex](#m_ntabindex)|Określa indeks kontrolki karta.|
|[CMFCTabToolTipInfo:: m_pTabWnd](#m_ptabwnd)|Wskaźnik do kontrolki karta.|
|[CMFCTabToolTipInfo:: m_strText](#m_strtext)|Tekst etykietki narzędzia.|

## <a name="remarks"></a>Uwagi

Wskaźnik do `CMFCTabToolTipInfo` struktury jest przenoszona jako parametr komunikatu AFX_WM_ON_GET_TAB_TOOLTIP. Ta wiadomość jest generowana, gdy karty MDI są włączone, a użytkownik umieści wskaźnik myszy na kontrolce karty.

## <a name="example"></a>Przykład

Poniższy przykład pokazuje, jak `CMFCTabToolTipInfo` jest używany w [przykładzie MDITabsDemo: aplikacja MDI z kartami MFC](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CMFCTabToolTipInfo](../../mfc/reference/cmfctabtooltipinfo-structure.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxbasetabctrl. h

## <a name="cmfctabtooltipinfom_ntabindex"></a><a name="m_ntabindex"></a> CMFCTabToolTipInfo:: m_nTabIndex

Określa indeks kontrolki karta.

```
int m_nTabIndex;
```

### <a name="remarks"></a>Uwagi

Indeks karty, nad którą użytkownik jest aktywowany.

### <a name="example"></a>Przykład

Poniższy przykład pokazuje, jak `m_nTabIndex` jest używany w [przykładzie MDITabsDemo: aplikacja MDI z kartami MFC](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]

## <a name="cmfctabtooltipinfom_ptabwnd"></a><a name="m_ptabwnd"></a> CMFCTabToolTipInfo:: m_pTabWnd

Wskaźnik do kontrolki karta.

```
CMFCBaseTabCtrl* m_pTabWnd;
```

### <a name="example"></a>Przykład

Poniższy przykład pokazuje, jak `m_pTabWnd` jest używany w [przykładzie MDITabsDemo: aplikacja MDI z kartami MFC](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]

## <a name="cmfctabtooltipinfom_strtext"></a><a name="m_strtext"></a> CMFCTabToolTipInfo:: m_strText

Tekst etykietki narzędzia.

```
CString m_strText;
```

### <a name="remarks"></a>Uwagi

Jeśli ciąg jest pusty, etykietka narzędzia nie zostanie wyświetlona.

### <a name="example"></a>Przykład

Poniższy przykład pokazuje, jak `m_strText` jest używany w [przykładzie MDITabsDemo: aplikacja MDI z kartami MFC](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)
