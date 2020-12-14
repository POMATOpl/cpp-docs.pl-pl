---
description: 'Dowiedz się więcej o: błąd kompilatora C3170'
title: Błąd kompilatora C3170
ms.date: 11/04/2016
f1_keywords:
- C3170
helpviewer_keywords:
- C3170
ms.assetid: ca9a59d6-7df3-42f0-b028-c09d0af3ac2a
ms.openlocfilehash: c799d3c62b32e87aadd02b22f22bb20db25ff16b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242239"
---
# <a name="compiler-error-c3170"></a>Błąd kompilatora C3170

nie może mieć innych identyfikatorów modułu w projekcie

atrybuty [modułu](../../windows/attributes/module-cpp.md) o różnych nazwach znajdują się w dwóch plikach w kompilacji. `module`Dla kompilacji można określić tylko jeden unikatowy atrybut.

Identyczne `module` atrybuty można określić w więcej niż jednym pliku kodu źródłowego.

Na przykład jeśli znaleziono następujące atrybuty modułu:

```cpp
// C3170.cpp
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f") ];
int main() {}
```

A następnie

```cpp
// C3170b.cpp
// compile with: C3170.cpp
// C3170 expected
[ module(name="MyModule1", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f") ];
```

kompilator generuje C3170 (należy pamiętać o różnych nazwach).
