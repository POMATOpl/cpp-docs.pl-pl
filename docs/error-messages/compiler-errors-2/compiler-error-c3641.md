---
description: 'Dowiedz się więcej o: błąd kompilatora C3641'
title: Błąd kompilatora C3641
ms.date: 11/04/2016
f1_keywords:
- C3641
helpviewer_keywords:
- C3641
ms.assetid: e8d3613e-5e8d-46fe-a516-eb7d1de7cd21
ms.openlocfilehash: 391994a5207fe27cea0b33e6d03e5a1fdc30f6c0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239106"
---
# <a name="compiler-error-c3641"></a>Błąd kompilatora C3641

> "*Function*": nieprawidłowa Konwencja wywoływania "calling_convention" dla funkcji skompilowanej z/CLR: Pure lub/CLR: Safe

## <a name="remarks"></a>Uwagi

**/CLR: Pure** i **/CLR:** opcje kompilatora bezpiecznego są przestarzałe w programie Visual Studio 2015 i nieobsługiwane w programie Visual Studio 2017.

Tylko Konwencja wywoływania [__clrcall](../../cpp/clrcall.md) jest dozwolona z [/CLR: Pure](../../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje C3641:

```cpp
// C3641.cpp
// compile with: /clr:pure /c
void __cdecl f() {}   // C3641
```
