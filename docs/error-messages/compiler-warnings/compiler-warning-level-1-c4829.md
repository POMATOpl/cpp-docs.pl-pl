---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4829'
title: Ostrzeżenie kompilatora (poziom 1) C4829
ms.date: 11/04/2016
f1_keywords:
- C4829
helpviewer_keywords:
- C4829
ms.assetid: 4ffabe2b-2ddc-4c52-8564-d1355c93cfa6
ms.openlocfilehash: ae44c50e7b680dff94427896eea2e10c4ed33483
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97198027"
---
# <a name="compiler-warning-level-1-c4829"></a>Ostrzeżenie kompilatora (poziom 1) C4829

Prawdopodobnie nieprawidłowe parametry dla funkcji main. Rozważmy "intmain (platform:: Array \<Platform::String^> ^ argv)"

Niektóre funkcje, takie jak Main, nie mogą przyjmować parametrów typu odwołania. Gdy kompilacja zakończy się powodzeniem, ostateczny obraz prawdopodobnie nie zostanie uruchomiony.

Poniższy przykład generuje C4829:

```cpp
// C4829.cpp
// compile by using: cl /EHsc /ZW /W4 /c C4829.cpp
int main(Platform::String ^ s) {}   // C4829
```
