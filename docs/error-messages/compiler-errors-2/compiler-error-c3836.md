---
description: 'Dowiedz się więcej o: błąd kompilatora C3836'
title: Błąd kompilatora C3836
ms.date: 11/04/2016
f1_keywords:
- C3836
helpviewer_keywords:
- C3836
ms.assetid: 254f851b-7b7d-4c34-a740-fcf72f6a636a
ms.openlocfilehash: c7e05bbf95facf5b8552b4442138cc38b86703c0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97180880"
---
# <a name="compiler-error-c3836"></a>Błąd kompilatora C3836

Konstruktor statyczny nie może mieć listy inicjatorów składowych

Klasa zarządzana nie może mieć konstruktora statycznego, który ma także listę inicjalizacji składowej. Konstruktory klas statycznych są wywoływane przez środowisko uruchomieniowe języka wspólnego do inicjowania klasy, inicjując statyczne składowe danych.

## <a name="example"></a>Przykład

Poniższy przykład generuje C3836:

```cpp
// C3836a.cpp
// compile with: /clr
ref class M
{
   static int s_i;

public:
   static M() :  s_i(1234)   // C3836, delete initializer to resolve
   {
   }
};

int main()
{
}
```
