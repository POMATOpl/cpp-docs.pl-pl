---
description: 'Dowiedz się więcej na temat: Klasa CMFCTasksPaneTaskGroup'
title: Klasa CMFCTasksPaneTaskGroup
ms.date: 11/19/2018
f1_keywords:
- CMFCTasksPaneTaskGroup
- AFXTASKSPANE/CMFCTasksPaneTaskGroup
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::CMFCTasksPaneTaskGroup
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::SetACCData
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_bIsBottom
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_bIsCollapsed
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_bIsSpecial
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_lstTasks
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_rect
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_rectGroup
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_strName
helpviewer_keywords:
- CMFCTasksPaneTaskGroup [MFC], CMFCTasksPaneTaskGroup
- CMFCTasksPaneTaskGroup [MFC], SetACCData
- CMFCTasksPaneTaskGroup [MFC], m_bIsBottom
- CMFCTasksPaneTaskGroup [MFC], m_bIsCollapsed
- CMFCTasksPaneTaskGroup [MFC], m_bIsSpecial
- CMFCTasksPaneTaskGroup [MFC], m_lstTasks
- CMFCTasksPaneTaskGroup [MFC], m_rect
- CMFCTasksPaneTaskGroup [MFC], m_rectGroup
- CMFCTasksPaneTaskGroup [MFC], m_strName
ms.assetid: 2111640b-a46e-4b27-b033-29e88632b86a
ms.openlocfilehash: 6b09923c70ad6208b1b029e6ad555c22cd4c771f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97254706"
---
# <a name="cmfctaskspanetaskgroup-class"></a>Klasa CMFCTasksPaneTaskGroup

`CMFCTasksPaneTaskGroup`Klasa jest klasą pomocnika używaną przez formant [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md) . Obiekty typu `CMFCTasksPaneTaskGroup` reprezentują *grupę zadań*. Grupa zadań to lista elementów, które struktura wyświetla w osobnym polu, które ma przycisk Zwiń. Pole może mieć opcjonalny podpis (nazwa grupy). Jeśli grupa jest zwinięta, lista zadań nie jest widoczna.

## <a name="syntax"></a>Składnia

```
class CMFCTasksPaneTaskGroup : public CObject
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCTasksPaneTaskGroup::CMFCTasksPaneTaskGroup](#cmfctaskspanetaskgroup)|Konstruuje `CMFCTasksPaneTaskGroup` obiekt.|
|`CMFCTasksPaneTaskGroup::~CMFCTasksPaneTaskGroup`|Destruktor.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCTasksPaneTaskGroup::SetACCData](#setaccdata)|Określa dane ułatwień dostępu dla bieżącej grupy zadań.|

### <a name="data-members"></a>Elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CMFCTasksPaneTaskGroup:: m_bIsBottom](#m_bisbottom)|Określa, czy grupa zadań jest wyrównana do dolnej części kontrolki okienka zadań.|
|[CMFCTasksPaneTaskGroup:: m_bIsCollapsed](#m_biscollapsed)|Określa, czy grupa zadań jest zwinięta.|
|[CMFCTasksPaneTaskGroup:: m_bIsSpecial](#m_bisspecial)|Określa, czy grupa zadań jest *specjalna.* Struktura wyświetla specjalne podpisy w innym kolorze.|
|[CMFCTasksPaneTaskGroup:: m_lstTasks](#m_lsttasks)|Zawiera wewnętrzną listę zadań.|
|[CMFCTasksPaneTaskGroup:: m_rect](#m_rect)|Określa prostokąt związany z podpisem grupy.|
|[CMFCTasksPaneTaskGroup:: m_rectGroup](#m_rectgroup)|Określa prostokąt związany z grupą.|
|[CMFCTasksPaneTaskGroup:: m_strName](#m_strname)|Określa nazwę grupy.|

## <a name="remarks"></a>Uwagi

Na poniższej ilustracji przedstawiono rozwiniętą grupę zadań:

![Grupa zadań, rozwinięta](../../mfc/reference/media/nexttaskgrpexpand.png "Grupa zadań, rozwinięta")

Na poniższej ilustracji przedstawiono rozwiniętą grupę zadań:

![Zwinięta grupa zadań](../../mfc/reference/media/nexttaskgrpcollapse.png "Zwinięta grupa zadań")

Na poniższej ilustracji przedstawiono grupę zadań bez podpisu:

![Grupa zadań bez podpisu](../../mfc/reference/media/nexttaskgrpnocapt.png "Grupa zadań bez podpisu")

Na poniższej ilustracji przedstawiono dwie grupy zadań. Pierwsza grupa zadań jest oznaczona jako specjalna przez ustawienie `m_bIsSpecial` flagi na true, podczas gdy druga grupa zadań nie jest specjalna. Zwróć uwagę, jak podpis pierwszej grupy zadań jest ciemniejszy niż druga grupa zadań:

![Specjalna grupa zadań](../../mfc/reference/media/nexttaskgrpspecial.png "Specjalna grupa zadań")

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxTasksPane. h

## <a name="cmfctaskspanetaskgroupcmfctaskspanetaskgroup"></a><a name="cmfctaskspanetaskgroup"></a> CMFCTasksPaneTaskGroup::CMFCTasksPaneTaskGroup

Konstruuje `CMFCTasksPaneTaskGroup` obiekt.

```
CMFCTasksPaneTaskGroup(
    LPCTSTR lpszName,
    BOOL bIsBottom,
    BOOL bIsSpecial=FALSE,
    BOOL bIsCollapsed=FALSE,
    CMFCTasksPanePropertyPage* pPage=NULL,
    HICON hIcon=NULL);
```

### <a name="parameters"></a>Parametry

*lpszName*<br/>
Określa nazwę grupy w podpisie grupy.

*bIsBottom*<br/>
Określa, czy grupa jest wyrównana do dolnej części kontrolki okienka zadań.

*bIsSpecial*<br/>
Określa, czy grupa jest oznaczona jako *specjalna* i w ten sposób, czy podpis grupy jest wypełniony innym kolorem.

*bIsCollapsed*<br/>
Określa, czy grupa jest zwinięta.

*pPage*<br/>
Określa stronę właściwości, do której należy ta grupa zadań.

*hIcon*<br/>
Określa ikonę wyświetlaną w podpisie grupy.

### <a name="remarks"></a>Uwagi

## <a name="cmfctaskspanetaskgroupm_bisbottom"></a><a name="m_bisbottom"></a> CMFCTasksPaneTaskGroup:: m_bIsBottom

Określa, czy grupa zadań jest wyrównana do dolnej części kontrolki okienka zadań.

```
BOOL m_bIsBottom;
```

### <a name="remarks"></a>Uwagi

Tylko jedną grupę można wyrównać do dolnej części kontrolki okienka zadań. Ta grupa zadań musi zostać dodana jako Ostatnia. Aby uzyskać więcej informacji, zobacz [CMFCTasksPane:: addgroup](../../mfc/reference/cmfctaskspane-class.md#addgroup).

## <a name="cmfctaskspanetaskgroupm_biscollapsed"></a><a name="m_biscollapsed"></a> CMFCTasksPaneTaskGroup:: m_bIsCollapsed

Określa, czy grupa zadań jest zwinięta.

```
BOOL m_bIsCollapsed;
```

### <a name="remarks"></a>Uwagi

Można włączyć lub wyłączyć możliwość zwijania grup w okienku zadań, wywołując [CMFCTasksPane:: EnableGroupCollapse](../../mfc/reference/cmfctaskspane-class.md#enablegroupcollapse).

## <a name="cmfctaskspanetaskgroupm_bisspecial"></a><a name="m_bisspecial"></a> CMFCTasksPaneTaskGroup:: m_bIsSpecial

Określa, czy grupa zadań jest *specjalna* i czy etykieta specjalnej grupy zadań powinna być identyfikowana przez inny kolor.

```
BOOL m_bIsSpecial;
```

### <a name="remarks"></a>Uwagi

Jeśli aplikacja używa motywu wizualnego systemu Windows XP i `m_bIsSpecial` ma wartość false, platforma wywołuje `DrawThemeBackground` z flagą EBP_NORMALGROUPBACKGROUND. Jeśli `m_bIsSpecial` ma wartość true, struktura wywołuje `DrawThemeBackground` flagę EBP_SPECIALGROUPBACKGROUND.

## <a name="cmfctaskspanetaskgroupm_lsttasks"></a><a name="m_lsttasks"></a> CMFCTasksPaneTaskGroup:: m_lstTasks

Zawiera wewnętrzną listę zadań.

```
CObList m_lstTasks;
```

### <a name="remarks"></a>Uwagi

Aby wypełnić tę listę, wywołaj [CMFCTasksPane:: AddTask](../../mfc/reference/cmfctaskspane-class.md#addtask).

## <a name="cmfctaskspanetaskgroupm_rect"></a><a name="m_rect"></a> CMFCTasksPaneTaskGroup:: m_rect

Określa prostokąt związany z podpisem grupy.

```
CRect m_rect;
```

### <a name="remarks"></a>Uwagi

Ta wartość jest obliczana automatycznie na podstawie struktury.

## <a name="cmfctaskspanetaskgroupm_rectgroup"></a><a name="m_rectgroup"></a> CMFCTasksPaneTaskGroup:: m_rectGroup

Określa prostokąt związany z grupą.

```
CRect m_rectGroup;
```

### <a name="remarks"></a>Uwagi

Ta wartość jest obliczana automatycznie przez platformę.

## <a name="cmfctaskspanetaskgroupm_strname"></a><a name="m_strname"></a> CMFCTasksPaneTaskGroup:: m_strName

Określa nazwę grupy.

```
CString m_strName;
```

### <a name="remarks"></a>Uwagi

Jeśli ta wartość jest pusta, podpis grupy nie będzie wyświetlany i nie można zwinąć grupy.

## <a name="cmfctaskspanetaskgroupsetaccdata"></a><a name="setaccdata"></a> CMFCTasksPaneTaskGroup::SetACCData

Określa dane ułatwień dostępu dla bieżącej grupy zadań.

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>Parametry

*pParent*<br/>
podczas Reprezentuje okno nadrzędne bieżącej grupy zadań.

*data*<br/>
określoną Obiekt typu `CAccessibilityData` , który jest wypełniony danymi dostępności bieżącej grupy zadań.

### <a name="return-value"></a>Wartość zwracana

Wartość TRUE, jeśli parametr *danych* został pomyślnie wypełniony danymi dostępności bieżącej grupy zadań; w przeciwnym razie FALSE.

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md)<br/>
[Klasa CMFCTasksPaneTask](../../mfc/reference/cmfctaskspanetask-class.md)<br/>
[Klasa CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)<br/>
[Klasa CObject](../../mfc/reference/cobject-class.md)
