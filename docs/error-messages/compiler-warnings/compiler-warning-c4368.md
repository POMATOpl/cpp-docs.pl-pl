---
title: Ostrzeżenie kompilatora C4368 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4368
dev_langs:
- C++
helpviewer_keywords:
- C4368
ms.assetid: cb85bcee-fd3d-4aa5-b626-2324f07a4f1b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 52026f08a56faa1372b73b94fe91c96682510038
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46073216"
---
# <a name="compiler-warning-c4368"></a>Ostrzeżenie kompilatora C4368

Nie można zdefiniować "członek" jako członka zarządzanego "type": mieszane typy nie są obsługiwane.

Element członkowski danych natywnych nie można osadzić w typie CLR.

Możliwe, jednak zadeklarować wskaźnika do typu macierzystego i kontrolować jego okres istnienia w Konstruktor i destruktor i finalizator klasy zarządzanej. Aby uzyskać więcej informacji, zobacz [destruktory i finalizatory](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).

To jest zawsze ostrzeżenie jako błąd. Użyj [ostrzeżenie](../../preprocessor/warning.md) pragma może wyłączyć C4368.

## <a name="example"></a>Przykład

Poniższy przykład spowoduje wygenerowanie C4368.

```
// C4368.cpp
// compile with: /clr /c
struct N {};
ref struct O {};
ref struct R {
    R() : m_p( new N ) {}
    ~R() { delete m_p; }

   property N prop;   // C4368
   int i[10];   // C4368

   property O ^ prop2;   // OK
   N * m_p;   // OK
};
```