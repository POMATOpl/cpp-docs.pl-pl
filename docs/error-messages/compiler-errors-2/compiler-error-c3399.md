---
description: 'Dowiedz się więcej o: błąd kompilatora C3399'
title: Błąd kompilatora C3399
ms.date: 11/04/2016
f1_keywords:
- C3399
helpviewer_keywords:
- C3399
ms.assetid: 306ad199-d150-4f6c-bcf1-24a7948b93be
ms.openlocfilehash: a950857e88c5cfcad50ac2efb064af4d7a5c0cf1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316430"
---
# <a name="compiler-error-c3399"></a>Błąd kompilatora C3399

"Type": nie można podać argumentów podczas tworzenia wystąpienia parametru generycznego

Podczas określania `gcnew()` ograniczenia należy określić, że typ ograniczenia będzie miał Konstruktor bez parametrów. W związku z tym, wystąpił błąd podczas próby utworzenia wystąpienia tego typu i przekazania parametru.

Aby uzyskać więcej informacji, zobacz [ograniczenia dotyczące parametrów typu ogólnego (C++/CLI)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md) .

## <a name="example"></a>Przykład

Poniższy przykład generuje C3399.

```cpp
// C3399.cpp
// compile with: /clr /c
generic <class T>
where T : gcnew()
void f() {
   T t = gcnew T(1);   // C3399
   T t2 = gcnew T();   // OK
}
```
