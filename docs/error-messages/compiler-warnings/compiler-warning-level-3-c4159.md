---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 3) C4159'
title: Ostrzeżenie kompilatora (poziom 3) C4159
ms.date: 11/04/2016
f1_keywords:
- C4159
helpviewer_keywords:
- C4159
ms.assetid: e2cf964e-f4b8-4b2c-9569-1abb94307232
ms.openlocfilehash: 153bd7ee7bc634ab10e0e6eb872a8f055e6470e9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326466"
---
# <a name="compiler-warning-level-3-c4159"></a>Ostrzeżenie kompilatora (poziom 3) C4159

> #<a name="pragma-pragmapop--has-popped-previously-pushed-identifier-identifier"></a>pragma pragma (pop,...): ma zdjęte poprzednio wypychany identyfikator "*Identifier*"

## <a name="remarks"></a>Uwagi

Kod źródłowy zawiera instrukcję **push** z identyfikatorem dyrektywy pragma, po której następuje instrukcja **pop** bez identyfikatora. W związku z tym *Identyfikator* to zdjęte, a kolejne zastosowania *identyfikatora* mogą spowodować nieoczekiwane zachowanie.

## <a name="example"></a>Przykład

Aby uniknąć tego ostrzeżenia, należy podać identyfikator w instrukcji **pop** . Na przykład:

```cpp
// C4159.cpp
// compile with: /W3
#pragma pack(push, f)
#pragma pack(pop)   // C4159

// using the identifier resolves the warning
// #pragma pack(pop, f)

int main()
{
}
```
