---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 4) C4263'
title: Ostrzeżenie kompilatora (poziom 4) C4263
ms.date: 11/04/2016
f1_keywords:
- C4263
helpviewer_keywords:
- C4263
ms.assetid: daabb05d-ab56-460f-ab6c-c74d222ef649
ms.openlocfilehash: 7b7eb7fdf8e66ab5d09c8dc0f9511d3c88162084
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339155"
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
