---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4627'
title: Ostrzeżenie kompilatora (poziom 1) C4627
ms.date: 09/09/2018
f1_keywords:
- C4627
helpviewer_keywords:
- C4627
ms.assetid: 8840f3e6-b496-423a-8635-eb55d5f854a2
ms.openlocfilehash: fc4c6c3931775b090dfd4c7c2fd5fd97441d40d3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281447"
---
# <a name="compiler-warning-level-1-c4627"></a>Ostrzeżenie kompilatora (poziom 1) C4627

> "*HEADER_FILE*": pominięto podczas wyszukiwania użycia prekompilowanego nagłówka

Jeśli bieżący plik źródłowy ma ustawioną opcję [/Yu \( Użyj prekompilowanego pliku nagłówkowego)](../../build/reference/yu-use-precompiled-header-file.md) , kompilator zignoruje wszystko w pliku przed włączeniem prekompilowanego nagłówka. Ostrzeżenie **C4627** jest generowana w programie Visual Studio 2015 i starszych wersjach, jeśli *HEADER_FILE* jest zawarty przed prekompilowanym plikiem nagłówkowym, a prekompilowany nagłówek nie zawiera również *HEADER_FILE*.

## <a name="example"></a>Przykład

Ten przykład pokazuje, jak może wystąpić błąd, i pokazuje, jak go naprawić:

```cpp
// c4627.cpp
#include <iostream>       // C4627 - iostream not included by pch.h
#include "pch.h"          // precompiled header file that does not include iostream
// #include <iostream>    // To fix, move the iostream header include here from above
int main()
{
    std::cout << "std::cout is defined!\n";
}
```

## <a name="see-also"></a>Zobacz też

[Tworzenie prekompilowanych plików nagłówka](../../build/creating-precompiled-header-files.md)
