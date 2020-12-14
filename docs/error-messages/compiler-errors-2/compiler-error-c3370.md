---
description: 'Dowiedz się więcej o: błąd kompilatora C3370'
title: Błąd kompilatora C3370
ms.date: 11/04/2016
f1_keywords:
- C3370
helpviewer_keywords:
- C3370
ms.assetid: ee6d4c85-78fc-42b2-836e-5cc491a3b2ba
ms.openlocfilehash: 9c34636f91035177e7408dfd4b3bdaaed0fe84c9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245268"
---
# <a name="compiler-error-c3370"></a>Błąd kompilatora C3370

"idl_module Name": nie idl_module jeszcze zdefiniowane

Aby można było użyć [idl_module](../../windows/attributes/idl-module.md) do określenia punktu wejścia w bibliotece DLL, należy najpierw użyć, `idl_module` Aby określić nazwę biblioteki DLL.

Poniższy przykład generuje C3370:

```cpp
// C3370.cpp
[module(name=MyLibrary)];
// uncomment the following line to resolve the error
// [idl_module(name="name1", dllname=x.dll)];
[idl_module(name="name1"), entry(100)] // C3370
int f1();

int main()
{
}
```
