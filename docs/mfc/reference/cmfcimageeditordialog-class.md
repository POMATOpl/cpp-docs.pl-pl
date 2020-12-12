---
description: 'Dowiedz się więcej na temat: Klasa CMFCImageEditorDialog'
title: Klasa CMFCImageEditorDialog
ms.date: 11/19/2018
f1_keywords:
- CMFCImageEditorDialog
- AFXIMAGEEDITORDIALOG/CMFCImageEditorDialog
- AFXIMAGEEDITORDIALOG/CMFCImageEditorDialog::CMFCImageEditorDialog
helpviewer_keywords:
- CMFCImageEditorDialog [MFC], CMFCImageEditorDialog
ms.assetid: 6a7d08f3-1ec2-4062-9b79-a0c2776b58d1
ms.openlocfilehash: 6c25cf4a1a8d0cc5852049a06c3a140cbb00a118
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265392"
---
# <a name="cmfcimageeditordialog-class"></a>Klasa CMFCImageEditorDialog

`CMFCImageEditorDialog`Klasa obsługuje okno dialogowe Edytor obrazów.

## <a name="syntax"></a>Składnia

```
class CMFCImageEditorDialog : public CDialogEx
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCImageEditorDialog::CMFCImageEditorDialog](#cmfcimageeditordialog)|Konstruuje `CMFCImageEditorDialog` obiekt.|

## <a name="remarks"></a>Uwagi

`CMFCImageEditorDialog`Klasa zawiera okno dialogowe, które zawiera:

- Obszar obrazu, który służy do modyfikowania pojedynczych pikseli w obrazie.

- Narzędzia do rysowania pozwalające modyfikować piksele w obszarze obrazu.

- Paleta kolorów określająca kolor używany przez narzędzia do rysowania.

- Obszar podglądu, który wyświetla efekt edycji.

Na poniższej ilustracji przedstawiono okno dialogowe Edytor obrazu.

![CMFCImageEditorDialog — okno dialogowe](../../mfc/reference/media/imageedit.png "CMFCImageEditorDialog — okno dialogowe")

Jednym ze sposobów używania `CMFCImageEditorDialog` obiektu jest przekazanie `CBitmap` obrazu do edycji. Nie twórz dużego obrazu, ponieważ obszar edycji obrazu ma ograniczony rozmiar, a rozmiar logicznego piksela jest dopasowywany do obszaru. Wywołaj `DoModal` metodę, aby uruchomić modalne okno dialogowe.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CDialogEx](../../mfc/reference/cdialogex-class.md)

[CMFCImageEditorDialog](../../mfc/reference/cmfcimageeditordialog-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afximageeditordialog. h

## <a name="cmfcimageeditordialogcmfcimageeditordialog"></a><a name="cmfcimageeditordialog"></a> CMFCImageEditorDialog::CMFCImageEditorDialog

Konstruuje `CMFCImageEditorDialog` obiekt.

```
CMFCImageEditorDialog(
    CBitmap* pBitmap,
    CWnd* pParent=NULL,
    int nBitsPixel=-1);
```

### <a name="parameters"></a>Parametry

*pBitmap*<br/>
Wskaźnik do obrazu.

*pParent*<br/>
Wskaźnik do okna nadrzędnego w bieżącym edytorze obrazu okna dialogowego.

*nBitsPixel*<br/>
Liczba bitów używanych do reprezentowania koloru pojedynczego piksela, która jest również określana jako głębia koloru.  Jeśli parametr *nBitsPixel* ma wartość-1, głębia kolorów pochodzi od obrazu określonego przez parametr *pBitmap* . Wartość domyślna to -1.

### <a name="return-value"></a>Wartość zwracana

Aby zmodyfikować obraz, Przekaż wskaźnik obrazu do `CMFCImageEditorDialog` konstruktora. Następnie Wywołaj `DoModal` metodę, aby otworzyć modalne okno dialogowe. Gdy `DoModal` Metoda zwraca, mapa bitowa zawiera nowy obraz.

### <a name="remarks"></a>Uwagi

### <a name="example"></a>Przykład

Poniższy przykład ilustruje sposób konstruowania obiektu `CMFCImageEditorDialog` klasy. Ten przykład jest częścią [nowych kontrolek](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_NewControls#8](../../mfc/reference/codesnippet/cpp/cmfcimageeditordialog-class_1.cpp)]
[!code-cpp[NVC_MFC_NewControls#40](../../mfc/reference/codesnippet/cpp/cmfcimageeditordialog-class_2.cpp)]

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)
