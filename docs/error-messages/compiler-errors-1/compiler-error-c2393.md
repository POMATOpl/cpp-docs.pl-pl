---
description: 'Dowiedz się więcej o: błąd kompilatora C2393'
title: Błąd kompilatora C2393
ms.date: 11/04/2016
f1_keywords:
- C2393
helpviewer_keywords:
- C2393
ms.assetid: 4bd95728-e813-4ce8-844a-c6ebe235ca82
ms.openlocfilehash: 7cf1b333afac9f976bb4bf38ce769e6982255959
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318991"
---
# <a name="compiler-error-c2393"></a>Błąd kompilatora C2393

> "*symbol*": symbol per-AppDomain nie może zostać alokowany *w segmencie segmentu*

## <a name="remarks"></a>Uwagi

**/CLR: Pure** i **/CLR:** opcje kompilatora bezpiecznego są przestarzałe w programie Visual Studio 2015 i nieobsługiwane w programie Visual Studio 2017.

Użycie zmiennych [AppDomain](../../cpp/appdomain.md) oznacza, że są kompilowane z **/CLR: Pure** lub **/CLR: Safe**, a Bezpieczny lub czysty obraz nie może zawierać segmentów danych.

Zobacz [/CLR (Kompilacja środowiska uruchomieniowego języka wspólnego)](../../build/reference/clr-common-language-runtime-compilation.md) , aby uzyskać więcej informacji.

## <a name="example"></a>Przykład

Poniższy przykład generuje C2393. Aby rozwiązać ten problem, nie należy tworzyć segmentu danych.

```cpp
// C2393.cpp
// compile with: /clr:pure /c
#pragma data_seg("myseg")
int n = 0;   // C2393
```
