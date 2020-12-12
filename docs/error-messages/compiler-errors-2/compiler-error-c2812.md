---
description: 'Dowiedz się więcej o: błąd kompilatora C2812'
title: Błąd kompilatora C2812
ms.date: 11/04/2016
f1_keywords:
- C2812
helpviewer_keywords:
- C2812
ms.assetid: 22aadb8c-7232-489d-a3ad-60662dda30a8
ms.openlocfilehash: d59105397ae773c2a46b04a64eb50da3055c3a4b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278428"
---
# <a name="compiler-error-c2812"></a>Błąd kompilatora C2812

> \#import nie jest obsługiwany z/CLR: Pure i/CLR: Safe

## <a name="remarks"></a>Uwagi

**/CLR: Pure** i **/CLR:** opcje kompilatora bezpiecznego są przestarzałe w programie Visual Studio 2015 i nieobsługiwane w programie Visual Studio 2017.

[dyrektywa #import](../../preprocessor/hash-import-directive-cpp.md) nie jest obsługiwana z **/CLR: Pure** i **/CLR: Safe** `#import` , ponieważ wymaga użycia natywnych bibliotek obsługi kompilatora.

## <a name="example"></a>Przykład

Poniższy przykład generuje C2812.

```cpp
// C2812.cpp
// compile with: /clr:pure /c
#import "importlib.tlb"   // C2812
```
