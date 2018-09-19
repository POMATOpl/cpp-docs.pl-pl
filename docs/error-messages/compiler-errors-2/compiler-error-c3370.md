---
title: Błąd kompilatora C3370 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3370
dev_langs:
- C++
helpviewer_keywords:
- C3370
ms.assetid: ee6d4c85-78fc-42b2-836e-5cc491a3b2ba
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0dfd3ed72e379af754af53422842f88911916a79
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46135818"
---
# <a name="compiler-error-c3370"></a>Błąd kompilatora C3370

"idl_module name": idl_module jeszcze nie jest zdefiniowana

Przed użyciem [idl_module](../../windows/idl-module.md) do określonego punktu wejścia w bibliotece DLL, należy najpierw użyć `idl_module` do określenia nazwy biblioteki DLL.

Poniższy przykład spowoduje wygenerowanie C3370:

```
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