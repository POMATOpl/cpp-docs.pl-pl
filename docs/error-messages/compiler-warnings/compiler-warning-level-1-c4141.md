---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4141'
title: Ostrzeżenie kompilatora (poziom 1) C4141
ms.date: 11/04/2016
f1_keywords:
- C4141
helpviewer_keywords:
- C4141
ms.assetid: 6ce8c058-7f4c-41cf-93e7-90a466744656
ms.openlocfilehash: beb4b45d112be1199c58ccce31723156053d3610
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97115771"
---
# <a name="compiler-warning-level-1-c4141"></a>Ostrzeżenie kompilatora (poziom 1) C4141

"modyfikator": użyto więcej niż raz

## <a name="example"></a>Przykład

```cpp
// C4141.cpp
// compile with: /W1 /LD
inline inline void func ();   // C4141
```
