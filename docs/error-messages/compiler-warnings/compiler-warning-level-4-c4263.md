---
title: Ostrzeżenie kompilatora (poziom 4) C4263
ms.date: 11/04/2016
f1_keywords:
- C4263
helpviewer_keywords:
- C4263
ms.assetid: daabb05d-ab56-460f-ab6c-c74d222ef649
ms.openlocfilehash: ea41f16420f847616b5bcb2c092ff187a14f7175
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541653"
---
# <a name="compiler-warning-level-4-c4263"></a>Ostrzeżenie kompilatora (poziom 4) C4263

"Function": funkcja członkowska nie przesłania żadnej wirtualnej funkcji składowej klasy bazowej

Definicja funkcji klasy ma taką samą nazwę jak funkcja wirtualna w klasie bazowej, ale nie ma tej samej liczby lub typu argumentów. Efektywnie ukrywa funkcję wirtualną w klasie bazowej.

To ostrzeżenie jest domyślnie wyłączone. Aby uzyskać więcej informacji [, zobacz ostrzeżenia kompilatora, które są domyślnie wyłączone](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Poniższy przykład generuje C4263:

```cpp
// C4263.cpp
// compile with: /W4
#pragma warning(default:4263)
#pragma warning(default:4264)
class B {
public:
   virtual void func();
};

class D : public B {
   void func(int);   // C4263
};

int main() {
}
```