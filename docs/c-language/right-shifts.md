---
description: 'Dowiedz się więcej na temat: zmiany w prawo'
title: Przesunięcia w prawo
ms.date: 11/04/2016
ms.assetid: c878e97d-ea3c-4c6b-90a8-b1b24b2d5b19
ms.openlocfilehash: 5bc359357e8a3a2e00d0c75012e0e6044d8055f9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97292926"
---
# <a name="right-shifts"></a>Przesunięcia w prawo

Wynik prawej zmiany typu całkowitego ze znakiem z wartością ujemną

Przesunięcie wartości ujemnej na prawo daje połowę wartość bezwzględną, zaokrągloną w dół. Na przykład **`signed short`** wartość-253 (szesnastkowa 0xFF03, binary 11111111 00000011) przesunięcie w prawo o jeden bit produkuje-127 (szesnastkowo 0xFF81, binary 11111111 10000001). Dodatnie przesunięcie w prawo 253 produkuje + 126.

Prawy Shift zachowuje bit znaku podpisanych typów całkowitych. Gdy liczba całkowita ze znakiem zostanie przesunięta w prawo, to najbardziej znaczący bit pozostaje ustawiony. Na przykład jeśli 0xF0000000 jest podpisany **`int`** , przesunięcie w prawo powoduje 0xF8000000. Przesunięcie negatywnego **`int`** prawa 32 razy tworzy 0xFFFFFFFF.

Gdy liczba całkowita bez znaku zostaje przesunięta w prawo, najbardziej znaczący bit jest wyczyszczony. Na przykład jeśli 0xF000 jest niepodpisana, wynikiem jest 0x7800. Przesunięcie **`unsigned`** lub dodatnie **`int`** prawo 32 razy produkuje.

## <a name="see-also"></a>Zobacz też

[Liczby całkowite](../c-language/integers.md)
