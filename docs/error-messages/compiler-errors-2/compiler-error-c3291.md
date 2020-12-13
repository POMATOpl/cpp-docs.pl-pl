---
description: 'Dowiedz się więcej o: błąd kompilatora C3291'
title: Błąd kompilatora C3291
ms.date: 11/04/2016
f1_keywords:
- C3291
helpviewer_keywords:
- C3291
ms.assetid: ed2e9f89-8dbc-4387-bc26-cc955e840858
ms.openlocfilehash: 4fcaa080167ae8ef63ffd7b1b180a74e29ac6411
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144745"
---
# <a name="compiler-error-c3291"></a>Błąd kompilatora C3291

"default": nie może być nazwą właściwości prostej

Właściwość prosta nie może mieć nazwy **`default`** . Aby uzyskać więcej informacji, zobacz [Właściwość](../../extensions/property-cpp-component-extensions.md) .

## <a name="example"></a>Przykład

Poniższy przykład generuje C3291.

```cpp
// C3291.cpp
// compile with: /clr /c
ref struct C {
   property System::String ^ default;   // C3291
   property System::String ^ Default;   // OK
};
```
