---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 4) C4032'
title: Ostrzeżenie kompilatora (poziom 4) C4032
ms.date: 11/04/2016
f1_keywords:
- C4032
helpviewer_keywords:
- C4032
ms.assetid: 70dd0c85-0239-43f9-bb06-507f6a57d206
ms.openlocfilehash: 1c150bff398bbd2d6e5f1a8d21211f4c6b4cb6bd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262103"
---
# <a name="compiler-warning-level-4-c4032"></a>Ostrzeżenie kompilatora (poziom 4) C4032

formalny parametr "number" ma inny typ podczas podwyższania poziomu

Typ parametru jest niezgodny, za pomocą domyślnej promocji, z typem w poprzedniej deklaracji.

Jest to błąd w języku ANSI C ([/za](../../build/reference/za-ze-disable-language-extensions.md)) i ostrzeżenie w ramach rozszerzeń Microsoft (/ze).

## <a name="example"></a>Przykład

```c
// C4032.c
// compile with: /W4
void func();
void func(char);   // C4032, char promotes to int

int main()
{
}
```
