---
description: 'Dowiedz się więcej na temat: Klasa CFormView'
title: Klasa CFormView
ms.date: 11/04/2016
f1_keywords:
- CFormView
- AFXEXT/CFormView
- AFXEXT/CFormView::CFormView
- AFXEXT/CFormView::IsInitDlgCompleted
helpviewer_keywords:
- CFormView [MFC], CFormView
- CFormView [MFC], IsInitDlgCompleted
ms.assetid: a99ec313-36f0-4f28-9d2b-de11de14ac19
ms.openlocfilehash: ec37a3819f299830fef96bfdf93c0170b2969c66
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184312"
---
# <a name="cformview-class"></a>Klasa CFormView

Klasa bazowa używana do wyświetlania widoków formularzy.

## <a name="syntax"></a>Składnia

```
class CFormView : public CScrollView
```

## <a name="members"></a>Elementy członkowskie

### <a name="protected-constructors"></a>Konstruktory chronione

|Nazwa|Opis|
|----------|-----------------|
|[CFormView:: CFormView](#cformview)|Konstruuje `CFormView` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CFormView:: IsInitDlgCompleted](#isinitdlgcompleted)|Używany do synchronizacji podczas inicjalizacji.|

## <a name="remarks"></a>Uwagi

Widok formularza jest zasadniczo widokiem zawierającym formanty. Te kontrolki są ustalane na podstawie zasobu szablonu okna dialogowego. Użyj `CFormView` , jeśli chcesz użyć formularzy w aplikacji. Te widoki obsługują przewijanie, w razie potrzeby, przy użyciu funkcji [CScrollView](../../mfc/reference/cscrollview-class.md) .

Podczas [tworzenia aplikacji Forms-Based](../../mfc/reference/creating-a-forms-based-mfc-application.md)można oprzeć jej klasy widoku na `CFormView` , tworząc aplikację opartą na formularzach.

Możesz także wstawiać nowe [Tematy formularzy](../../mfc/form-views-mfc.md) do aplikacji opartych na widoku dokumentu. Nawet jeśli Twoja aplikacja nie obsługuje wstępnie formularzy, Visual C++ doda to wsparcie podczas wstawiania nowego formularza.

Kreator aplikacji MFC i polecenie Dodaj klasy są preferowanymi metodami tworzenia aplikacji opartych na formularzach. Jeśli musisz utworzyć aplikację opartą na formularzach bez używania tych metod, zobacz [Tworzenie aplikacji Forms-Based](../../mfc/reference/creating-a-forms-based-mfc-application.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CScrollView](../../mfc/reference/cscrollview-class.md)

`CFormView`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxext. h

## <a name="cformviewcformview"></a><a name="cformview"></a> CFormView:: CFormView

Konstruuje `CFormView` obiekt.

```
CFormView(LPCTSTR lpszTemplateName);
CFormView(UINT nIDTemplate);
```

### <a name="parameters"></a>Parametry

*lpszTemplateName*<br/>
Zawiera ciąg zakończony znakiem null, który jest nazwą zasobu szablonu okna dialogowego.

*nIDTemplate*<br/>
Zawiera numer IDENTYFIKACYJNy zasobu szablonu okna dialogowego.

### <a name="remarks"></a>Uwagi

Podczas tworzenia obiektu typu pochodnego `CFormView` wywoływanie jednego z konstruktorów w celu utworzenia obiektu widoku i zidentyfikowania zasobu okna dialogowego, w którym jest oparty ten widok. Zasób można zidentyfikować według nazwy (przekazać ciąg jako argument do konstruktora) lub według jego identyfikatora (przekazać jako argument liczbę całkowitą bez znaku).

Okna widoku Formularz i kontrolki podrzędne nie są tworzone, dopóki nie `CWnd::Create` zostanie wywołana. `CWnd::Create` jest wywoływany przez platformę w ramach procesu tworzenia dokumentu i widoku, który jest oparty na szablonie dokumentu.

> [!NOTE]
> Klasa pochodna *musi* dostarczyć własnego konstruktora. W konstruktorze Wywołaj konstruktora, `CFormView::CFormView` przy użyciu nazwy zasobu lub identyfikatora jako argumentu, jak pokazano w poprzedniej klasie przegląd.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCDocView#90](../../mfc/codesnippet/cpp/cformview-class_1.h)]

[!code-cpp[NVC_MFCDocView#91](../../mfc/codesnippet/cpp/cformview-class_2.cpp)]

## <a name="cformviewisinitdlgcompleted"></a><a name="isinitdlgcompleted"></a> CFormView:: IsInitDlgCompleted

Używany przez MFC, aby upewnić się, że inicjalizacja została ukończona przed wykonaniem innych operacji.

```
BOOL IsInitDlgCompleted() const;
```

### <a name="return-value"></a>Wartość zwracana

Prawda, jeśli funkcja inicjowania dla tego okna dialogowego została ukończona.

## <a name="see-also"></a>Zobacz też

[Przykład SNAPVW MFC](../../overview/visual-cpp-samples.md)<br/>
[Przykład VIEWEX MFC](../../overview/visual-cpp-samples.md)<br/>
[Klasa CScrollView](../../mfc/reference/cscrollview-class.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasa CDialog](../../mfc/reference/cdialog-class.md)<br/>
[Klasa CScrollView](../../mfc/reference/cscrollview-class.md)
