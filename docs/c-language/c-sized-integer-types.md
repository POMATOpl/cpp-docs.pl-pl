---
description: Dowiedz się więcej na temat typów całkowitych o rozmiarze C
title: Typy liczb całkowitych o rozmiarze C
ms.date: 07/22/2020
helpviewer_keywords:
- sized integer types
ms.assetid: 0d6199b4-d0ab-4e8c-a769-785f5afb92eb
ms.openlocfilehash: ad50806f52638884da69e109da252379dea0d571
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97300128"
---
# <a name="c-sized-integer-types"></a>Typy liczb całkowitych o rozmiarze C

**Specyficzne dla firmy Microsoft**

Funkcje Microsoft C obsługują typy liczb całkowitych. Można zadeklarować 8-, 16-, 32-lub 64-bitowe zmienne całkowite przy użyciu `__intN` specyfikatora typu, gdzie *`N`* jest rozmiar w bitach zmiennej całkowitej. Wartość *n* może być 8, 16, 32 lub 64. Poniższy przykład deklaruje jedną zmienną dla każdego z czterech typów liczb całkowitych:

```C
__int8  nSmall;     // Declares 8-bit integer
__int16 nMedium;    // Declares 16-bit integer
__int32 nLarge;     // Declares 32-bit integer
__int64 nHuge;      // Declares 64-bit integer
```

Pierwsze trzy typy liczb całkowitych są synonimami dla typów ANSI, które mają ten sam rozmiar. Są one przydatne do pisania kodu przenośnego, który działa identycznie na wielu platformach. **`__int8`** Typ danych jest synonimem typu **`char`** , **`__int16`** jest synonimem typu **`short`** , **`__int32`** jest synonimem typu **`int`** i **`__int64`** jest synonimem typu **`long long`** .

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Magazyn typów podstawowych](../c-language/storage-of-basic-types.md)
