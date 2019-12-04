---
title: Błąd kompilatora C3368
ms.date: 11/04/2016
f1_keywords:
- C3368
helpviewer_keywords:
- C3368
ms.assetid: 5bfd5be4-dfa9-4b33-9612-010561b40955
ms.openlocfilehash: 8e67655e90b571ea099572cdc34bc39124fc3271
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2019
ms.locfileid: "74751875"
---
# <a name="compiler-error-c3368"></a>Błąd kompilatora C3368

"deklaracja funkcji": nieprawidłowa Konwencja wywoływania dla języka IDL

W pliku. idl można używać tylko konwencji wywoływania [__stdcall](../../cpp/stdcall.md) lub [__cdecl](../../cpp/cdecl.md) .

Poniższy przykład generuje C3368:

```cpp
// C3368.cpp
// processor: x86
[idl_module(name="Name", dllname="Some.dll")];

[idl_module(name="Name")]
int __fastcall f1();   // C3368
```
