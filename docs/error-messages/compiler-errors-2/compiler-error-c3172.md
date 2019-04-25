---
title: Błąd kompilatora C3172
ms.date: 11/04/2016
f1_keywords:
- C3172
helpviewer_keywords:
- C3172
ms.assetid: 1834e2fd-6036-4c33-aff2-b51bc7c99441
ms.openlocfilehash: 5c9c1561b63c740b9f7f5d85b2bf3e04de2542c0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62175189"
---
# <a name="compiler-error-c3172"></a>Błąd kompilatora C3172

"nazwa_modułu": nie można określić innych atrybutów idl_module w projekcie

[idl_module](../../windows/idl-module.md) atrybutów o tej samej nazwy, ale o innej `dllname` lub `version` parametry zostały znalezione w dwóch plików w kompilacji. Tylko jeden unikatowy `idl_module` atrybut może być określona dla kompilacji.

Identyczne `idl_module` atrybuty można określić w więcej niż jeden plik kodu źródłowego.

Na przykład jeśli następujące `idl_module` znaleziono atrybuty:

```
// C3172.cpp
[module(name="MyMod")];
[ idl_module(name="x", dllname="file.dll", version="1.1") ];
int main() {}
```

Następnie wyszukaj maszynę

```
// C3172b.cpp
// compile with: C3172.cpp
// C3172 expected
[ idl_module(name="x", dllname="file.dll", version="1.0") ];
```

kompilator wygeneruje C3172 (Zwróć uwagę na wartości różnych wersji).