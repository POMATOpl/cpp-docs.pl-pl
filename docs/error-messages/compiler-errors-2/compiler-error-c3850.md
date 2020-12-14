---
description: 'Dowiedz się więcej o: błąd kompilatora C3850'
title: Błąd kompilatora C3850
ms.date: 09/05/2018
f1_keywords:
- C3850
helpviewer_keywords:
- C3850
ms.assetid: 028f3a37-f3ad-4ebc-9168-3cdea47524d4
ms.openlocfilehash: 9563ee8b4ebb2f8c08b67ff88401ef2e3022a03a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97255343"
---
# <a name="compiler-error-c3850"></a>Błąd kompilatora C3850

> "*char*": nazwa typu uniwersalnego określa nieprawidłowy znak

## <a name="remarks"></a>Uwagi

Znaki reprezentowane jako uniwersalne nazwy znaków muszą reprezentować prawidłowe punkty kodu Unicode w zakresie 0 – 10FFFF. Nazwa znaku uniwersalnego nie może zawierać wartości w zakresie surogatu Unicode, D800-DFFF ani zakodowanej pary zastępczej. Kompilator generuje parę surogatów z prawidłowego punktu kodu.

W kodzie skompilowanym jako C, uniwersalna nazwa znaku nie może reprezentować znaku w zakresie 0000-009F, włącznie, z wyjątkami 0024 ("$"), 0040 (" \@ ") i 0060 ("" ").

W kodzie skompilowanym jako C++ nazwa znaku uniwersalnego może używać dowolnego prawidłowego punktu kodu Unicode w ciągu lub w literale znakowym. Poza literałem, uniwersalna nazwa znaku nie może reprezentować znaku kontrolnego w zakresach 0000-001F lub 007F-009F, zarówno włącznie, jak i elementów członkowskich podstawowego zestawu znaków źródłowych.  Aby uzyskać więcej informacji, zobacz [zestawy znaków](../../cpp/character-sets.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje C3850 i pokazuje, jak go naprawić:

```cpp
// C3850.cpp
int main() {
   int \u0019 = 0;   // C3850, not in allowed range for an identifier
   const wchar_t * wstr_bad  = L"\UD840DC8A"; // C3850, UCN is surrogate pair
   const wchar_t * wstr_good = L"\U0002008A"; // Okay, UCN is valid code point
}
```
