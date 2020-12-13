---
description: 'Dowiedz się więcej na temat: Klasa CMFCToolBarInfo'
title: Klasa CMFCToolBarInfo
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarInfo
- AFXTOOLBAR/CMFCToolBarInfo
- AFXTOOLBAR/CMFCToolBarInfo::m_uiColdResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiDisabledResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiHotResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiLargeColdResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiLargeDisabledResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiLargeHotResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiMenuDisabledResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiMenuResID
helpviewer_keywords:
- CMFCToolBarInfo [MFC], m_uiColdResID
- CMFCToolBarInfo [MFC], m_uiDisabledResID
- CMFCToolBarInfo [MFC], m_uiHotResID
- CMFCToolBarInfo [MFC], m_uiLargeColdResID
- CMFCToolBarInfo [MFC], m_uiLargeDisabledResID
- CMFCToolBarInfo [MFC], m_uiLargeHotResID
- CMFCToolBarInfo [MFC], m_uiMenuDisabledResID
- CMFCToolBarInfo [MFC], m_uiMenuResID
ms.assetid: 6dc84482-eaaa-491f-aa5d-dd7a57886b46
ms.openlocfilehash: 9b85ef4f39c8b42c35975a15836a21e7cc6dd6b1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331714"
---
# <a name="cmfctoolbarinfo-class"></a>Klasa CMFCToolBarInfo

Zawiera identyfikatory zasobów obrazów pasków narzędzi w różnych stanach. `CMFCToolBarInfo` jest klasą pomocnika, która jest używana jako parametr metody [CMFCToolBar:: LoadToolBarEx](../../mfc/reference/cmfctoolbar-class.md#loadtoolbarex) .

## <a name="syntax"></a>Składnia

```
class CMFCToolBarInfo
```

## <a name="members"></a>Elementy członkowskie

### <a name="data-members"></a>Elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CMFCToolBarInfo:: m_uiColdResID](#m_uicoldresid)|Identyfikator zasobu mapy bitowej paska narzędzi, który zawiera zwykłe (zimne) obrazy paska narzędzi.|
|[CMFCToolBarInfo:: m_uiDisabledResID](#m_uidisabledresid)|Identyfikator zasobu mapy bitowej paska narzędzi, który zawiera wyłączone obrazy pasków narzędzi.|
|[CMFCToolBarInfo:: m_uiHotResID](#m_uihotresid)|Identyfikator zasobu mapy bitowej paska narzędzi, który zawiera wybrane (gorąca) obrazy paska narzędzi.|
|[CMFCToolBarInfo:: m_uiLargeColdResID](#m_uilargecoldresid)|Identyfikator zasobu mapy bitowej paska narzędzi, który zawiera duże, zwykłe obrazy pasków narzędzi.|
|[CMFCToolBarInfo:: m_uiLargeDisabledResID](#m_uilargedisabledresid)|Identyfikator zasobu mapy bitowej paska narzędzi, który zawiera duże, wyłączone obrazy pasków narzędzi.|
|[CMFCToolBarInfo:: m_uiLargeHotResID](#m_uilargehotresid)|Identyfikator zasobu mapy bitowej paska narzędzi, który zawiera duże, wybrane obrazy pasków narzędzi.|
|[CMFCToolBarInfo:: m_uiMenuDisabledResID](#m_uimenudisabledresid)|Identyfikator zasobu mapy bitowej paska narzędzi zawierającego wyłączone obrazy menu.|
|[CMFCToolBarInfo:: m_uiMenuResID](#m_uimenuresid)|Identyfikator zasobu mapy bitowej paska narzędzi, który zawiera obrazy menu.|

## <a name="remarks"></a>Uwagi

Pełna mapa bitowa paska narzędzi składa się z małych obrazów pasków narzędzi (przycisków) o stałym rozmiarze. Każdy identyfikator zasobu, który jest przechowywany w `CMFCToolBarInfo` obiekcie, jest mapą bitową, która zawiera pełny zestaw obrazów pasków narzędzi w jednym stanie (na przykład, wybrane, wyłączone, duże lub menu).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CMFCToolBarInfo](../../mfc/reference/cmfctoolbarinfo-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxtoolbar. h

## <a name="cmfctoolbarinfom_uicoldresid"></a><a name="m_uicoldresid"></a> CMFCToolBarInfo:: m_uiColdResID

Określa identyfikator zasobu dla wszystkich zwykłych obrazów przycisków na pasku narzędzi.

```
UINT m_uiColdResID;
```

## <a name="cmfctoolbarinfom_uidisabledresid"></a><a name="m_uidisabledresid"></a> CMFCToolBarInfo:: m_uiDisabledResID

Określa identyfikator zasobu dla niedostępnych obrazów przycisków na pasku narzędzi.

```
UINT m_uiDisabledResID;
```

## <a name="cmfctoolbarinfom_uihotresid"></a><a name="m_uihotresid"></a> CMFCToolBarInfo:: m_uiHotResID

Określa identyfikator zasobu dla wszystkich wyróżnionych obrazów przycisków na pasku narzędzi.

```
UINT m_uiHotResID
```

## <a name="cmfctoolbarinfom_uilargecoldresid"></a><a name="m_uilargecoldresid"></a> CMFCToolBarInfo:: m_uiLargeColdResID

Określa identyfikator zasobu dla wszystkich obrazów zwykłych przycisków na pasku narzędzi.

```
UINT m_uiLargeColdResID
```

## <a name="cmfctoolbarinfom_uilargedisabledresid"></a><a name="m_uilargedisabledresid"></a> CMFCToolBarInfo:: m_uiLargeDisabledResID

Określa identyfikator zasobu dla wszystkich obrazów przycisków z dużymi wyłączonymi przyciskami paska narzędzi.

```
UINT m_uiLargeDisabledResID;
```

## <a name="cmfctoolbarinfom_uilargehotresid"></a><a name="m_uilargehotresid"></a> CMFCToolBarInfo:: m_uiLargeHotResID

Określa identyfikator zasobu dla wszystkich dużych obrazów wyróżnionych na pasku narzędzi.

```
UINT m_uiLargeHotResID;
```

## <a name="cmfctoolbarinfom_uimenudisabledresid"></a><a name="m_uimenudisabledresid"></a> CMFCToolBarInfo:: m_uiMenuDisabledResID

Określa identyfikator zasobu dla obrazów niedostępnych dla poleceń na pasku narzędzi.

```
UINT m_uiMenuDisabledResID;
```

## <a name="cmfctoolbarinfom_uimenuresid"></a><a name="m_uimenuresid"></a> CMFCToolBarInfo:: m_uiMenuResID

Określa identyfikator zasobu dla wszystkich obrazów zwykłych elementów menu na pasku narzędzi.

```
UINT m_uiMenuResID;
```

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)
