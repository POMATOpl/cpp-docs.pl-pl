---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4537'
title: Ostrzeżenie kompilatora (poziom 1) C4537
ms.date: 08/27/2018
f1_keywords:
- C4537
helpviewer_keywords:
- C4537
ms.assetid: 9454493c-d419-475e-8f35-9c00233c9329
ms.openlocfilehash: 39219361445832f51160311733c77d3becd8bc5f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294772"
---
# <a name="compiler-warning-level-1-c4537"></a>Ostrzeżenie kompilatora (poziom 1) C4537

> "*Object*": "*operator*" został zastosowany do typu innego niż UDT

## <a name="remarks"></a>Uwagi

Odwołanie zostało przesłane, gdy oczekiwano obiektu (typu zdefiniowanego przez użytkownika). Odwołanie nie jest obiektem, ale wbudowany kod asemblera nie może dokonać rozróżnienia. Kompilator generuje kod, jakby *obiekt* był wystąpieniem.

## <a name="example"></a>Przykład

Poniższy przykład generuje C4537 i pokazuje, jak to naprawić:

```cpp
// C4537.cpp
// compile with: /W1 /c
// processor: x86
struct S {
    int member;
};

void f1(S &s) {
    __asm mov eax, s.member;   // C4537
    // try the following code instead
    // or, make the declaration "void f1(S s)"
    /*
    mov eax, s
    mov eax, [eax]s.member
    */
}
```
