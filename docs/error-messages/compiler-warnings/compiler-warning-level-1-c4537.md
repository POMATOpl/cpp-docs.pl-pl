---
title: Kompilator ostrzeżenie (poziom 1) C4537 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4537
dev_langs:
- C++
helpviewer_keywords:
- C4537
ms.assetid: 9454493c-d419-475e-8f35-9c00233c9329
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 052d11d5bdf269d950abe1ef761adc055cbc6ce3
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/29/2018
ms.locfileid: "43213366"
---
# <a name="compiler-warning-level-1-c4537"></a>Kompilator ostrzeżenie (poziom 1) C4537

> "*obiektu*": "*operator*" zastosowany do typu innego niż UDT

## <a name="remarks"></a>Uwagi

Odwołanie został przekazany, gdy Oczekiwano obiektu (typ zdefiniowany przez użytkownika). Odwołanie nie jest obiektem, ale kodem wbudowanego asemblera nie będzie mógł wprowadzić rozróżnienia. Kompilator generuje kod tak, jakby *obiektu* zostały wystąpienia.

## <a name="example"></a>Przykład

Poniższy przykład generuje C4537 i pokazuje, jak go naprawić:

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