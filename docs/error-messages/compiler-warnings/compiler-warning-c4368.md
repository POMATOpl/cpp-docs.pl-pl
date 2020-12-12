---
description: 'Dowiedz się więcej na temat: Ostrzeżenie kompilatora C4368'
title: Ostrzeżenie kompilatora C4368
ms.date: 11/04/2016
f1_keywords:
- C4368
helpviewer_keywords:
- C4368
ms.assetid: cb85bcee-fd3d-4aa5-b626-2324f07a4f1b
ms.openlocfilehash: 106d8b0bb0dc70f03017892e8597c0cf059016cd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97180789"
---
# <a name="compiler-warning-c4368"></a>Ostrzeżenie kompilatora C4368

nie można zdefiniować elementu "member" jako elementu członkowskiego zarządzanego "Type": typy mieszane nie są obsługiwane.

Nie można osadzić natywnej składowej danych w typie CLR.

Można jednak zadeklarować wskaźnik do typu natywnego i kontrolować jego okres istnienia w konstruktorze i destruktorze oraz finalizatorze klasy zarządzanej. Aby uzyskać więcej informacji [, zobacz Destruktory i finalizatory](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).

To ostrzeżenie jest zawsze emitowane jako błąd. Użyj [ostrzeżenia](../../preprocessor/warning.md) pragma, aby wyłączyć C4368.

## <a name="example"></a>Przykład

Poniższy przykład generuje C4368.

```cpp
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
