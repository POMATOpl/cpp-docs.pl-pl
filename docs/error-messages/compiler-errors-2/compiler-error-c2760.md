---
description: 'Dowiedz się więcej o: błąd kompilatora C2760'
title: Błąd kompilatora C2760
ms.date: 11/04/2016
f1_keywords:
- C2760
helpviewer_keywords:
- C2760
ms.assetid: 585757fd-d519-43f3-94e5-50316ac8b90b
ms.openlocfilehash: bba26b68a2e4c98cf478098b2e44e82962afd9f0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336162"
---
# <a name="compiler-error-c2760"></a>Błąd kompilatora C2760

> Błąd składniowy: oczekiwano "*Name1*", a nie "*NAME2*"

## <a name="remarks"></a>Uwagi

Istnieje kilka sposobów na wystąpienie tego błędu. Zwykle jest to spowodowane przez sekwencję tokenów, która nie może być zrozumiała dla kompilatora.

## <a name="example"></a>Przykład

W tym przykładzie operator rzutowania jest używany z nieprawidłowym operatorem.

```cpp
// C2760.cpp
class B {};
class D : public B {};

void f(B* pb) {
    D* pd1 = static_cast<D*>(pb);
    D* pd2 = static_cast<D*>=(pb);  // C2760
    D* pd3 = static_cast<D*=(pb);   // C2760
}
```
