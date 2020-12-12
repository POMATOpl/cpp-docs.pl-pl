---
description: Dowiedz się więcej na temat typów stałych typu parametru Variant
title: Stałe typów parametru Variant
ms.date: 11/04/2016
f1_keywords:
- VTS_YPOS_HIMETRIC
- VTS_PICTURE
- VTS_FONT
- VTS_XPOS_HIMETRIC
- VTS_XPOS_PIXELS
- VTS_XSIZE_HIMETRIC
- VTS_YPOS_PIXELS
- VTS_TRISTATE
- VTS_HANDLE
- VTS_YSIZE_HIMETRIC
- VTS_COLOR
- VTS_OPTEXCLUSIVE
- VTS_YSIZE_PIXELS
- VTS_XSIZE_PIXELS
helpviewer_keywords:
- VTS_XPOS_HIMETRIC constant [MFC]
- VTS_FONT constant [MFC]
- VTS_XPOS_PIXELS constant [MFC]
- VTS_COLOR constant [MFC]
- Variants [MFC]
- VTS_YPOS_PIXELS constant [MFC]
- VTS_YSIZE_HIMETRIC constant [MFC]
- VTS_YPOS_HIMETRIC constant [MFC]
- Variants, parameter type constants
- Variant data constants [MFC]
- VTS_PICTURE constant [MFC]
- VTS_TRISTATE constant [MFC]
- VTS_XSIZE_HIMETRIC constant [MFC]
- VTS_HANDLE constant [MFC]
- VTS_XSIZE_PIXELS constant [MFC]
- VTS_OPTEXCLUSIVE constant [MFC]
- VTS_YSIZE_PIXELS constant [MFC]
ms.assetid: de99c7a9-7aae-4dc4-b723-40c6380543ab
ms.openlocfilehash: 5bc3dcc8a0a888b21b88700db99b05c0f12a4c5e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218501"
---
# <a name="variant-parameter-type-constants"></a>Stałe typów parametru Variant

W tym temacie wymieniono nowe stałe wskazujące typy parametrów wariantów przeznaczone do użycia z klasami formantów OLE biblioteka MFC.

Poniżej znajduje się lista stałych klasy:

## <a name="variant-data-constants"></a><a name="_mfc_variant_data_constants"></a> Stałe danych wariantu

- VTS_COLOR 32-bitowej liczby całkowitej używanej do reprezentowania wartości koloru RGB.

- VTS_FONT wskaźnik do `IFontDisp` interfejsu obiektu czcionki OLE.

- VTS_HANDLE wartość dojścia systemu Windows.

- VTS_PICTURE wskaźnik do `IPictureDisp` interfejsu obiektu obrazu OLE.

- VTS_OPTEXCLUSIVE wartość 16-bitowa użytą dla kontrolki, która jest przeznaczona do użycia w grupie kontrolek, takiej jak przyciski radiowe. Ten typ informuje kontener, że jeśli jedna kontrolka w grupie ma wartość TRUE, wszystkie pozostałe muszą mieć wartość FALSE.

- VTS_TRISTATE 16-bitową liczbę całkowitą ze znakiem używaną dla właściwości, które mogą mieć jedną z trzech możliwych wartości (wybrane, wyczyszczone, niedostępne), na przykład pole wyboru.

- VTS_XPOS_HIMETRIC 32-bitową liczbę całkowitą bez znaku użytą do reprezentowania pozycji wzdłuż osi x w jednostkach HIMETRIC.

- VTS_YPOS_HIMETRIC 32-bitową liczbę całkowitą bez znaku użytą do reprezentowania pozycji wzdłuż osi y w jednostkach HIMETRIC.

- VTS_XPOS_PIXELS 32-bitową liczbę całkowitą bez znaku użytą do reprezentowania pozycji wzdłuż osi x w pikselach.

- VTS_YPOS_PIXELS 32-bitową liczbę całkowitą bez znaku użytą do reprezentowania pozycji wzdłuż osi y w pikselach.

- VTS_XSIZE_PIXELS 32-bitową liczbę całkowitą bez znaku użytą do reprezentowania szerokości obiektu ekranu w pikselach.

- VTS_YSIZE_PIXELS 32-bitową liczbę całkowitą bez znaku służącą do reprezentowania wysokości obiektu ekranu w pikselach.

- VTS_XSIZE_HIMETRIC 32-bitową liczbę całkowitą bez znaku użytą do reprezentowania szerokości obiektu ekranu w jednostkach HIMETRIC.

- VTS_YSIZE_HIMETRIC 32-bitową liczbę całkowitą bez znaku służącą do reprezentowania wysokości obiektu ekranu w jednostkach HIMETRIC.

    > [!NOTE]
    >  Dodatkowe stałe wariantowe zostały zdefiniowane dla wszystkich typów wariantów, z wyjątkiem VTS_FONT i VTS_PICTURE, które zapewniają wskaźnik do stałej danych Variant. Te stałe są nazwane przy użyciu `constantname` konwencji VTS_P. Na przykład VTS_PCOLOR jest wskaźnikiem do stałej VTS_COLOR.

## <a name="requirements"></a>Wymagania

**Nagłówek:** AFXDISP. h

## <a name="see-also"></a>Zobacz też

[Makra i Globals](../../mfc/reference/mfc-macros-and-globals.md)
