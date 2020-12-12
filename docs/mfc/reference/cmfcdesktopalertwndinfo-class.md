---
description: 'Dowiedz się więcej na temat: Klasa CMFCDesktopAlertWndInfo'
title: Klasa CMFCDesktopAlertWndInfo
ms.date: 10/18/2018
f1_keywords:
- CMFCDesktopAlertWndInfo
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_hIcon
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_nURLCmdID
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_strText
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_strURL
helpviewer_keywords:
- CMFCDesktopAlertWndInfo [MFC], m_hIcon
- CMFCDesktopAlertWndInfo [MFC], m_nURLCmdID
- CMFCDesktopAlertWndInfo [MFC], m_strText
- CMFCDesktopAlertWndInfo [MFC], m_strURL
ms.assetid: 5c9bb84e-6c96-4748-8e74-6951b6ae8e84
ms.openlocfilehash: 1c23e5b890e892df9bccce51542f2d36b3d6f7d4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97250689"
---
# <a name="cmfcdesktopalertwndinfo-class"></a>Klasa CMFCDesktopAlertWndInfo

`CMFCDesktopAlertWndInfo`Klasa jest używana z [klasą CMFCDesktopAlertWnd](../../mfc/reference/cmfcdesktopalertwnd-class.md). Określa kontrolki, które są wyświetlane, gdy zostanie wyświetlone okno alertu pulpitu.

## <a name="syntax"></a>Składnia

```
class CMFCDesktopAlertWndInfo
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|`CMFCDesktopAlertWndInfo::~CMFCDesktopAlertWndInfo`|Destruktor.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCDesktopAlertWndInfo:: operator =](#operator_eq)||

### <a name="data-members"></a>Elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CMFCDesktopAlertWndInfo:: m_hIcon](#m_hicon)|Dojście do wyświetlanej ikony.|
|[CMFCDesktopAlertWndInfo:: m_nURLCmdID](#m_nurlcmdid)|Identyfikator polecenia skojarzony z linkiem w oknie alertu pulpitu.|
|[CMFCDesktopAlertWndInfo:: m_strText](#m_strtext)|Tekst wyświetlany w oknie alertu pulpitu.|
|[CMFCDesktopAlertWndInfo:: m_strURL](#m_strurl)|Link wyświetlany w oknie alertu pulpitu.|

## <a name="remarks"></a>Uwagi

`CMFCDesktopAlertWndInfo`Klasa jest przenoszona do metody [CMFCDesktopAlertWnd:: Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create) , aby określić elementy, które są wyświetlane w oknie dialogowym alertu pulpitu. Domyślne okno dialogowe może zawierać trzy elementy:

- Ikona, która jest ustawiana przez wywołanie [CMFCDesktopAlertWndInfo:: m_hIcon](#m_hicon).

- Etykieta lub wiadomość tekstowa, która jest ustawiana przez wywołanie [CMFCDesktopAlertWndInfo:: m_strText](#m_strtext).

- Link, który jest ustawiany przez wywołanie [CMFCDesktopAlertWndInfo:: m_strURL](#m_strurl). Aby ustawić polecenie, które jest wykonywane po kliknięciu łącza, wywołaj [CMFCDesktopAlertWndInfo:: m_nURLCmdID](#m_nurlcmdid).

Jeśli domyślne okno dialogowe nie jest wystarczające, można utworzyć niestandardowe okno dialogowe i przekazać je do metody [CMFCDesktopAlertWnd:: Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create) zamiast używać tej klasy. Aby uzyskać więcej informacji, zobacz [Klasa CMFCDesktopAlertDialog](../../mfc/reference/cmfcdesktopalertdialog-class.md).

## <a name="example"></a>Przykład

W poniższym przykładzie pokazano, jak używać różnych elementów członkowskich w `CMFCDesktopAlertWndInfo` klasie. W przykładzie przedstawiono sposób ustawiania uchwytu do wyświetlanej ikony, tekstu wyświetlanego w oknie alertu pulpitu, linku wyświetlanego w oknie alertu pulpitu oraz identyfikatora polecenia, który jest skojarzony z linkiem w oknie alertu pulpitu. Ten przykład jest częścią [przykładu pokazu alertu na pulpicie](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_DesktopAlertDemo#3](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndinfo-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CMFCDesktopAlertWndInfo](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxDesktopAlertDialog. h

## <a name="cmfcdesktopalertwndinfooperator"></a><a name="operator_eq"></a> CMFCDesktopAlertWndInfo:: operator =

Aby uzyskać więcej szczegółów, zobacz kod źródłowy znajdujący się w folderze **VC \\ atlmfc \\ src \\ MFC** instalacji programu Visual Studio.

```
CMFCDesktopAlertWndInfo& operator=(CMFCDesktopAlertWndInfo& src);
```

### <a name="parameters"></a>Parametry

podczas *src*<br/>

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cmfcdesktopalertwndinfom_hicon"></a><a name="m_hicon"></a> CMFCDesktopAlertWndInfo:: m_hIcon

Dojście do wyświetlanej ikony.

```
HICON m_hIcon;
```

### <a name="remarks"></a>Uwagi

## <a name="cmfcdesktopalertwndinfom_nurlcmdid"></a><a name="m_nurlcmdid"></a> CMFCDesktopAlertWndInfo:: m_nURLCmdID

Identyfikator polecenia skojarzony z linkiem w oknie alertu pulpitu.

```
UINT m_nURLCmdID;
```

### <a name="remarks"></a>Uwagi

Identyfikator polecenia jest wysyłany do właściciela okna podręcznego, gdy użytkownik kliknie link określony przez [CMFCDesktopAlertWndInfo:: m_strURL](#m_strurl).

## <a name="cmfcdesktopalertwndinfom_strtext"></a><a name="m_strtext"></a> CMFCDesktopAlertWndInfo:: m_strText

Tekst wyświetlany w oknie alertu pulpitu.

```
CString m_strText;
```

### <a name="remarks"></a>Uwagi

## <a name="cmfcdesktopalertwndinfom_strurl"></a><a name="m_strurl"></a> CMFCDesktopAlertWndInfo:: m_strURL

Link wyświetlany w oknie alertu pulpitu.

```
CString m_strURL;
```

### <a name="remarks"></a>Uwagi

Gdy użytkownik kliknie link, polecenie z IDENTYFIKATORem polecenia [CMFCDesktopAlertWndInfo:: m_nURLCmdID](#m_nurlcmdid) zostanie wysłane do właściciela okna podręcznego.

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CMFCDesktopAlertWnd](../../mfc/reference/cmfcdesktopalertwnd-class.md)<br/>
[CMFCDesktopAlertWnd:: Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create)<br/>
[Klasa CMFCDesktopAlertDialog](../../mfc/reference/cmfcdesktopalertdialog-class.md)
