---
description: 'Dowiedz się więcej na temat: Ostrzeżenie kompilatora C4687'
title: Ostrzeżenie kompilatora C4687
ms.date: 11/04/2016
f1_keywords:
- C4687
helpviewer_keywords:
- C4687
ms.assetid: 2f28e0b1-7358-4c88-bd70-aad8f0aa004c
ms.openlocfilehash: ffa8e645aa82a8577d0cd39a4963b8008b6cf9a3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97180724"
---
# <a name="compiler-warning-c4687"></a>Ostrzeżenie kompilatora C4687

> "*Class*": zapieczętowana Klasa abstrakcyjna nie może implementować interfejsu "*Interface*"

## <a name="remarks"></a>Uwagi

Zapieczętowany, abstrakcyjny typ jest zwykle przydatny tylko do przechowywania statycznych funkcji Członkowskich.

Aby uzyskać więcej informacji, zobacz [abstrakcyjny](../../extensions/abstract-cpp-component-extensions.md) i [zapieczętowany](../../extensions/sealed-cpp-component-extensions.md).

C4687 jest domyślnie wystawiany jako błąd. Możesz pominąć C4687 z pragmą [ostrzeżenia](../../preprocessor/warning.md) . Jeśli masz pewność, że chcesz zaimplementować interfejs w zapieczętowanym, abstrakcyjnym typie, możesz pominąć C4687.

## <a name="example"></a>Przykład

Poniższy przykład generuje C4687.

```cpp
// C4687.cpp
// compile with: /clr /c
interface class A {};

ref struct B sealed abstract : A {};   // C4687
ref struct C sealed : A {};   // OK
ref struct D abstract : A {};   // OK
```
