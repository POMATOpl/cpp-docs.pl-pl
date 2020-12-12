---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4810'
title: Ostrzeżenie kompilatora (poziom 1) C4810
ms.date: 11/04/2016
f1_keywords:
- C4810
helpviewer_keywords:
- C4810
ms.assetid: 39e2cae0-9c1c-4ac1-aaa0-5f661d06085b
ms.openlocfilehash: 4cebcf6b4cabc2539d5fcf25363f573a704ae577
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328097"
---
# <a name="compiler-warning-level-1-c4810"></a>Ostrzeżenie kompilatora (poziom 1) C4810

wartość dyrektywy pragma Pack (show) = = n

To ostrzeżenie jest generowane, gdy używana jest opcja **Pokaż** dyrektywy pragma [pakietu](../../preprocessor/pack.md) . *n* to bieżąca wartość pakietu.

Na przykład poniższy kod pokazuje, jak działa ostrzeżenie C4810 z dyrektywy pragma Pack:

```cpp
// C4810.cpp
// compile with: /W1 /LD
// C4810 expected
#pragma pack(show)
#pragma pack(4)
#pragma pack(show)
```
