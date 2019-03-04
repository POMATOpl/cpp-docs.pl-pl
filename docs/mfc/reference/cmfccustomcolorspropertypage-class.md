---
title: CMFCCustomColorsPropertyPage Class
ms.date: 11/04/2016
f1_keywords:
- CMFCCustomColorsPropertyPage
- AFXCUSTOMCOLORSPROPERTYPAGE/CMFCCustomColorsPropertyPage
- AFXCUSTOMCOLORSPROPERTYPAGE/CMFCCustomColorsPropertyPage::Setup
helpviewer_keywords:
- CMFCCustomColorsPropertyPage [MFC], Setup
ms.assetid: 46a45ba2-1fda-440d-8018-d4dcd44f5816
ms.openlocfilehash: b28711991835dd14929e5387709046c3867c715e
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/04/2019
ms.locfileid: "57299893"
---
# <a name="cmfccustomcolorspropertypage-class"></a>CMFCCustomColorsPropertyPage Class

Reprezentuje stronę właściwości, które może wybrać kolory niestandardowe w oknie dialogowym koloru.

## <a name="syntax"></a>Składnia

```
class CMFCCustomColorsPropertyPage : public CPropertyPage
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|||
|-|-|
|Nazwa|Opis|
|`CMFCCustomColorsPropertyPage::CMFCCustomColorsPropertyPage`|Domyślny konstruktor.|

### <a name="public-methods"></a>Metody publiczne

|||
|-|-|
|Nazwa|Opis|
|`CMFCCustomColorsPropertyPage::CreateObject`|Używane przez platformę do tworzenia dynamicznych wystąpienia tego typu klasy.|
|`CMFCCustomColorsPropertyPage::GetThisClass`|Używane przez architekturę, aby uzyskać wskaźnik do [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) obiektu, który jest skojarzony z tym typem klasy.|
|[CMFCCustomColorsPropertyPage::Setup](#setup)|Ustawia kolor składniki na stronie właściwości.|

### <a name="remarks"></a>Uwagi

`CMFCColorDialog` Klasa korzysta z tej klasy można wyświetlić strony właściwości koloru niestandardowego. Aby uzyskać więcej informacji na temat `CMFCColorDialog`, zobacz [klasa CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md).

## <a name="example"></a>Przykład

W poniższym przykładzie pokazano sposób tworzenia `CMFCCustomColorsPropertyPage` obiektu i ustaw składników koloru na stronie właściwości.

[!code-cpp[NVC_MFC_RibbonApp#35](../../mfc/reference/codesnippet/cpp/cmfccustomcolorspropertypage-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CPropertyPage](../../mfc/reference/cpropertypage-class.md)

[CMFCCustomColorsPropertyPage](../../mfc/reference/cmfccustomcolorspropertypage-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxcustomcolorspropertypage.h

##  <a name="setup"></a>  CMFCCustomColorsPropertyPage::Setup

Ustawia kolor składniki na stronie właściwości.

```
void Setup(
    BYTE R,
    BYTE G,
    BYTE B);
```

### <a name="parameters"></a>Parametry

|||
|-|-|
|Parametr|Opis|
|*R*|[in] Składnik czerwony wartości RGB.|
|*G*|[in] Składnik zielony wartości RGB.|
|*B*|[in] Składnik niebieski wartości RGB.|

### <a name="remarks"></a>Uwagi

Ta metoda aktualizacji bieżący RGB i skojarzone HLS (hue, jasność i nasycenie) wartości kolorów na stronie właściwości. [CMFCColorDialog::SetPageTwo](../../mfc/reference/cmfccolordialog-class.md#setpagetwo) metoda wywołuje tę metodę, gdy struktura inicjuje okno dialogowe kolorów lub naciśnięciu lewego przycisku myszy. Aby uzyskać więcej informacji na temat `CMFCColorDialog`, zobacz [klasa CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md).

## <a name="see-also"></a>Zobacz także

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md)<br/>
[Klasa CMFCStandardColorsPropertyPage](../../mfc/reference/cmfcstandardcolorspropertypage-class.md)
