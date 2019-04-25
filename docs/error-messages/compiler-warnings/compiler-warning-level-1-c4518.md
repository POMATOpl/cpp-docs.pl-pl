---
title: Kompilator ostrzeżenie (poziom 1) C4518
ms.date: 11/04/2016
f1_keywords:
- C4518
helpviewer_keywords:
- C4518
ms.assetid: 4ad21004-f076-43fd-99f4-4bf1f9be4c0b
ms.openlocfilehash: 85e0d87094fc355bf63d79bf2eb5b1d06f233542
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160734"
---
# <a name="compiler-warning-level-1-c4518"></a>Kompilator ostrzeżenie (poziom 1) C4518

"specyfikatora": Klasa magazynu lub wpisz specyfikator(y) nieoczekiwane w tym miejscu; ignorowane

Poniższy przykład spowoduje wygenerowanie C4518:

```
// C4518.cpp
// compile with: /c /W1
_declspec(dllexport) extern "C" void MyFunction();   // C4518

extern "C" void MyFunction();   // OK
```