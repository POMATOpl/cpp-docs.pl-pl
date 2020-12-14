---
description: 'Dowiedz się więcej o: błąd kompilatora C3895'
title: Błąd kompilatora C3895
ms.date: 11/04/2016
f1_keywords:
- C3895
helpviewer_keywords:
- C3895
ms.assetid: 771b9fe5-d6d4-4297-bf57-e2f857722155
ms.openlocfilehash: ae963eb89ee8f0cefc9092e9d3b16aa40885e63c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315117"
---
# <a name="compiler-error-c3895"></a>Błąd kompilatora C3895

"var": elementy członkowskie danych typu nie mogą być "volatile"

Niektóre rodzaje składowych danych, na przykład [Literal](../../extensions/literal-cpp-component-extensions.md) lub [initonly](../../dotnet/initonly-cpp-cli.md), nie mogą być [nietrwałe](../../cpp/volatile-cpp.md).

Poniższy przykład generuje C3895:

```cpp
// C3895.cpp
// compile with: /clr
ref struct Y1 {
   initonly
   volatile int data_var2;   // C3895
};
```
