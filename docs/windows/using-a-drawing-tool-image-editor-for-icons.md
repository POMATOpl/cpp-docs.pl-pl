---
description: 'Dowiedz się więcej na temat: jak używać narzędzia do rysowania'
title: 'Instrukcje: korzystanie z narzędzia do rysowania'
ms.date: 02/15/2019
f1_keywords:
- vc.editors.image.drawing
helpviewer_keywords:
- Image editor [C++], selecting drawing tools
- Image editor [C++], toolbar
- drawing tools
- Image editor [C++], drawing lines
- shapes, drawing
- colors [C++], brush
- brushes, colors
- brushes, creating custom
- images [C++], creating custom brushes
- graphics [C++], custom brushes
- custom brushes
ms.assetid: 1f8c6eef-7760-45a9-a5cb-9e15c6f91245
ms.openlocfilehash: 9415b81eb520b626186fe321184bd1d7d7391b61
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97283267"
---
# <a name="how-to-use-a-drawing-tool"></a>Instrukcje: korzystanie z narzędzia do rysowania

**Edytor obrazów** zawiera narzędzia do rysowania i wymazywania, które działają w taki sam sposób. Użytkownik wybiera narzędzie i, w razie potrzeby, [wybiera kolor pierwszego planu i tła](./image-editor-for-icons.md) oraz opcje rozmiaru i kształtu. Następnie można przenieść wskaźnik do obrazu i kliknąć lub przeciągnąć, aby narysować i wymazać.

## <a name="drawing-tools"></a>Narzędzia do rysowania

Narzędzia do rysowania można wybrać za pomocą paska narzędzi **edytora obrazu** lub menu **obraz** . Po wybraniu narzędzia **Gumka** , narzędzia **pędzel** lub narzędzia **aerografu** , selektor opcji wyświetla opcje tego narzędzia.

> [!TIP]
> Etykietki narzędzi są wyświetlane po umieszczeniu wskaźnika myszy nad przyciskami na [pasku narzędzi edytora obrazów](./image-editor-for-icons.md). Te porady ułatwią zidentyfikowanie określonych przycisków wymienionych tutaj.

### <a name="to-select-and-use-a-drawing-tool-from-the-image-editor-toolbar"></a>Aby wybrać narzędzie rysowania i użyć go na pasku narzędzi edytora obrazu

1. Wybierz przycisk na pasku narzędzi **edytora obrazów** .

   - Narzędzie **Gumka** maluje na obrazie przy użyciu bieżącego koloru tła po naciśnięciu lewego przycisku myszy.

      > [!TIP]
      > Zamiast korzystać z narzędzia **Gumka** , przydatne może być Rysowanie w kolorze tła za pomocą jednego z narzędzi do rysowania.

   - Narzędzie **ołówek** rysuje FreeHand w stałej szerokości jednego piksela.

   - Narzędzie **pędzel** ma różne kształty i rozmiary.

   - Narzędzie **aerografu** losowo dystrybuuje piksele kolorów wokół środka pędzla.

1. W razie potrzeby wybierz pozycję kolory i Pędzel:

   - W [palecie kolorów](./image-editor-for-icons.md)wybierz lewy przycisk myszy, aby wybrać kolor pierwszego planu lub prawy przycisk myszy, aby wybrać kolor tła.

   - W [selektorze opcji](./image-editor-for-icons.md)wybierz kształt reprezentujący Pędzel, którego chcesz użyć.

1. Wskaż miejsce na obrazie, w którym chcesz rozpocząć rysowanie lub malowanie. Wskaźnik zmienia kształt zgodnie z wybranym narzędziem.

1. Naciśnij lewy przycisk myszy (kolor pierwszego planu) lub prawy przycisk myszy (dla koloru tła) i przytrzymaj go podczas rysowania.

### <a name="to-select-and-use-a-drawing-tool-from-the-image-menu"></a>Aby wybrać narzędzie rysowania z menu obrazu i korzystać z niego

1. Przejdź do menu   >  **Narzędzia** obrazu.

1. W podmenu kaskadowym wybierz narzędzie, którego chcesz użyć.

## <a name="lines-or-closed-figures"></a>Linie lub zamknięte figury

Narzędzia **edytora obrazu** do rysowania linii i zamkniętych figur działają w ten sam sposób: punkt wstawiania należy umieścić w jednym punkcie i przeciągnąć do innego. W przypadku linii punkty te są punktami końcowymi. W przypadku zamkniętych liczb te punkty są przeciwległe do rogów prostokąta.

Linie są rysowane w szerokości określonej przez bieżący wybór pędzla, a liczby ramek są rysowane w szerokości ustalonej przez bieżącą szerokość. Linie i wszystkie cyfry, zarówno z ramką, jak i wypełnione, są rysowane w bieżącym kolorze pierwszego planu, jeśli naciśniesz lewy przycisk myszy lub w bieżącym kolorze tła, jeśli naciśniesz prawy przycisk myszy.

### <a name="to-draw-a-line"></a>Aby narysować linię

1. Użyj [paska narzędzi edytora obrazu](./image-editor-for-icons.md) lub przejdź do menu  >  **Narzędzia** obrazu i wybierz narzędzie **linia** .

1. W razie potrzeby wybierz pozycję kolory i Pędzel:

   - W [palecie kolorów](./image-editor-for-icons.md)wybierz lewy przycisk myszy, aby wybrać kolor pierwszego planu lub prawy przycisk myszy, aby wybrać kolor tła.

   - W [selektorze opcji](./image-editor-for-icons.md)wybierz kształt reprezentujący Pędzel, którego chcesz użyć.

1. Umieść wskaźnik w punkcie początkowym wiersza.

1. Przeciągnij do punktu końcowego wiersza.

### <a name="to-draw-a-closed-figure"></a>Aby narysować figurę zamkniętą

1. Użyj paska narzędzi **edytora obrazu** lub przejdź do menu   >  **Narzędzia** obrazu i wybierz narzędzie do **rysowania zamkniętego rysunku** .

   Narzędzia do **rysowania z zamkniętą** ilustracją tworzą rysunki zgodnie z ich odpowiednimi przyciskami.

1. W razie potrzeby wybierz opcję kolory i szerokość linii.

1. Przesuń wskaźnik do jednego rogu prostokątnego obszaru, w którym ma nastąpić rysowanie rysunku.

1. Przeciągnij wskaźnik do ukośnie przeciwległego rogu.

## <a name="custom-brushes"></a>Pędzle niestandardowe

Pędzel niestandardowy to prostokątna część obrazu, który można pobrać i użyć jak jednego z gotowych pędzli **edytora obrazu**. Wszystkie operacje, które można wykonać w ramach zaznaczenia, można również wykonać na niestandardowym pędzlu.

### <a name="to-create-a-custom-brush-from-a-portion-of-an-image"></a>Aby utworzyć pędzel niestandardowy na podstawie fragmentu obrazu

1. Wybierz część obrazu, która ma być używana dla pędzla.

1. Przytrzymaj klawisz **SHIFT** , wybierz opcję w zaznaczeniu i przeciągnij ją na obrazie lub przejdź do **obrazu** menu  >  **Użyj opcji zaznacz jako pędzel**.

   Wybór zostanie przekształcony w niestandardowy Pędzel, który dystrybuuje kolory w zaznaczeniu na obrazie. Kopie zaznaczenia są pozostawiane wzdłuż ścieżki przeciągania. Im wolniej przeciągniesz, tym więcej kopii jest wykonanych.

   > [!NOTE]
   > Wybranie opcji **Użyj zaznaczenia jako pędzla** bez wcześniejszego wyboru części obrazu spowoduje użycie całego obrazu jako pędzla. Wynik użycia pędzla niestandardowego zależeć również od tego, czy wybrano [tło nieprzezroczyste, czy przezroczyste](./image-editor-for-icons.md).

Piksele w pędzlu niestandardowym, które pasują do bieżącego koloru tła są zwykle przezroczyste: nie malują na istniejącym obrazie. To zachowanie można zmienić tak, aby piksele koloru tła malować na istniejącym obrazie.

Możesz użyć niestandardowego pędzla, takiego jak stempel lub wzornik, aby utworzyć różne efekty specjalne.

### <a name="to-draw-custom-brush-shapes-in-the-background-color"></a>Aby narysować niestandardowe kształty pędzla w kolorze tła

1. Wybierz tło nieprzezroczyste lub przezroczyste.

1. Ustaw kolor tła na kolor, który ma być rysowany.

1. Umieść pędzla niestandardowego, który ma zostać narysowany.

1. Wybierz prawy przycisk myszy. Wszystkie nieprzezroczyste regiony niestandardowego pędzla są rysowane kolorem tła.

### <a name="to-double-or-halve-the-custom-brush-size"></a>Aby dwukrotnie lub połowę rozmiaru pędzla niestandardowego

Naciśnij klawisz **znaku plus** ( **+** ), aby dwukrotnie zmienić rozmiar pędzla lub klawisza **minus** ( **-** ), aby je pomniejszać.

### <a name="to-cancel-the-custom-brush"></a>Aby anulować pędzel niestandardowy

Naciśnij klawisz **ESC** lub wybierz inne narzędzie rysowania.

## <a name="requirements"></a>Wymagania

Brak

## <a name="see-also"></a>Zobacz też

[Edytor obrazów dla ikon](../windows/image-editor-for-icons.md)<br/>
[Instrukcje: Tworzenie ikony lub innego obrazu](../windows/creating-an-icon-or-other-image-image-editor-for-icons.md)<br/>
[Instrukcje: Edytowanie obrazu](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md)<br/>
[Instrukcje: korzystanie z koloru](../windows/working-with-color-image-editor-for-icons.md)<br/>
[Klawisze skrótów](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
