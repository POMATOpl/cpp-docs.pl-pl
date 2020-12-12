---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4229'
title: Ostrzeżenie kompilatora (poziom 1) C4229
ms.date: 11/04/2016
f1_keywords:
- C4229
helpviewer_keywords:
- C4229
ms.assetid: aadfc83b-1e5f-4229-bd0a-9c10a5d13182
ms.openlocfilehash: 5c91a3730ff85d71d519c646a1dab64cc08b1003
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97266367"
---
# <a name="compiler-warning-level-1-c4229"></a>Ostrzeżenie kompilatora (poziom 1) C4229

anachronizm: Modyfikatory dla danych są ignorowane

Używanie modyfikatora Microsoft, takiego jak **`__cdecl`** na deklaracji danych, jest nieaktualnym postępowaniem.

## <a name="example"></a>Przykład

```cpp
// C4229.cpp
// compile with: /W1 /LD
int __cdecl counter;   // C4229 cdecl ignored
```
