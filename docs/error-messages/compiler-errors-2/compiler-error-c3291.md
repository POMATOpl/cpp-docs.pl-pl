---
title: Błąd kompilatora C3291
ms.date: 11/04/2016
f1_keywords:
- C3291
helpviewer_keywords:
- C3291
ms.assetid: ed2e9f89-8dbc-4387-bc26-cc955e840858
ms.openlocfilehash: e3f20d7d7e63079ed9c7a078e9fc9eac06d32677
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/05/2019
ms.locfileid: "58781617"
---
# <a name="compiler-error-c3291"></a>Błąd kompilatora C3291

"default": nie może być nazwą właściwości prostej

Właściwość prosta nie może mieć nazwy `default`. Zobacz [właściwość](../../extensions/property-cpp-component-extensions.md) Aby uzyskać więcej informacji.

## <a name="example"></a>Przykład

Poniższy przykład spowoduje wygenerowanie C3291.

```
// C3291.cpp
// compile with: /clr /c
ref struct C {
   property System::String ^ default;   // C3291
   property System::String ^ Default;   // OK
};
```