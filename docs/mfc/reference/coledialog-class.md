---
description: 'Dowiedz się więcej na temat: Klasa COleDialog'
title: Klasa COleDialog
ms.date: 11/04/2016
f1_keywords:
- COleDialog
- AFXODLGS/COleDialog
- AFXODLGS/COleDialog::GetLastError
helpviewer_keywords:
- COleDialog [MFC], GetLastError
ms.assetid: b1ed0aca-3914-4b00-af34-4a4fb491aec7
ms.openlocfilehash: 9bdb532d58136ac2aac622fa88f674e60ec7221e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227302"
---
# <a name="coledialog-class"></a>Klasa COleDialog

Udostępnia funkcje wspólne dla okien dialogowych OLE.

## <a name="syntax"></a>Składnia

```
class COleDialog : public CCommonDialog
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[COleDialog:: GetLastError](#getlasterror)|Pobiera kod błędu zwracany przez okno dialogowe.|

## <a name="remarks"></a>Uwagi

Biblioteka MFC zawiera kilka klas pochodnych z `COleDialog` :

- [COleInsertDialog](../../mfc/reference/coleinsertdialog-class.md)

- [COleConvertDialog](../../mfc/reference/coleconvertdialog-class.md)

- [COleChangeIconDialog](../../mfc/reference/colechangeicondialog-class.md)

- [COleLinksDialog](../../mfc/reference/colelinksdialog-class.md)

- [COleBusyDialog](../../mfc/reference/colebusydialog-class.md)

- [COleUpdateDialog](../../mfc/reference/coleupdatedialog-class.md)

- [COlePasteSpecialDialog](../../mfc/reference/colepastespecialdialog-class.md)

- [COlePropertiesDialog](../../mfc/reference/colepropertiesdialog-class.md)

- [COleChangeSourceDialog](../../mfc/reference/colechangesourcedialog-class.md)

Aby uzyskać więcej informacji o oknach dialogowych specyficznych dla OLE, zobacz [okna dialogowe artykułu w OLE](../../mfc/dialog-boxes-in-ole.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`COleDialog`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxodlgs. h

## <a name="coledialoggetlasterror"></a><a name="getlasterror"></a> COleDialog:: GetLastError

Wywołaj `GetLastError` funkcję członkowską, aby uzyskać dodatkowe informacje o błędzie podczas `DoModal` zwraca IDABORT.

```
UINT GetLastError() const;
```

### <a name="return-value"></a>Wartość zwracana

Kody błędów zwracane przez `GetLastError` zależą od wyświetlonego okna dialogowego.

### <a name="remarks"></a>Uwagi

Zobacz `DoModal` funkcja członkowska w klasach pochodnych, aby uzyskać informacje o określonych komunikatach o błędach.

## <a name="see-also"></a>Zobacz też

[Klasa CCommonDialog](../../mfc/reference/ccommondialog-class.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)
