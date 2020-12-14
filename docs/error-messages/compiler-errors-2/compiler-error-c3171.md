---
description: 'Dowiedz się więcej o: błąd kompilatora C3171'
title: Błąd kompilatora C3171
ms.date: 11/04/2016
f1_keywords:
- C3171
helpviewer_keywords:
- C3171
ms.assetid: 1ce26997-7ef1-4c9f-84da-003ea1a4251e
ms.openlocfilehash: 65e7e1db9a864b894a0bce825df09a372489a79d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242200"
---
# <a name="compiler-error-c3171"></a>Błąd kompilatora C3171

"module": nie można określić innych atrybutów modułu w projekcie

atrybuty [modułu](../../windows/attributes/module-cpp.md) o różnych listach parametrów znaleziono w dwóch plikach w kompilacji. `module`Dla kompilacji można określić tylko jeden unikatowy atrybut.

Identyczne `module` atrybuty można określić w więcej niż jednym pliku kodu źródłowego.

Na przykład jeśli `module` znaleziono następujące atrybuty:

```cpp
// C3171.cpp
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f", version="1.0") ];
int main() {}
```

A następnie

```cpp
// C3171b.cpp
// compile with: C3171.cpp
// C3171 expected
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f", version="1.1") ];
```

kompilator generuje C3171 (zanotuj różne wartości wersji).
