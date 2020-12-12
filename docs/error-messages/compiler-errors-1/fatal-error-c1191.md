---
description: 'Dowiedz się więcej na temat: błąd krytyczny C1191'
title: Błąd krytyczny C1191
ms.date: 11/04/2016
f1_keywords:
- C1191
helpviewer_keywords:
- C1191
ms.assetid: 2888c6c4-b4e6-449e-8ee0-7917f31086df
ms.openlocfilehash: ef7f9ec6554daf0d83f3e597877509025512a6d5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123581"
---
# <a name="fatal-error-c1191"></a>Błąd krytyczny C1191

plik "dll" można zaimportować tylko w zakresie globalnym

Instrukcja importowania mscorlib.dll do programu korzystającego z programowania/CLR nie może występować w przestrzeni nazw lub funkcji, ale musi być widoczna w zakresie globalnym.

Poniższy przykład generuje C1191:

```cpp
// C1191.cpp
// compile with: /clr
namespace sample {
   #using <mscorlib.dll>   // C1191 not at global scope
}
```

Możliwe rozwiązanie:

```cpp
// C1191b.cpp
// compile with: /clr /c
#using <mscorlib.dll>
namespace sample {}
```
