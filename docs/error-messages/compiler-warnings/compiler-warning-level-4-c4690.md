---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 4) C4690'
title: Ostrzeżenie kompilatora (poziom 4) C4690
ms.date: 07/03/2018
f1_keywords:
- C4690
helpviewer_keywords:
- C4690
ms.assetid: 080a0ea1-458b-477b-a37a-4a34c94709ff
ms.openlocfilehash: 1f6d3ee3f6ba20207a355350edda99861d10b5f8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97133850"
---
# <a name="compiler-warning-level-4-c4690"></a>Ostrzeżenie kompilatora (poziom 4) C4690

> \[ emitidl (pop)]: więcej punktów obecności niż wypychanie

## <a name="remarks"></a>Uwagi

Atrybut [emitidl](../../windows/attributes/emitidl.md) został zdjęte jeszcze raz na wypchnięcie.

## <a name="example"></a>Przykład

Poniższy przykład generuje C4690. Aby rozwiązać ten problem, upewnij się, że atrybut jest zdjęte dokładnie tyle razy, ile jest wypchnięci.

```cpp
// C4690.cpp
// compile with: /c /W4
[emitidl(pop)];   // C4690
class x {};
```
