---
description: 'Dowiedz się więcej o: błąd kompilatora C3510'
title: Błąd kompilatora C3510
ms.date: 11/04/2016
f1_keywords:
- C3510
helpviewer_keywords:
- C3510
ms.assetid: c48387bc-0300-4a4d-97f7-3fb90f82a451
ms.openlocfilehash: 97727f22e94993cff051c57b5692e9a14c9ab930
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315429"
---
# <a name="compiler-error-c3510"></a>Błąd kompilatora C3510

nie można zlokalizować biblioteki typów zależnych "type_lib"

[no_registry](../../preprocessor/no-registry.md) i [auto_search](../../preprocessor/auto-search.md) zostały przesłane do, `#import` ale kompilator nie mógł odnaleźć przywoływanej biblioteki typów.

Aby rozwiązać ten problem, upewnij się, że wszystkie biblioteki typów i biblioteki typów, do których istnieją odwołania, są dostępne dla kompilatora.

Poniższy przykład generuje C3510:

Załóżmy, że zostały skompilowane następujące dwie biblioteki typów i że C3510a. tlb został usunięty z ścieżki.

```
// C3510a.idl
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12b")]
library C3510aLib
{
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12c")]
   enum E_C3510
   {
      one, two, three
   };
};
```

A następnie kod źródłowy dla drugiej biblioteki typów:

```
// C3510b.idl
// post-build command: del /f C3510a.tlb
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12e")]
library C3510bLib
{
   importlib ("C3510a.tlb");
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12d")]
   struct S_C3510 {
      enum E_C3510 e;
   };
};
```

A następnie kod klienta:

```cpp
// C3510.cpp
#import "c3510b.tlb" no_registry auto_search   // C3510
int main() {
   C3510aLib::S_C4336 ccc;
}
```
