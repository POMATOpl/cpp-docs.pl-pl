---
description: 'Dowiedz się więcej o: błąd kompilatora C2099'
title: Błąd kompilatora C2099
ms.date: 11/04/2016
f1_keywords:
- C2099
helpviewer_keywords:
- C2099
ms.assetid: 30e151ee-d458-4901-b0c0-d45054a913f5
ms.openlocfilehash: 03a021216bdb5228bb2ef9cba961b06161d20948
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97170272"
---
# <a name="compiler-error-c2099"></a>Błąd kompilatora C2099

Inicjator nie jest stałą

Ten błąd jest wystawiany tylko przez kompilator C i występuje tylko w przypadku zmiennych nieautomatycznych.  Kompilator inicjuje zmienne nieautomatyczne na początku programu i wartości, które są inicjowane, muszą być stałe.

## <a name="examples"></a>Przykłady

Poniższy przykład generuje C2099.

```c
// C2099.c
int j;
int *p;
j = *p;   // C2099 *p is not a constant
```

C2099 może również wystąpić, ponieważ kompilator nie jest w stanie wykonać ciągłej łamania na wyrażeniu w obszarze **/FP: Strict** , ponieważ ustawienia środowiska liczby zmiennoprzecinkowej (zobacz [_controlfp_s](../../c-runtime-library/reference/controlfp-s.md) więcej informacji) mogą różnić się od kompilacji w czasie wykonywania.

Gdy stałe łamanie nie powiedzie się, kompilator wywołuje dynamiczną inicjalizację, która nie jest dozwolona w C.

Aby rozwiązać ten problem, skompiluj moduł jako plik. cpp lub Uprość wyrażenie.

Aby uzyskać więcej informacji, zobacz [/FP (Określ zachowanie Floating-Point)](../../build/reference/fp-specify-floating-point-behavior.md).

Poniższy przykład generuje C2099.

```c
// C2099_2.c
// compile with: /fp:strict /c
float X = 2.0 - 1.0;   // C2099
float X2 = 1.0;   // OK
```
