---
description: 'Dowiedz się więcej o: błąd kompilatora C3084'
title: Błąd kompilatora C3084
ms.date: 11/04/2016
f1_keywords:
- C3084
helpviewer_keywords:
- C3084
ms.assetid: 0362cb70-e24e-476f-a24d-8f5bb97c3afd
ms.openlocfilehash: 8603930e9087f1e407d5e8df65078604836b9a16
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320122"
---
# <a name="compiler-error-c3084"></a>Błąd kompilatora C3084

"Function": finalizator/destruktor nie może być "słowo kluczowe"

Finalizator lub destruktor został niepoprawnie zadeklarowany.

Na przykład destruktor nie powinien być oznaczony jako zapieczętowany.  Destruktor będzie niedostępny dla typów pochodnych.  Aby uzyskać więcej informacji, zobacz [jawne zastąpienia](../../extensions/explicit-overrides-cpp-component-extensions.md) i [destruktory oraz finalizatory w instrukcje: Definiowanie i korzystanie z klas i struktur (C++/CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).

## <a name="example"></a>Przykład

Poniższy przykład generuje C3084.

```cpp
// C3084.cpp
// compile with: /clr /c
ref struct R {
protected:
   !R() sealed;   // C3084
   !R() abstract;   // C3084
   !R();
};
```
