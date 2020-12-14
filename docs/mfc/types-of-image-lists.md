---
description: 'Dowiedz się więcej na temat: typy list obrazów'
title: Typy list obrazów
ms.date: 11/04/2016
helpviewer_keywords:
- lists [MFC], image
- image lists [MFC], types of
- CImageList class [MFC], types
ms.assetid: bee5e7c3-78f5-4037-a136-9c50d67cdee5
ms.openlocfilehash: be18a523db366813a236fd4fd94bbb001345f0d1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263741"
---
# <a name="types-of-image-lists"></a>Typy list obrazów

Istnieją dwa typy list obrazów ([Korzystanie CImageList](../mfc/reference/cimagelist-class.md)): niemaskowane i maskowane. "Lista obrazów niemaskowanych" składa się z mapy bitowej koloru, która zawiera co najmniej jeden obraz. "Lista zamaskowanych obrazów" składa się z dwóch map bitowych o równym rozmiarze. Pierwsza to mapa bitowa koloru, która zawiera obrazy, a druga to mapa bitowa monochromatyczny, która zawiera szereg masek — jeden dla każdego obrazu w pierwszej mapie bitowej.

Jedno z przeciążeń `Create` funkcji składowej przyjmuje flagę, aby wskazać, czy lista obrazów jest zamaskowane. (Inne przeciążenia tworzą listę zamaskowanych obrazów).

Po narysowaniu obrazu niemaskowanego jest on po prostu kopiowany do kontekstu urządzenia docelowego; oznacza to, że jest on rysowany na istniejącym kolorze tła kontekstu urządzenia. Po narysowaniu zamaskowanego obrazu bity obrazu są łączone z bitami maski, zwykle wytwarzając przezroczyste obszary w mapie bitowej, w której widoczny jest kolor tła kontekstu urządzenia docelowego. Możesz określić kilka stylów rysowania podczas rysowania maskowanego obrazu. Na przykład można określić, że obraz ma zostać wyszukany w celu wskazania zaznaczonego obiektu.

## <a name="see-also"></a>Zobacz też

[Korzystanie z CImageList](../mfc/using-cimagelist.md)<br/>
[Formanty](../mfc/controls-mfc.md)
