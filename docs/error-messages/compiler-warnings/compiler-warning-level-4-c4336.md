---
title: Kompilator ostrzeżenie (poziom 4) C4336
ms.date: 11/04/2016
f1_keywords:
- C4336
helpviewer_keywords:
- C4336
ms.assetid: 93f199dd-d6dd-42c0-82d8-c12d101a7235
ms.openlocfilehash: 4946b932fa897dab057e430f16c781e2d06bebd0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50484893"
---
# <a name="compiler-warning-level-4-c4336"></a>Kompilator ostrzeżenie (poziom 4) C4336

Importowanie typów odsyłaczy biblioteki "type_lib1" przed importem "type_lib2"

Odwołanie do biblioteki typów z [#import](../../preprocessor/hash-import-directive-cpp.md) dyrektywy. Jednak biblioteka typów zawiera odwołanie do innej biblioteki typów, który nie był przywoływany z `#import`. Pliku .tlb znaleziono przez kompilator.

Danej biblioteki dwa typy na dysku utworzone na podstawie następujące dwa pliki (skompilowany przy użyciu midl.exe):

```
// c4336a.idl
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12b")]
library c4336aLib
{
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12c")]
   enum E_C4336
   {
      one, two, three
   };
};
```

Drugi Biblioteka typów:

```
// c4336b.idl
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12d")]
library C4336bLib
{
   importlib ("c4336a.tlb");
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12e")]
   struct S_C4336
   {
      enum E_C4336 e;
   };
};
```

Poniższy przykład spowoduje wygenerowanie C4336:

```
// C4336.cpp
// compile with: /W4 /LD
// #import "C4336a.tlb"
#import "C4336b.tlb"   // C4336, uncomment previous line to resolve
```