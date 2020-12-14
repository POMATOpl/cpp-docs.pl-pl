---
description: 'Dowiedz się więcej o: błąd kompilatora C2435'
title: Błąd kompilatora C2435
ms.date: 11/04/2016
f1_keywords:
- C2435
helpviewer_keywords:
- C2435
ms.assetid: be6aa8f8-579b-42ea-bdd8-2d01393646ad
ms.openlocfilehash: d0ab5d8c7c45c9636a5e48acc17d3ac379c755a9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97189941"
---
# <a name="compiler-error-c2435"></a>Błąd kompilatora C2435

> "*var*": dynamiczna Inicjalizacja wymaga zarządzanego CRT, nie można kompilować z/CLR: Safe

## <a name="remarks"></a>Uwagi

**/CLR: Pure** i **/CLR:** opcje kompilatora bezpiecznego są przestarzałe w programie Visual Studio 2015 i nieobsługiwane w programie Visual Studio 2017.

Inicjalizacja globalnej zmiennej domeny dla aplikacji wymaga skompilowania CRT z `/clr:pure` , który nie produkuje obrazu do zweryfikowania.

Aby uzyskać więcej informacji, zobacz temat [AppDomain](../../cpp/appdomain.md) i [Process](../../cpp/process.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje C2435:

```cpp
// C2435.cpp
// compile with: /clr:safe /c
int globalvar = 0;   // C2435

__declspec(process)
int globalvar2 = 0;
```
