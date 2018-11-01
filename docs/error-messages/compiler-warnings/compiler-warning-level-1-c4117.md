---
title: Kompilator ostrzeżenie (poziom 1) C4117
ms.date: 11/04/2016
f1_keywords:
- C4117
helpviewer_keywords:
- C4117
ms.assetid: c45aa281-4cc1-4dfd-bd32-bd7a60ddd577
ms.openlocfilehash: 657963dd0199c1474f0cef566e5a177a16247521
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50466225"
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