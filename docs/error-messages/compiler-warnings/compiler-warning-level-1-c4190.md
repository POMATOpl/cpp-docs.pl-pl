---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4190'
title: Ostrzeżenie kompilatora (poziom 1) C4190
ms.date: 11/04/2016
f1_keywords:
- C4190
helpviewer_keywords:
- C4190
ms.assetid: a4d0ad93-a19a-4063-addd-36d605831567
ms.openlocfilehash: ff27d5913e23fa1488816b3e2bb7284440c7577b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97266588"
---
# <a name="compiler-warning-level-1-c4190"></a>Ostrzeżenie kompilatora (poziom 1) C4190

"Identifier1" ma określone powiązanie C, ale zwraca UDT "identifier2", które jest niezgodne z C

Funkcja lub wskaźnik do funkcji ma typ UDT (zdefiniowany przez użytkownika, który jest klasą, strukturą, wyliczeniem lub Unią) jako zwracany typ i `extern "C"` powiązania. Jest to dozwolone, jeśli:

- Wszystkie wywołania tej funkcji występują w języku C++.

- Definicja funkcji jest w języku C++.

## <a name="example"></a>Przykład

```cpp
// C4190.cpp
// compile with: /W1 /LD
struct X
{
   int i;
   X ();
   virtual ~X ();
};

extern "C" X func ();   // C4190
```
