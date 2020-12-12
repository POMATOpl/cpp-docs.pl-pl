---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4117'
title: Ostrzeżenie kompilatora (poziom 1) C4117
ms.date: 11/04/2016
f1_keywords:
- C4117
helpviewer_keywords:
- C4117
ms.assetid: c45aa281-4cc1-4dfd-bd32-bd7a60ddd577
ms.openlocfilehash: 2c7b80c2e1a9e155e0196c2b62857d56877857b9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97267407"
---
# <a name="compiler-warning-level-1-c4117"></a>Ostrzeżenie kompilatora (poziom 1) C4117

Nazwa makra "name" jest zastrzeżona; Zignorowano polecenie "Command"

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aby rozwiązać ten problem, sprawdzając następujące możliwe przyczyny

1. Próba zdefiniowania lub usunięcia wstępnie zdefiniowanego makra.

1. Próba zdefiniowania lub usunięcia **definicji zdefiniowanego** operatora preprocesora.

Poniższy przykład generuje C4117:

```cpp
// C4117.cpp
// compile with: /W1
#define __FILE__ test         // C4117. __FILE__ is a predefined macro
#define ValidMacroName test   // ok

int main() {
}
```
