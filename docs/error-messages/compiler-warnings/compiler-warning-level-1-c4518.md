---
title: Kompilator ostrzeżenie (poziom 1) C4518 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4518
dev_langs:
- C++
helpviewer_keywords:
- C4518
ms.assetid: 4ad21004-f076-43fd-99f4-4bf1f9be4c0b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 90936d7ad695cb826e7fc58798706822ca1b8f24
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46037791"
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