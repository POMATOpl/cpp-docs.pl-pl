---
description: 'Dowiedz się więcej na temat: Klasa COleControlModule'
title: Klasa COleControlModule
ms.date: 11/04/2016
f1_keywords:
- OleControlModule
helpviewer_keywords:
- OLE control modules [MFC]
- MFC ActiveX controls [MFC], OLE control modules
- COleControlModule class [MFC]
- control modules [MFC]
ms.assetid: 0721724d-d4af-4eda-ad34-5a2b27810dd4
ms.openlocfilehash: f88296b7c0e897f82227343b31ca2f639902256e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227484"
---
# <a name="colecontrolmodule-class"></a>Klasa COleControlModule

Klasa bazowa, z której pochodzi obiekt modułu kontrolki OLE.

## <a name="syntax"></a>Składnia

```
class COleControlModule : public CWinApp
```

## <a name="remarks"></a>Uwagi

Ta klasa udostępnia funkcje członkowskie do inicjowania modułu kontroli. Każdy moduł kontrolny OLE, który używa klas Microsoft Foundation, może zawierać tylko jeden obiekt pochodny `COleControlModule` . Ten obiekt jest konstruowany, gdy tworzone są inne obiekty globalne C++. Zadeklaruj obiekt pochodny `COleControlModule` na poziomie globalnym.

Aby uzyskać więcej informacji na temat używania `COleControlModule` klasy, zobacz Klasa [CWinApp](../../mfc/reference/cwinapp-class.md) i [kontrolki ActiveX](../../mfc/mfc-activex-controls.md)artykułów.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWinThread](../../mfc/reference/cwinthread-class.md)

[CWinApp](../../mfc/reference/cwinapp-class.md)

`COleControlModule`

## <a name="requirements"></a>Wymagania

**Nagłówek:** 'afxctl. h

## <a name="see-also"></a>Zobacz też

[Przykład TESTHELP MFC](../../overview/visual-cpp-samples.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)
