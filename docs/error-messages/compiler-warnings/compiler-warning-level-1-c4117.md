---
title: Kompilator ostrzeżenie (poziom 1) C4117 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4117
dev_langs:
- C++
helpviewer_keywords:
- C4117
ms.assetid: c45aa281-4cc1-4dfd-bd32-bd7a60ddd577
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 675f5465e30977575c018d7c76b2b7516d4c5a56
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46077246"
---
# <a name="compiler-warning-level-1-c4117"></a>Kompilator ostrzeżenie (poziom 1) C4117

Nazwa makro "name" jest zarezerwowana; 'Command' ignorowane

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aby rozwiązać problem, sprawdzając następujące możliwe przyczyny

1. Zdefiniuj lub usuń definicję wstępnie zdefiniowane makro.

1. Próby zdefiniuj lub usuń definicję — operator preprocesora **zdefiniowane**.

Poniższy przykład spowoduje wygenerowanie C4117:

```
// C4117.cpp
// compile with: /W1
#define __FILE__ test         // C4117. __FILE__ is a predefined macro
#define ValidMacroName test   // ok

int main() {
}
```