---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 4) C4234'
title: Ostrzeżenie kompilatora (poziom 4) C4234
ms.date: 11/04/2016
f1_keywords:
- C4234
helpviewer_keywords:
- C4234
ms.assetid: f7fecd5c-8248-4fde-8446-502aedc357ca
ms.openlocfilehash: 98a3f5bc2c13dec3822342a669f7c9de3dc452fc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334900"
---
# <a name="compiler-warning-level-4-c4234"></a>Ostrzeżenie kompilatora (poziom 4) C4234

użyto niestandardowego rozszerzenia: słowo kluczowe "Keyword" zarezerwowane do użytku w przyszłości

Kompilator nie implementuje jeszcze użytego słowa kluczowego.

To ostrzeżenie jest automatycznie podwyższana do błędu. Jeśli chcesz zmodyfikować to zachowanie, użyj [#pragma ostrzeżenie](../../preprocessor/warning.md). Na przykład, aby C4234 na problem z ostrzeżeniem poziomu 4,

```cpp
#pragma warning(2:4234)
```

w pliku kodu źródłowego.
