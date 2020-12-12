---
description: 'Dowiedz się więcej o: błąd kompilatora C3625'
title: Błąd kompilatora C3625
ms.date: 11/04/2016
f1_keywords:
- C3625
helpviewer_keywords:
- C3625
ms.assetid: fdf49f21-d6b1-42f4-9eec-23b04ae8b4aa
ms.openlocfilehash: ee28175eac35e05ca2a4620dffa84cf995e053a7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144498"
---
# <a name="compiler-error-c3625"></a>Błąd kompilatora C3625

"native_type": typ natywny nie może pochodzić od typu zarządzanego lub WinRT "Type"

Klasa macierzysta nie może dziedziczyć z klasy zarządzanej ani WinRT. Aby uzyskać więcej informacji, zobacz [klasy i struktury](../../extensions/classes-and-structs-cpp-component-extensions.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje C3625:

```cpp
// C3625.cpp
// compile with: /clr /c
ref class B {};
class D : public B {};   // C3625 cannot inherit from a managed class
```
