---
description: 'Dowiedz się więcej o: błąd kompilatora C3453'
title: Błąd kompilatora C3453
ms.date: 11/04/2016
f1_keywords:
- C3453
helpviewer_keywords:
- C3453
ms.assetid: dbefdbcf-f697-4239-b7a5-1d99b85e9e7f
ms.openlocfilehash: 2ff1c246dc66d60266f0fc44e134db3ab21605df
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315975"
---
# <a name="compiler-error-c3453"></a>Błąd kompilatora C3453

"Attribute": atrybut nie został zastosowany, ponieważ kwalifikator "Assembly" nie jest zgodny

Atrybuty na poziomie zestawu lub modułu można określać tylko jako instrukcje autonomiczne.

## <a name="example"></a>Przykład

Poniższy przykład generuje C3453.

```cpp
// C3453.cpp
// compile with: /clr /c
[assembly:System::CLSCompliant(true)]   // C3453
// try the following line instead
// [assembly:System::CLSCompliant(true)];
ref class X {};
```
