---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4087'
title: Ostrzeżenie kompilatora (poziom 1) C4087
ms.date: 11/04/2016
f1_keywords:
- C4087
helpviewer_keywords:
- C4087
ms.assetid: 546e4d57-5c8e-422c-8ef1-92657336dad5
ms.openlocfilehash: 2375ad5c99862f7ee8a0156ca1b3d637b95f0569
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97267550"
---
# <a name="compiler-warning-level-1-c4087"></a>Ostrzeżenie kompilatora (poziom 1) C4087

"Function": zadeklarowano z listą parametrów "void"

Deklaracja funkcji nie ma formalnych parametrów, ale wywołanie funkcji ma rzeczywiste parametry. Dodatkowe parametry są przesyłane zgodnie z konwencją wywoływania funkcji.

To ostrzeżenie dotyczy kompilatora języka C.

## <a name="example"></a>Przykład

```c
// C4087.c
// compile with: /W1
int f1( void ) {
}

int main() {
   f1( 10 );   // C4087
}
```
