---
description: 'Dowiedz się więcej o: błąd kompilatora C2130'
title: Błąd kompilatora C2130
ms.date: 11/04/2016
f1_keywords:
- C2130
helpviewer_keywords:
- C2130
ms.assetid: c6fd5a7e-8f28-4f67-99d1-95a13b0dff90
ms.openlocfilehash: 78e7b756d5902562c6093e3f26f9934e87e732ff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323184"
---
# <a name="compiler-error-c2130"></a>Błąd kompilatora C2130

\#wiersz oczekiwał ciągu zawierającego nazwę pliku, znaleziono "token"

Opcjonalny token nazwy pliku następujący [#line](../../preprocessor/hash-line-directive-c-cpp.md) `linenumber` musi być ciągiem.

Poniższy przykład generuje C2130:

```cpp
// C2130.cpp
int main() {
   #line 1000 test   // C2130
   #line 1000 "test"   // OK
}
```
