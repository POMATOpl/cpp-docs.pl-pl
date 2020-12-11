---
description: 'Dowiedz się więcej o: błąd kompilatora C2720'
title: Błąd kompilatora C2720
ms.date: 11/04/2016
f1_keywords:
- C2720
helpviewer_keywords:
- C2720
ms.assetid: 9ee3aab7-711b-4f5a-b2f1-cb62b130f1ce
ms.openlocfilehash: 187142af02289374235725340a206f35b6a42493
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97155660"
---
# <a name="compiler-error-c2720"></a>Błąd kompilatora C2720

> "*Identyfikator*": specyfikator klasy magazynu "*specyfikator*" jest niedozwolony w składowych

Klasy Storage nie można używać w składowych klasy poza deklaracją. Aby naprawić ten błąd, Usuń niepotrzebny specyfikator [klasy magazynu](../../cpp/storage-classes-cpp.md) z definicji elementu członkowskiego spoza deklaracji klasy.

## <a name="example"></a>Przykład

Poniższy przykład generuje C2720 i pokazuje, jak to naprawić:

```cpp
// C2720.cpp
struct S {
   static int i;
};
static S::i;   // C2720 - remove the unneeded 'static' to fix it
```
