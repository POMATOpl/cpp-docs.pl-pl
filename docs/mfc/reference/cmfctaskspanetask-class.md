---
description: 'Dowiedz się więcej na temat: Klasa CMFCTasksPaneTask'
title: Klasa CMFCTasksPaneTask
ms.date: 11/19/2018
f1_keywords:
- CMFCTasksPaneTask
- AFXTASKSPANE/CMFCTasksPaneTask
- AFXTASKSPANE/CMFCTasksPaneTask::CMFCTasksPaneTask
- AFXTASKSPANE/CMFCTasksPaneTask::SetACCData
- AFXTASKSPANE/CMFCTasksPaneTask::m_bAutoDestroyWindow
- AFXTASKSPANE/CMFCTasksPaneTask::m_bIsBold
- AFXTASKSPANE/CMFCTasksPaneTask::m_dwUserData
- AFXTASKSPANE/CMFCTasksPaneTask::m_hwndTask
- AFXTASKSPANE/CMFCTasksPaneTask::m_nIcon
- AFXTASKSPANE/CMFCTasksPaneTask::m_nWindowHeight
- AFXTASKSPANE/CMFCTasksPaneTask::m_pGroup
- AFXTASKSPANE/CMFCTasksPaneTask::m_rect
- AFXTASKSPANE/CMFCTasksPaneTask::m_strName
- AFXTASKSPANE/CMFCTasksPaneTask::m_uiCommandID
helpviewer_keywords:
- CMFCTasksPaneTask [MFC], CMFCTasksPaneTask
- CMFCTasksPaneTask [MFC], SetACCData
- CMFCTasksPaneTask [MFC], m_bAutoDestroyWindow
- CMFCTasksPaneTask [MFC], m_bIsBold
- CMFCTasksPaneTask [MFC], m_dwUserData
- CMFCTasksPaneTask [MFC], m_hwndTask
- CMFCTasksPaneTask [MFC], m_nIcon
- CMFCTasksPaneTask [MFC], m_nWindowHeight
- CMFCTasksPaneTask [MFC], m_pGroup
- CMFCTasksPaneTask [MFC], m_rect
- CMFCTasksPaneTask [MFC], m_strName
- CMFCTasksPaneTask [MFC], m_uiCommandID
ms.assetid: c5a7513b-cd8f-4e2e-b16f-650e1fe30954
ms.openlocfilehash: 8dad8520c938cae655143464189897d216a5f3ce
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97306771"
---
# <a name="cmfctaskspanetask-class"></a>Klasa CMFCTasksPaneTask

`CMFCTasksPaneTask`Klasa jest klasą pomocnika, która reprezentuje zadania dla kontrolki okienka zadań ( [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md)). Obiekt task reprezentuje element w grupie zadań ( [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md)). Każde zadanie może mieć polecenie, które jest wykonywane przez użytkownika, gdy użytkownik kliknie zadanie i ikonę, która pojawia się po lewej stronie nazwy zadania.

## <a name="syntax"></a>Składnia

```
class CMFCTasksPaneTask : public CObject
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCTasksPaneTask::CMFCTasksPaneTask](#cmfctaskspanetask)|Tworzy i inicjuje `CMFCTasksPaneTask` obiekt.|
|`CMFCTasksPaneTask::~CMFCTasksPaneTask`|Destruktor.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCTasksPaneTask::SetACCData](#setaccdata)|Określa dane ułatwień dostępu dla bieżącego zadania.|

### <a name="data-members"></a>Elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CMFCTasksPaneTask:: m_bAutoDestroyWindow](#m_bautodestroywindow)|Określa, czy okno zadania jest automatycznie niszczone.|
|[CMFCTasksPaneTask:: m_bIsBold](#m_bisbold)|Określa, czy struktura rysuje etykietę zadania pogrubioną czcionką.|
|[CMFCTasksPaneTask:: m_dwUserData](#m_dwuserdata)|Zawiera dane zdefiniowane przez użytkownika, które struktura kojarzy z zadaniem. Ustaw wartość zero, jeśli zadanie nie ma skojarzonych danych.|
|[CMFCTasksPaneTask:: m_hwndTask](#m_hwndtask)|Uchwyt do okna zadania.|
|[CMFCTasksPaneTask:: m_nIcon](#m_nicon)|Indeks na liście obrazów obrazu, który zostanie wyświetlony przez strukturę obok zadania.|
|[CMFCTasksPaneTask:: m_nWindowHeight](#m_nwindowheight)|Wysokość okna zadania. Jeśli zadanie nie ma okna zadania, ta wartość jest równa zero.|
|[CMFCTasksPaneTask:: m_pGroup](#m_pgroup)|Wskaźnik do `CMFCTasksPaneTaskGroup` którego należy to zadanie.|
|[CMFCTasksPaneTask:: m_rect](#m_rect)|Określa prostokąt ograniczenia zadania.|
|[CMFCTasksPaneTask:: m_strName](#m_strname)|Nazwa zadania.|
|[CMFCTasksPaneTask:: m_uiCommandID](#m_uicommandid)|Określa identyfikator polecenia, które jest wykonywane przez środowisko, gdy użytkownik kliknie zadanie. Jeśli ta wartość nie jest prawidłowym IDENTYFIKATORem polecenia, zadanie jest traktowane jako prosta etykieta.|

## <a name="remarks"></a>Uwagi

Na poniższej ilustracji przedstawiono grupę zadań, która zawiera trzy zadania:

![Grupa zadań, rozwinięta](../../mfc/reference/media/nexttaskgrpexpand.png "Grupa zadań, rozwinięta")

> [!NOTE]
> Jeśli zadanie nie ma prawidłowego identyfikatora polecenia, jest traktowane jako prosta etykieta.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CMFCTasksPaneTask](../../mfc/reference/cmfctaskspanetask-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxTasksPane. h

## <a name="cmfctaskspanetaskcmfctaskspanetask"></a><a name="cmfctaskspanetask"></a> CMFCTasksPaneTask::CMFCTasksPaneTask

Tworzy i inicjuje `CMFCTasksPaneTask` obiekt.

```
CMFCTasksPaneTask(
    CMFCTasksPaneTaskGroup* pGroup,
    LPCTSTR lpszName,
    int nIcon,
    UINT uiCommandID,
    DWORD dwUserData = 0,
    HWND hwndTask = NULL,
    BOOL bAutoDestroyWindow = FALSE,
    int nWindowHeight = 0);
```

### <a name="parameters"></a>Parametry

*pGroup*<br/>
Określa [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md) , do którego należy zadanie.

*lpszName*<br/>
Określa nazwę zadania.

*nIcon*<br/>
Określa indeks obrazu zadania na liście obrazów.

*uiCommandID*<br/>
Określa identyfikator polecenia, które jest wykonywane po kliknięciu zadania.

*dwUserData*<br/>
Dane zdefiniowane przez użytkownika.

*hwndTask*<br/>
Określa uchwyt do okna zadania.

*bAutoDestroyWindow*<br/>
W przypadku wartości TRUE okno zadania zostanie zniszczone automatycznie.

*nWindowHeight*<br/>
Określa wysokość okna zadania.

### <a name="remarks"></a>Uwagi

## <a name="cmfctaskspanetaskm_bautodestroywindow"></a><a name="m_bautodestroywindow"></a> CMFCTasksPaneTask:: m_bAutoDestroyWindow

Określa, czy okno zadania jest automatycznie niszczone.

```
BOOL m_bAutoDestroyWindow;
```

### <a name="remarks"></a>Uwagi

Ustaw wartość TRUE, aby określić, że okno zadania ( [CMFCTasksPaneTask:: m_hwndTask](#m_hwndtask)) powinno zostać automatycznie zniszczone; w przeciwnym razie FALSE.

## <a name="cmfctaskspanetaskm_bisbold"></a><a name="m_bisbold"></a> CMFCTasksPaneTask:: m_bIsBold

Określa, czy etykieta zadania jest rysowana pogrubioną czcionką.

```
BOOL m_bIsBold;
```

### <a name="remarks"></a>Uwagi

Ustaw dla tego elementu członkowskiego wartość TRUE, aby wyświetlić pogrubiony tekst dla etykiety zadania.

## <a name="cmfctaskspanetaskm_dwuserdata"></a><a name="m_dwuserdata"></a> CMFCTasksPaneTask:: m_dwUserData

Zawiera dane zdefiniowane przez użytkownika, które są skojarzone z zadaniem. Ustaw wartość zero, jeśli żadne dane nie są skojarzone z zadaniem.

```
DWORD m_dwUserData;
```

### <a name="remarks"></a>Uwagi

## <a name="cmfctaskspanetaskm_hwndtask"></a><a name="m_hwndtask"></a> CMFCTasksPaneTask:: m_hwndTask

Uchwyt do okna zadania.

```
HWND m_hwndTask;
```

### <a name="remarks"></a>Uwagi

Aby dodać okno zadania, wywołaj [CMFCTasksPane:: AddWindow](../../mfc/reference/cmfctaskspane-class.md#addwindow).

## <a name="cmfctaskspanetaskm_nicon"></a><a name="m_nicon"></a> CMFCTasksPaneTask:: m_nIcon

Pozycja indeksu na liście obrazów, która identyfikuje obraz wyświetlany obok określonego zadania.

```
int m_nIcon;
```

### <a name="remarks"></a>Uwagi

Lista obrazów jest ustawiana przez [CMFCTasksPane:: SetIconsList](../../mfc/reference/cmfctaskspane-class.md#seticonslist).

Ustaw wartość `m_nIcon` -1, jeśli chcesz wyświetlić zadanie bez obrazu.

## <a name="cmfctaskspanetaskm_nwindowheight"></a><a name="m_nwindowheight"></a> CMFCTasksPaneTask:: m_nWindowHeight

Wysokość okna zadania. Jeśli zadanie nie ma okna zadania, ta wartość jest równa zero.

```
int m_nWindowHeight;
```

### <a name="remarks"></a>Uwagi

## <a name="cmfctaskspanetaskm_pgroup"></a><a name="m_pgroup"></a> CMFCTasksPaneTask:: m_pGroup

Wskaźnik do [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md) , do którego należy to zadanie.

```
CMFCTasksPaneTaskGroup* m_pGroup;
```

### <a name="remarks"></a>Uwagi

Każde zadanie musi mieć grupę nadrzędną. Dodawanie grup do okienka zadań przez wywołanie [CMFCTasksPane:: addgroup](../../mfc/reference/cmfctaskspane-class.md#addgroup).

## <a name="cmfctaskspanetaskm_rect"></a><a name="m_rect"></a> CMFCTasksPaneTask:: m_rect

Określa prostokąt ograniczenia zadania.

```
CRect m_rect;
```

### <a name="remarks"></a>Uwagi

Ta wartość jest obliczana przez platformę, gdy zadanie jest rysowane.

## <a name="cmfctaskspanetaskm_strname"></a><a name="m_strname"></a> CMFCTasksPaneTask:: m_strName

Nazwa zadania.

```
CString m_strName;
```

### <a name="remarks"></a>Uwagi

## <a name="cmfctaskspanetaskm_uicommandid"></a><a name="m_uicommandid"></a> CMFCTasksPaneTask:: m_uiCommandID

Określa identyfikator polecenia, które jest wykonywane, gdy użytkownik kliknie zadanie. Jeśli ta wartość nie jest prawidłowym IDENTYFIKATORem polecenia, zadanie jest traktowane jako prosta etykieta.

```
UINT m_uiCommandID;
```

### <a name="remarks"></a>Uwagi

## <a name="cmfctaskspanetasksetaccdata"></a><a name="setaccdata"></a> CMFCTasksPaneTask::SetACCData

Określa dane ułatwień dostępu dla bieżącego zadania.

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>Parametry

*pParent*<br/>
podczas Reprezentuje okno nadrzędne bieżącego zadania.

*data*<br/>
określoną Obiekt typu `CAccessibilityData` , który jest wypełniony danymi dostępności bieżącego zadania.

### <a name="return-value"></a>Wartość zwracana

Wartość TRUE, jeśli parametr *danych* został pomyślnie wypełniony danymi dostępności bieżącego zadania; w przeciwnym razie FALSE.

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CObject](../../mfc/reference/cobject-class.md)
