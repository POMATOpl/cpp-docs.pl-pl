---
description: 'Dowiedz się więcej o: błąd kompilatora C2991'
title: Błąd kompilatora C2991
ms.date: 11/04/2016
f1_keywords:
- C2991
helpviewer_keywords:
- C2991
ms.assetid: a87e4404-26e8-4927-b3ee-5d02b3b8bee1
ms.openlocfilehash: 9f42d96a15869b656abfff21a921ec340aa6ce1f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338592"
---
# <a name="compiler-error-c2991"></a>Błąd kompilatora C2991

Ponowna definicja parametru typu "parameter"

Wystąpił konflikt typu między dwiema ogólnymi lub definicjami szablonu `parameter` . Podczas definiowania wielu parametrów ogólnych lub szablonów należy użyć równoważnych typów.

Poniższy przykład generuje C2991:

```cpp
// C2991.cpp
// compile with: /c
template<class T, class T> struct TC {};   // C2991
// try the following line instead
// template<class T, class T2> struct TC {};
```

C2991 może również wystąpić przy użyciu typów ogólnych:

```cpp
// C2991b.cpp
// compile with: /clr /c
generic<class T,class T> ref struct GC {};   // C2991
// try the following line instead
// generic<class T,class T2> ref struct GC {};
```
