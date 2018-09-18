---
title: Błąd kompilatora C3611 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3611
dev_langs:
- C++
helpviewer_keywords:
- C3611
ms.assetid: 42f3e320-41de-420a-bd05-8924cab765aa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6bc7f1f96e774c7b0dd9df2f760d9c45a522de1c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46039650"
---
# <a name="compiler-error-c3611"></a>Błąd kompilatora C3611

'Funkcja': funkcja zapieczętowana nie może mieć czystego specyfikatora

Funkcja zapieczętowana zadeklarowano niepoprawnie.  Aby uzyskać więcej informacji, zobacz [zapieczętowanego](../../windows/sealed-cpp-component-extensions.md).

## <a name="example"></a>Przykład

Poniższy przykład spowoduje wygenerowanie C3611.

```
// C3611.cpp
// compile with: /clr /c

ref struct V {
   virtual void Test() sealed = 0;   // C3611
   virtual void Test2() sealed;   // OK
   virtual void Test3() = 0;   // OK
};
```