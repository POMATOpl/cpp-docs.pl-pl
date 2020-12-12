---
description: 'Dowiedz się więcej o: błąd kompilatora C3553'
title: Błąd kompilatora C3553
ms.date: 11/04/2016
f1_keywords:
- C3553
helpviewer_keywords:
- C3553
ms.assetid: 7f84bf37-6419-4ad3-ab30-64266100b930
ms.openlocfilehash: 43e322b78bac05f6e301501a86ce7fbd2f27d285
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223220"
---
# <a name="compiler-error-c3553"></a>Błąd kompilatora C3553

> decltype oczekuje wyrażenia, a nie typu

`decltype()`Słowo kluczowe wymaga wyrażenia jako argumentu, a nie nazwy typu. Na przykład ostatnią instrukcją w poniższym fragmencie kodu jest zwrócenie błędu C3553.

```cpp
int x = 0;
decltype(x+1);
decltype(int); // C3553
```
