---
description: 'Dowiedz się więcej o: błąd kompilatora C3354'
title: Błąd kompilatora C3354
ms.date: 11/04/2016
f1_keywords:
- C3354
helpviewer_keywords:
- C3354
ms.assetid: 185de401-231e-4999-a149-172ee4c69d84
ms.openlocfilehash: cb2c110471b95010e56677608725e5d6abeaa5e7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245320"
---
# <a name="compiler-error-c3354"></a>Błąd kompilatora C3354

"Function": funkcja użyta do utworzenia delegata nie może mieć zwracanego typu "Type"

Następujące typy są nieprawidłowe jako typy zwracane dla **`delegate`** :

- Wskaźnik do funkcji

- Wskaźnik do elementu członkowskiego

- Wskaźnik do funkcji składowej

- Odwołanie do funkcji

- Odwołanie do funkcji członkowskiej

Poniższy przykład generuje C3354:

```cpp
// C3354_2.cpp
// compile with: /clr /c
using namespace System;
typedef void ( *VoidPfn )();

delegate VoidPfn func(); // C3354
// try the following line instead
// delegate  void func();
```
