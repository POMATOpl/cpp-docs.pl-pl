---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4080'
title: Ostrzeżenie kompilatora (poziom 1) C4080
ms.date: 11/04/2016
f1_keywords:
- C4080
helpviewer_keywords:
- C4080
ms.assetid: 964fb3f4-b9fd-450b-aa23-35cece126172
ms.openlocfilehash: 05dcb119d0c028446f038a2cbd796432c688a8c9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344292"
---
# <a name="compiler-warning-level-1-c4080"></a>Ostrzeżenie kompilatora (poziom 1) C4080

Oczekiwano identyfikatora dla nazwy segmentu; znaleziono "symbol"

Nazwa segmentu w [#pragma alloc_text](../../preprocessor/alloc-text.md) musi być ciągiem lub identyfikatorem. Kompilator ignoruje pragmę, jeśli nie znaleziono prawidłowego identyfikatora.

Poniższy przykład generuje C4080:

```cpp
// C4080.cpp
// compile with: /W1
extern "C" void func(void);

#pragma alloc_text()   // C4080

// try this line to resolve the warning
// #pragma alloc_text("mysection", func)

int main() {
}

void func(void) {
}
```
