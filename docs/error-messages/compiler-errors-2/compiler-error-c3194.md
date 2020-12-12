---
description: 'Dowiedz się więcej o: błąd kompilatora C3194'
title: Błąd kompilatora C3194
ms.date: 11/04/2016
f1_keywords:
- C3194
helpviewer_keywords:
- C3194
ms.assetid: 49d3ffc6-eff6-4b46-865b-18811692a8bb
ms.openlocfilehash: 7513b9d4964b6eb0024c3b51480f188243bf2637
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97174042"
---
# <a name="compiler-error-c3194"></a>Błąd kompilatora C3194

"member": typ wartości nie może mieć operatora przypisania

Specjalne funkcje członkowskie, które wymagają automatycznego wywołania przez kompilator, takie jak Konstruktor kopiujący lub operator przypisania kopii, nie są obsługiwane w klasie wartości.

## <a name="example"></a>Przykład

Poniższy przykład generuje C3194.

```cpp
// C3194.cpp
// compile with: /clr /c
value struct MyStruct {
   MyStruct& operator= (const MyStruct& i) { return *this; }   // C3194
};

ref struct MyStruct2 {
   MyStruct2% operator= (const MyStruct2% i) { return *this; }   // OK
};
```
