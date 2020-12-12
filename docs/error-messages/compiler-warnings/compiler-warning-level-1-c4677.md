---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4677'
title: Ostrzeżenie kompilatora (poziom 1) C4677
ms.date: 11/04/2016
f1_keywords:
- C4677
helpviewer_keywords:
- C4677
ms.assetid: a8d656a1-e2ff-4f8b-9028-201765131026
ms.openlocfilehash: e2edd37149fd4242cc1a0f5c5df29fe4fe21e17f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97285425"
---
# <a name="compiler-warning-level-1-c4677"></a>Ostrzeżenie kompilatora (poziom 1) C4677

"Function": Sygnatura nieprywatnej składowej zawiera prywatny Typ zestawu "private_type"

Typ z publiczną dostępnością poza zestawem korzysta z typu, który ma prywatny dostęp poza zestawem. Składnik, który odwołuje się do typu zestawu publicznego, nie będzie mógł używać składowej typu lub składowych odwołujących się do typu prywatnego zestawu.

## <a name="example"></a>Przykład

Poniższy przykład generuje C4677.

```cpp
// C4677.cpp
// compile with: /clr /c /W1
delegate void TestDel();
public delegate void TestDel2();

public ref class MyClass {
public:
   static event TestDel^ MyClass_Event;   // C4677
   static event TestDel2^ MyClass_Event2;   // OK
};
```
