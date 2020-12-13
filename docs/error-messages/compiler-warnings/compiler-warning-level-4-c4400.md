---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 4) C4400'
title: Ostrzeżenie kompilatora (poziom 4) C4400
ms.date: 11/04/2016
f1_keywords:
- C4400
helpviewer_keywords:
- C4400
ms.assetid: f135fe98-4f92-4e07-9d71-2621b36ee755
ms.openlocfilehash: c91a77758127b5c5b5c5ab742c980f6367830812
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97136243"
---
# <a name="compiler-warning-level-4-c4400"></a>Ostrzeżenie kompilatora (poziom 4) C4400

"Type": kwalifikatory const/volatile dla tego typu nie są obsługiwane

Kwalifikatory [const](../../cpp/const-cpp.md)i [volatile](../../cpp/volatile-cpp.md)nie będą współdziałać ze zmiennymi typów środowiska uruchomieniowego języka wspólnego.

## <a name="example"></a>Przykład

Poniższy przykład generuje C4400.

```cpp
// C4400.cpp
// compile with: /clr /W4
// C4401 expected
using namespace System;
#pragma warning (disable : 4101)
int main() {
   const String^ str;   // C4400
   volatile String^ str2;   // C4400
}
```
