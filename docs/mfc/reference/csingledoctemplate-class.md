---
description: 'Dowiedz się więcej na temat: Klasa CSingleDocTemplate'
title: Klasa CSingleDocTemplate
ms.date: 11/04/2016
f1_keywords:
- CSingleDocTemplate
- AFXWIN/CSingleDocTemplate
- AFXWIN/CSingleDocTemplate::CSingleDocTemplate
helpviewer_keywords:
- CSingleDocTemplate [MFC], CSingleDocTemplate
ms.assetid: 4f3a8212-81ee-48a0-ad22-e0ed7c36a391
ms.openlocfilehash: 611cada1c90fa776bafb78f0856658cd1bd0a8e4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264625"
---
# <a name="csingledoctemplate-class"></a>Klasa CSingleDocTemplate

Definiuje szablon dokumentu, który implementuje interfejs pojedynczego dokumentu (SDI).

## <a name="syntax"></a>Składnia

```
class CSingleDocTemplate : public CDocTemplate
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CSingleDocTemplate::CSingleDocTemplate](#csingledoctemplate)|Konstruuje `CSingleDocTemplate` obiekt.|

## <a name="remarks"></a>Uwagi

Aplikacja SDI używa okna głównego ramki do wyświetlania dokumentu; tylko jeden dokument może być otwarty w danym momencie.

Szablon dokumentu definiuje relację między trzema typami klas:

- Klasa dokumentu, z której pochodzą `CDocument` .

- Klasa widoku, która wyświetla dane z klasy dokumentu wymienionej powyżej. Tę klasę można utworzyć z `CView` , `CScrollView` , `CFormView` , lub `CEditView` . (Można również użyć `CEditView` bezpośrednio).

- Klasa okna ramki, która zawiera widok. Dla szablonu dokumentu SDI można utworzyć tę klasę z `CFrameWnd` ; Jeśli nie musisz dostosowywać zachowania okna głównego ramki, możesz użyć `CFrameWnd` bezpośrednio bez tworzenia własnej klasy.

Aplikacja SDI zazwyczaj obsługuje jeden typ dokumentu, więc ma tylko jeden `CSingleDocTemplate` obiekt. Tylko jeden dokument może być otwarty w danym momencie.

Nie musisz wywoływać żadnych funkcji składowych z `CSingleDocTemplate` wyjątkiem konstruktora. Struktura obsługuje `CSingleDocTemplate` obiekty wewnętrznie.

Aby uzyskać więcej informacji na temat korzystania z programu `CSingleDocTemplate` , zobacz [Szablony dokumentów i proces tworzenia dokumentu/widoku](../../mfc/document-templates-and-the-document-view-creation-process.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocTemplate](../../mfc/reference/cdoctemplate-class.md)

`CSingleDocTemplate`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxwin. h

## <a name="csingledoctemplatecsingledoctemplate"></a><a name="csingledoctemplate"></a> CSingleDocTemplate::CSingleDocTemplate

Konstruuje `CSingleDocTemplate` obiekt.

```
CSingleDocTemplate(
    UINT nIDResource,
    CRuntimeClass* pDocClass,
    CRuntimeClass* pFrameClass,
    CRuntimeClass* pViewClass);
```

### <a name="parameters"></a>Parametry

*nIDResource*<br/>
Określa identyfikator zasobów używanych z typem dokumentu. Może to obejmować menu, ikonę, tabelę akceleratorów i zasoby ciągu.

Zasób ciągu składa się z maksymalnie siedmiu podciągów rozdzielonych znakiem "\n" (znak "\n" jest potrzebny jako symbol zastępczy, jeśli podciąg nie jest uwzględniony, ale końcowe znaki "\n" nie są wymagane); te podciągi opisują typ dokumentu. Aby uzyskać informacje na temat podciągów, zobacz [CDocTemplate:: GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring). Ten zasób ciągu znajduje się w pliku zasobów aplikacji. Na przykład:

```RC
// MYCALC.RC
STRINGTABLE PRELOAD DISCARDABLE
BEGIN
  IDR_MAINFRAME "MyCalc Windows Application\nSheet\nWorksheet\n Worksheets (*.myc)\n.myc\nMyCalcSheet\n MyCalc Worksheet"
END
```

Można edytować ten ciąg za pomocą edytora ciągów; cały ciąg pojawia się jako pojedynczy wpis w edytorze ciągów, a nie jako siedem oddzielnych wpisów.

Aby uzyskać więcej informacji na temat tych typów zasobów, zobacz [Edytor ciągów](../../windows/string-editor.md).

*pDocClass*<br/>
Wskazuje `CRuntimeClass` obiekt klasy dokumentu. Ta klasa jest `CDocument` klasą pochodną, która jest definiowana do reprezentowania dokumentów.

*pFrameClass*<br/>
Wskazuje `CRuntimeClass` obiekt klasy okna ramek. Ta klasa może być `CFrameWnd` klasą pochodną lub `CFrameWnd` samą, jeśli chcesz, aby domyślne zachowanie głównego okna ramki było możliwe.

*pViewClass*<br/>
Wskazuje `CRuntimeClass` obiekt klasy widoku. Ta klasa jest `CView` klasą pochodną, która jest definiowana do wyświetlania dokumentów.

### <a name="remarks"></a>Uwagi

Dynamicznie Przydziel `CSingleDocTemplate` obiekt i przekaż go do `CWinApp::AddDocTemplate` `InitInstance` funkcji członkowskiej klasy aplikacji.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCDocViewSDI#13](../../mfc/codesnippet/cpp/csingledoctemplate-class_1.cpp)]

[!code-cpp[NVC_MFCDocViewSDI#14](../../mfc/codesnippet/cpp/csingledoctemplate-class_2.cpp)]

## <a name="see-also"></a>Zobacz także

[Przykład DOCKTOOL MFC](../../overview/visual-cpp-samples.md)<br/>
[Klasa CDocTemplate](../../mfc/reference/cdoctemplate-class.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasa CDocTemplate](../../mfc/reference/cdoctemplate-class.md)<br/>
[Klasa CDocument](../../mfc/reference/cdocument-class.md)<br/>
[Klasa obiektu CFrameWnd](../../mfc/reference/cframewnd-class.md)<br/>
[Klasa CMultiDocTemplate](../../mfc/reference/cmultidoctemplate-class.md)<br/>
[Klasa CView](../../mfc/reference/cview-class.md)<br/>
[Klasa CWinApp](../../mfc/reference/cwinapp-class.md)
