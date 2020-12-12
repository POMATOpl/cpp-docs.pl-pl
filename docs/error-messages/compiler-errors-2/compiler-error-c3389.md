---
description: 'Dowiedz się więcej o: błąd kompilatora C3389'
title: Błąd kompilatora C3389
ms.date: 11/04/2016
f1_keywords:
- C3389
helpviewer_keywords:
- C3389
ms.assetid: eaaffe17-23f2-413c-b1ad-f7220cfa1334
ms.openlocfilehash: b9fedf0993738d054cd5ded605d96001b3db13eb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97285503"
---
# <a name="compiler-error-c3389"></a>Błąd kompilatora C3389

> nie można użyć __declspec (*słowo kluczowe*) z/CLR: Pure lub/CLR: Safe

## <a name="remarks"></a>Uwagi

**`/clr:pure`** **`/clr:safe`** Opcje kompilatora i są przestarzałe w programie visual Studio 2015 i nie są obsługiwane w programie visual Studio 2017.

[`__declspec`](../../cpp/declspec.md)Używany modyfikator oznacza stan dla procesu.  [`/clr:pure`](../../build/reference/clr-common-language-runtime-compilation.md) oznacza dla [`appdomain`](../../cpp/appdomain.md) stanu.  Dlatego zadeklarowanie zmiennej z modyfikatorem *słowa kluczowego* **`__declspec`** i kompilowanie za pomocą **`/clr:pure`** nie jest dozwolone.

## <a name="example"></a>Przykład

Poniższy przykład generuje C3389:

```cpp
// C3389.cpp
// compile with: /clr:pure /c
__declspec(dllexport) int g2 = 0;   // C3389
```
