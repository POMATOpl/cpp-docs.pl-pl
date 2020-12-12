---
description: 'Dowiedz się więcej o: błąd kompilatora C2732'
title: Błąd kompilatora C2732
ms.date: 11/04/2016
f1_keywords:
- C2732
helpviewer_keywords:
- C2732
ms.assetid: 01b7ad2c-93cf-456f-a4c0-c5f2fdc7c07c
ms.openlocfilehash: 1ca97fbf46685af1df37b8caf82a03effc1ec6bd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123217"
---
# <a name="compiler-error-c2732"></a>Błąd kompilatora C2732

Specyfikacja powiązania jest sprzeczna z wcześniejszą specyfikacją dla elementu "Function"

Funkcja jest już zadeklarowana z innym specyfikatorem powiązania.

Przyczyną tego błędu może być dołączenie plików z różnymi specyfikatorami powiązania.

Aby naprawić ten błąd, należy zmienić **`extern`** instrukcje w taki sposób, aby powiązania były zgodne. W szczególności nie należy zawijać `#include` dyrektyw w `extern "C"` blokach.

## <a name="example"></a>Przykład

Poniższy przykład generuje C2732:

```cpp
// C2732.cpp
extern void func( void );   // implicit C++ linkage
extern "C" void func( void );   // C2732
```
