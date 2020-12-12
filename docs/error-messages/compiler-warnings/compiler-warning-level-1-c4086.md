---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4086'
title: Ostrzeżenie kompilatora (poziom 1) C4086
ms.date: 11/04/2016
f1_keywords:
- C4086
helpviewer_keywords:
- C4086
ms.assetid: 9248831b-22bf-47af-8684-bfadb17e94fc
ms.openlocfilehash: e2bb38d781a18b98a386e17ccdb347be9fe0f0df
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278119"
---
# <a name="compiler-warning-level-1-c4086"></a>Ostrzeżenie kompilatora (poziom 1) C4086

Oczekiwano parametru pragma "1", "2", "4", "8" lub "16"

Parametr pragma nie ma wymaganej wartości (1, 2, 4, 8 lub 16).

## <a name="example"></a>Przykład

```cpp
// C4086.cpp
// compile with: /W1 /LD
#pragma pack( 3 ) // C4086
```
