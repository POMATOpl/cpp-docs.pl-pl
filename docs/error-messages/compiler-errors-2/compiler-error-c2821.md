---
description: 'Dowiedz się więcej o: błąd kompilatora C2821'
title: Błąd kompilatora C2821
ms.date: 11/04/2016
f1_keywords:
- C2821
helpviewer_keywords:
- C2821
ms.assetid: e8d71988-a968-4484-94db-e8c3bad74a4a
ms.openlocfilehash: c21c9dc0b1413292e1d73b6448ed008d6fc9a64d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194699"
---
# <a name="compiler-error-c2821"></a>Błąd kompilatora C2821

pierwszy formalny parametr dla "operator new" musi mieć wartość "unsigned int"

Pierwszy formalny parametr [operatora new](../../standard-library/new-operators.md#op_new) musi być typem unsigned **`int`** .

## <a name="example"></a>Przykład

Poniższy przykład generuje C2821:

```cpp
// C2821.cpp
// compile with: /c
void * operator new( /* unsigned int,*/ void * );   // C2821
void * operator new( unsigned int, void * );
```
