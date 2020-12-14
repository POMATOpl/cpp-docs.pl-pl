---
description: 'Dowiedz się więcej o: błąd kompilatora C3141'
title: Błąd kompilatora C3141
ms.date: 11/04/2016
f1_keywords:
- C3141
helpviewer_keywords:
- C3141
ms.assetid: b4fd65c3-50cc-46cd-8de0-6a6d24cb9cda
ms.openlocfilehash: bc5ebc1376d17cead4697987e35b4733e8ab0a22
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97304210"
---
# <a name="compiler-error-c3141"></a>Błąd kompilatora C3141

"interface_name": interfejsy obsługują tylko publiczne dziedziczenie

Interfejsy zdefiniowane za pomocą słowa kluczowego [Interface (lub __interface)](../../cpp/interface.md) obsługują tylko publiczne dziedziczenie.

Poniższy przykład generuje C3141:

```cpp
// C3141.cpp
__interface IBase {};
__interface IDerived1 : protected IBase {};  // C3141
__interface IDerived2 : private IBase {};    // C3141
```
