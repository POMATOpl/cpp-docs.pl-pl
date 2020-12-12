---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4180'
title: Ostrzeżenie kompilatora (poziom 1) C4180
ms.date: 11/04/2016
f1_keywords:
- C4180
helpviewer_keywords:
- C4180
ms.assetid: 40c91bd4-37f1-4d59-a4f3-d5ddab68239b
ms.openlocfilehash: d85097212086d98b70b71837b01ef1522f87580c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97266718"
---
# <a name="compiler-warning-level-1-c4180"></a>Ostrzeżenie kompilatora (poziom 1) C4180

kwalifikator stosowany do typu funkcji nie ma znaczenia; Ignoruj

Kwalifikator, taki jak **`const`** , jest stosowany do typu funkcji zdefiniowanego przez **`typedef`** .

## <a name="example"></a>Przykład

```cpp
// C4180.cpp
// compile with: /W1 /c
typedef int FuncType(void);

// the const qualifier cannot be applied to the
// function type FuncType
const FuncType f;   // C4180
```
