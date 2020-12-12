---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4518'
title: Ostrzeżenie kompilatora (poziom 1) C4518
ms.date: 11/04/2016
f1_keywords:
- C4518
helpviewer_keywords:
- C4518
ms.assetid: 4ad21004-f076-43fd-99f4-4bf1f9be4c0b
ms.openlocfilehash: 1a04dbcdc62e6758e2b65c6b0ef5aa99a1823ef0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97212301"
---
# <a name="compiler-warning-level-1-c4518"></a>Ostrzeżenie kompilatora (poziom 1) C4518

"specyfikator": nieoczekiwany w tym miejscu Klasa magazynu lub Specyfikatory typu; Ignoruj

Poniższy przykład generuje C4518:

```cpp
// C4518.cpp
// compile with: /c /W1
_declspec(dllexport) extern "C" void MyFunction();   // C4518

extern "C" void MyFunction();   // OK
```
