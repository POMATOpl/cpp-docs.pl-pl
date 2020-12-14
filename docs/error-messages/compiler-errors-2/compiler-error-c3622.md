---
description: 'Dowiedz się więcej o: błąd kompilatora C3622'
title: Błąd kompilatora C3622
ms.date: 11/04/2016
f1_keywords:
- C3622
helpviewer_keywords:
- C3622
ms.assetid: 02836f78-0cf2-4947-b87e-710187d81014
ms.openlocfilehash: 19c599fced524001f360a4ad462a9dbebbfb2fa3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223038"
---
# <a name="compiler-error-c3622"></a>Błąd kompilatora C3622

"Class": nie można utworzyć wystąpienia klasy zadeklarowanej jako "słowo kluczowe"

Podjęto próbę utworzenia wystąpienia klasy oznaczonej jako [abstrakcyjna](../../extensions/abstract-cpp-component-extensions.md). Klasa oznaczona jako **`abstract`** może być klasą bazową, ale nie można jej utworzyć.

## <a name="example"></a>Przykład

Poniższy przykład generuje C3622.

```cpp
// C3622.cpp
// compile with: /clr
ref class a abstract {};

int main() {
   a aa;   // C3622
}
```
