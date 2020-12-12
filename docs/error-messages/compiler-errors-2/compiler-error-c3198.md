---
description: 'Dowiedz się więcej o: błąd kompilatora C3198'
title: Błąd kompilatora C3198
ms.date: 11/04/2016
f1_keywords:
- C3198
helpviewer_keywords:
- C3198
ms.assetid: ec4ecf61-0067-4aa4-b443-a91013a1e59d
ms.openlocfilehash: 8f72dd32af7f004696afd87b7141768f09ea5f12
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321986"
---
# <a name="compiler-error-c3198"></a>Błąd kompilatora C3198

nieprawidłowe użycie zmiennoprzecinkowych pragm: fenv_access pragma działa tylko w trybie precyzyjnym

[fenv_access](../../preprocessor/fenv-access.md) pragma została użyta w ustawieniu [/FP](../../build/reference/fp-specify-floating-point-behavior.md) innym niż **/FP: precyzyjne**.

Poniższy przykład generuje C3198:

```cpp
// C3198.cpp
// compile with: /fp:fast
#pragma fenv_access(on)   // C3198
```
