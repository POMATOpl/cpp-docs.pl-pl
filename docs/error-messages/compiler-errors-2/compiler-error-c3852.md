---
description: 'Dowiedz się więcej o: błąd kompilatora C3852'
title: Błąd kompilatora C3852
ms.date: 11/04/2016
f1_keywords:
- C3852
helpviewer_keywords:
- C3852
ms.assetid: 194e5c5e-0dfb-414e-86db-791c11eb610c
ms.openlocfilehash: f5bfeb5507943dc4f860b81912bfb6880621f290
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97255239"
---
# <a name="compiler-error-c3852"></a>Błąd kompilatora C3852

Typ "member" typu ": inicjalizacja agregująca nie może zainicjować tego elementu członkowskiego

Podjęto próbę przypisania domyślnej inicjalizacji w ramach inicjalizacji agregacji do elementu członkowskiego danych, który nie może odebrać domyślnej inicjalizacji w ramach inicjalizacji agregacji.

Następujące przykłady generują C3852:

```cpp
// C3852.cpp
struct S
{
   short s;
};

struct S1
{
   int i;
   const S s;
};

struct S2
{
   int i;
   char & rc;
};

int main()
{
   S1 s1 = { 1 };   // C3852 const member
   // try the following line instead
   // S1 s1 = { 1, 2 };

   S2 s2 = { 2 };   // C3852 reference member
   // try the following line instead
   // char c = 'a';
   S2 s2 = { 2, c };
}
```
