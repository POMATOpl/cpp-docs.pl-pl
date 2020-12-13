---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 4) C4235'
title: Ostrzeżenie kompilatora (poziom 4) C4235
ms.date: 11/04/2016
f1_keywords:
- C4235
helpviewer_keywords:
- C4235
ms.assetid: d4214799-d62c-4674-b4e2-9e201c303303
ms.openlocfilehash: 011586efb311cab1da5cd4452bbbc03a942a5045
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334889"
---
# <a name="compiler-warning-level-4-c4235"></a>Ostrzeżenie kompilatora (poziom 4) C4235

użyto niestandardowego rozszerzenia: słowo kluczowe "Keyword" nie jest obsługiwane w tej architekturze

Kompilator nie obsługuje użytego słowa kluczowego.

To ostrzeżenie jest automatycznie podwyższana do błędu. Jeśli chcesz zmodyfikować to zachowanie, użyj [#pragma ostrzeżenie](../../preprocessor/warning.md). Na przykład, aby C4235 na ostrzeżenie poziomu 2, użyj następującego wiersza kodu

```cpp
#pragma warning(2:4235)
```

w pliku kodu źródłowego.
