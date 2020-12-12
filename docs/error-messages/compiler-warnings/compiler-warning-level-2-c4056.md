---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 2) C4056'
title: Ostrzeżenie kompilatora (poziom 2) C4056
ms.date: 11/04/2016
f1_keywords:
- C4056
helpviewer_keywords:
- C4056
ms.assetid: a3c3a9b8-ec30-452d-96cb-3694adcce789
ms.openlocfilehash: 5d8b96e97197e43bf288476e310ddd842a90ec48
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326547"
---
# <a name="compiler-warning-level-2-c4056"></a>Ostrzeżenie kompilatora (poziom 2) C4056

przepełnienie w zmiennoprzecinkowej stałej arytmetycznej

Stała zmiennoprzecinkowa arytmetyczna generuje wynik, który przekracza maksymalną dozwoloną wartość.

To ostrzeżenie może być spowodowane optymalizacją kompilatora wykonywaną podczas arytmetycznej stałej. Możesz bezpiecznie zignorować to ostrzeżenie, Jeśli wyłączysz opcję Optymalizacja ([/od](../../build/reference/od-disable-debug.md)).

Poniższy przykład generuje C4056:

```cpp
// C4056.cpp
// compile with: /W2 /LD
#pragma warning (default : 4056)
float fp_val = 1.0e300 * 1.0e300;   // C4056
```
