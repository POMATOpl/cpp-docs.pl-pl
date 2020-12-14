---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4742'
title: Ostrzeżenie kompilatora (poziom 1) C4742
ms.date: 07/22/2020
f1_keywords:
- C4742
helpviewer_keywords:
- C4742
ms.assetid: e520881d-1eeb-48b1-9df0-8017ee8ba076
ms.openlocfilehash: 009c8b894b9c53d3a0c802dbb0f5786fc9934b57
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228524"
---
# <a name="compiler-warning-level-1-c4742"></a>Ostrzeżenie kompilatora (poziom 1) C4742

> element "*Variable*" ma inne wyrównanie w "*plik1*" i "*plik2*": *Liczba1* i *liczba2*

Zmienna zewnętrzna, do której odwołuje się lub została zdefiniowana w dwóch plikach, ma inne wyrównanie w tych plikach.

## <a name="remarks"></a>Uwagi

To ostrzeżenie jest emitowane po znalezieniu przez kompilator, że **`alignof`** dla zmiennej w *plik1* różni się od **`alignof`** dla zmiennej w *plik2*. Może to być spowodowane użyciem niezgodnych typów podczas deklarowania zmiennej w różnych plikach lub przy użyciu niezgodnych `#pragma pack` z innymi plikami.

Aby rozwiązać to ostrzeżenie, należy użyć tej samej definicji typu lub użyć różnych nazw dla zmiennych.

Aby uzyskać więcej informacji, zobacz [`pack`](../../preprocessor/pack.md) i [ `alignof` operator](../../cpp/alignof-operator.md).

## <a name="example"></a>Przykład

Jest to pierwszy plik, który definiuje typ.

```c
// C4742a.c
// compile with: /c
struct X {
   char x, y, z, w;
} global;
```

Poniższy przykład generuje C4742.

```c
// C4742b.c
// compile with: C4742a.c /W1 /GL
// C4742 expected
extern struct X {
   int a;
} global;

int main() {
   global.a = 0;
}
```
