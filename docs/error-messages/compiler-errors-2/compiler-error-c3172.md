---
title: Błąd kompilatora C3172 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3172
dev_langs:
- C++
helpviewer_keywords:
- C3172
ms.assetid: 1834e2fd-6036-4c33-aff2-b51bc7c99441
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 25c3b1fd9132c6b170fdf74b1619a35d83959f90
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46117643"
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