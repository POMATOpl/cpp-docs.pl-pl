---
description: 'Dowiedz się więcej na temat: Klasa CMFCRibbonApplicationButton'
title: Klasa CMFCRibbonApplicationButton
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonApplicationButton
- AFXRIBBONBAR/CMFCRibbonApplicationButton
- AFXRIBBONBAR/CMFCRibbonApplicationButton::CMFCRibbonApplicationButton
- AFXRIBBONBAR/CMFCRibbonApplicationButton::SetImage
helpviewer_keywords:
- CMFCRibbonApplicationButton [MFC], CMFCRibbonApplicationButton
- CMFCRibbonApplicationButton [MFC], SetImage
ms.assetid: beb81757-fabd-4641-9130-876ba8505b78
ms.openlocfilehash: 391274c7540e7e52a19c20e17a09b25f37badcd6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97289806"
---
# <a name="cmfcribbonapplicationbutton-class"></a>Klasa CMFCRibbonApplicationButton

Implementuje specjalny przycisk znajdujący się w lewym górnym rogu okna aplikacji. Po kliknięciu przycisku otwiera menu, które zwykle zawiera typowe polecenia dotyczące **plików** , takie jak **Otwórz**, **Zapisz** i **Wyjdź**.

## <a name="syntax"></a>Składnia

```
class CMFCRibbonApplicationButton : public CMFCRibbonButton
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCRibbonApplicationButton::CMFCRibbonApplicationButton](#cmfcribbonapplicationbutton)|Konstruuje i inicjuje `CMFCRibbonApplicationButton` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|`CMFCRibbonApplicationButton::CreateObject`|Używane przez platformę do tworzenia wystąpienia dynamicznego tego typu klasy.|
|`CMFCRibbonApplicationButton::GetThisClass`|Używane przez platformę do uzyskania wskaźnika do obiektu [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) , który jest skojarzony z tym typem klasy.|
|[CMFCRibbonApplicationButton:: SetImage](#setimage)|Przypisuje obraz do przycisku aplikacji wstążki.|

## <a name="example"></a>Przykład

Poniższy przykład ilustruje sposób użycia różnych metod w `CMFCRibbonApplicationButton` klasie. W przykładzie pokazano, jak przypisać obraz do przycisku aplikacji oraz jak ustawić jego etykietkę narzędzi. Ten fragment kodu jest częścią [przykładu rysowania klienta](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_DrawClient#4](../../mfc/reference/codesnippet/cpp/cmfcribbonapplicationbutton-class_1.h)]
[!code-cpp[NVC_MFC_DrawClient#5](../../mfc/reference/codesnippet/cpp/cmfcribbonapplicationbutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonApplicationButton](../../mfc/reference/cmfcribbonapplicationbutton-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxRibbonBar. h

## <a name="cmfcribbonapplicationbuttoncmfcribbonapplicationbutton"></a><a name="cmfcribbonapplicationbutton"></a> CMFCRibbonApplicationButton::CMFCRibbonApplicationButton

Tworzy i inicjuje obiekt [CMFCRibbonApplicationButton](../../mfc/reference/cmfcribbonapplicationbutton-class.md) .

```
CMFCRibbonApplicationButton();
CMFCRibbonApplicationButton(UINT uiBmpResID);
CMFCRibbonApplicationButton(HBITMAP hBmp);
```

### <a name="parameters"></a>Parametry

*uiBmpResID*<br/>
Identyfikator zasobu obrazu, który ma być wyświetlany na przycisku aplikacji.

*hBmp*<br/>
Uchwyt mapy bitowej, który będzie wyświetlany na przycisku aplikacji.

### <a name="remarks"></a>Uwagi

Przycisk aplikacji wstążki jest specjalnym przyciskiem, który znajduje się w lewym górnym rogu okna aplikacji. Gdy użytkownik kliknie ten przycisk, aplikacja otworzy menu, które zwykle zawiera typowe polecenia **plików** , takie jak **Otwórz**, **Zapisz** i **Zakończ**.

## <a name="cmfcribbonapplicationbuttonsetimage"></a><a name="setimage"></a> CMFCRibbonApplicationButton:: SetImage

Przypisuje obraz do przycisku aplikacji.

```cpp
void SetImage(UINT uiBmpResID);
void SetImage(HBITMAP hBmp);
```

### <a name="parameters"></a>Parametry

*uiBmpResID*<br/>
podczas Identyfikator zasobu obrazu, który ma być wyświetlany na przycisku aplikacji.

*hBmp*<br/>
podczas Uchwyt mapy bitowej, który będzie wyświetlany na przycisku aplikacji.

### <a name="remarks"></a>Uwagi

Użyj tej metody, aby przypisać nowy obraz do przycisku aplikacji wstążki po utworzeniu przycisku. Przycisk aplikacji znajduje się w lewym górnym rogu okna aplikacji.

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)
