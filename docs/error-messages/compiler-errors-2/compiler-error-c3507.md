---
description: 'Dowiedz się więcej o: błąd kompilatora C3507'
title: Błąd kompilatora C3507
ms.date: 11/04/2016
f1_keywords:
- C3507
helpviewer_keywords:
- C3507
ms.assetid: 75f89767-f6f9-40f6-9820-81a49e09abdf
ms.openlocfilehash: d745aab4fec8c7a0bebab6fd4f41b27b7ac5c4df
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113092"
---
# <a name="compiler-error-c3507"></a>Błąd kompilatora C3507

Identyfikator ProgID może zawierać nie więcej niż 39 znaków "ID"; ani nie zawierać żadnych znaków interpunkcyjnych z wyjątkiem "."; ani Rozpocznij od cyfry

Atrybut [ProgID](../../windows/attributes/progid.md) ma ograniczenia dotyczące wartości, które może wykonać.

Poniższy przykład generuje C3507:

```cpp
// C3507.cpp
[module(name="x")];
[
coclass,
progid("0123456789012345678901234567890123456789"),
uuid("00000000-0000-0000-0000-000000000001") // C3507 expected
]
struct CMyStruct {
};
int main() {
}
```
