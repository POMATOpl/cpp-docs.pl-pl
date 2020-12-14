---
description: 'Dowiedz się więcej o: błąd kompilatora C2768'
title: Błąd kompilatora C2768
ms.date: 11/04/2016
f1_keywords:
- C2768
helpviewer_keywords:
- C2768
ms.assetid: a7f6047a-6a80-4737-ad5c-c12868639fb5
ms.openlocfilehash: 0911153b9b89996631433d8a19bde9d19fc5f6b3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239470"
---
# <a name="compiler-error-c2768"></a>Błąd kompilatora C2768

"Function": niedozwolone użycie argumentów jawnego szablonu

Kompilator nie może określić, czy definicja funkcji powinna być jawną specjalizacją szablonu funkcji, czy też jeśli definicja funkcji miała być dla nowej funkcji.

Ten błąd został wprowadzony w programie Visual Studio .NET 2003 w ramach ulepszeń zgodności kompilatora.

Poniższy przykład generuje C2768:

```cpp
// C2768.cpp
template<typename T>
void f(T) {}

void f<int>(int) {}   // C2768

// an explicit specialization
template<>
void f<int>(int) {}

// global nontemplate function overload
void f(int) {}
```
