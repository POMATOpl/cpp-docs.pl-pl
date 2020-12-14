---
description: 'Dowiedz się więcej o: błąd kompilatora C2865'
title: Błąd kompilatora C2865
ms.date: 11/04/2016
f1_keywords:
- C2865
helpviewer_keywords:
- C2865
ms.assetid: 973eb6a0-c99a-4d25-b3e5-fe0539794d77
ms.openlocfilehash: 0c57fdb120eb147b3877cc834e142ab92f147aaa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220750"
---
# <a name="compiler-error-c2865"></a>Błąd kompilatora C2865

"Function": niedozwolone porównanie dla handle_or_pointer

Odwołania do [klas i struktur](../../extensions/classes-and-structs-cpp-component-extensions.md) lub typów odwołań zarządzanych można porównać tylko dla równości, aby sprawdzić, czy odwołują się do tego samego obiektu (= =) lub do różnych obiektów (! =).

Nie można porównać ich do uporządkowania, ponieważ środowisko uruchomieniowe platformy .NET może przenosić obiekty zarządzane w dowolnym momencie, zmieniając wyniki testu.
