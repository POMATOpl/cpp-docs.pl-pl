---
title: Kompilator ostrzeżenie (poziom 1) C4098 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4098
dev_langs:
- C++
helpviewer_keywords:
- C4098
ms.assetid: 8c8aef1c-1639-44ec-a3dd-c0dfe9aa727d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 84b3cdcdbb487774a92361d3a003ba83895d475e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118313"
---
# <a name="compiler-warning-level-1-c4098"></a>Kompilator ostrzeżenie (poziom 1) C4098

'Funkcja': void funkcja zwraca wartość

Funkcja zadeklarowana z typem zwracanym [void](../../cpp/void-cpp.md) ma `return` instrukcji, która nie zwraca wartości. Kompilator zakłada, funkcja zwraca wartość typu `int`.