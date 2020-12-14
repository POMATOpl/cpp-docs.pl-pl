---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4470'
title: Ostrzeżenie kompilatora (poziom 1) C4470
ms.date: 11/04/2016
f1_keywords:
- C4470
helpviewer_keywords:
- C4470
ms.assetid: f52a3eaa-a235-4747-a47d-9ec4ad4cb0ea
ms.openlocfilehash: 6fe01782fbd2151175bc1da59afa8bd73fa5648d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97310983"
---
# <a name="compiler-warning-level-1-c4470"></a>Ostrzeżenie kompilatora (poziom 1) C4470

dyrektywy kontroli zmiennoprzecinkowej zostały zignorowane w opcji/CLR

Dyrektywy pragma kontroli zmiennoprzecinkowej:

- [fenv_access](../../preprocessor/fenv-access.md)

- [float_control](../../preprocessor/float-control.md)

- [fp_contract](../../preprocessor/fp-contract.md)

nie ma żadnego wpływu na [/CLR](../../build/reference/clr-common-language-runtime-compilation.md).

Poniższy przykład generuje C4470:

```cpp
// C4470.cpp
// compile with: /clr /W1 /LD
#pragma float_control(except, on)   // C4470
```
