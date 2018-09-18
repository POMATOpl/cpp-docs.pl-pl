---
title: Kompilator ostrzeżenie (poziom 4) C4337 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4337
dev_langs:
- C++
helpviewer_keywords:
- C4337
ms.assetid: 70bc72d9-aac5-45cd-abd3-ebe42a05897b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d5b4e72f3dfda903a3d0f4563a730dc44411f79c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46016458"
---
# <a name="compiler-warning-level-4-c4337"></a>Kompilator ostrzeżenie (poziom 4) C4337

Biblioteka typów odsyłaczy "typelib1" w "typelib2" jest automatycznie importowana

Auto_search — atrybut [dyrektywy #import](../../preprocessor/hash-import-directive-cpp.md) spowodowane biblioteki typów do zaimportowania niejawnie.

Danej biblioteki dwa typy na dysku utworzone na podstawie następujące dwa pliki (skompilowany przy użyciu midl.exe):

```
// C4337a.idl
[
  uuid(F87070BA-C6D9-405C-A8E4-8CD9CA25C12B)
]
library C4337aLib
{
   [uuid(F87070BA-C6D9-405C-A8E4-8CD9CA25C12C)]
   enum E_C4337a
   {
      one = 0,
      two = 1,
      three = 2
    };
};
```

a następnie drugiego pliku .idl,

```
// C4337b.idl
[
   uuid(F87070BA-C6D9-405C-A8E4-8CD9CA25C12D)
]

library C4337bLib
{
   importlib("c4337a.tlb");

   [uuid(F87070BA-C6D9-405C-A8E4-8CD9CA25C12E)]
   struct S_C4337b
   {
      enum E_C4337a e;
   };
};
```

Poniższy przykład spowoduje wygenerowanie C4337:

```
// C4337.cpp
// compile with: /W4 /LD
#import "c4337b.tlb" auto_search   // C4337
// explicitly #import all type libraries to resolve
// #import "C4337a.tlb"
// #import "C4337b.tlb"
```