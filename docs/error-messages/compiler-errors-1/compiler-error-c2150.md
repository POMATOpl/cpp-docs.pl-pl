---
description: 'Dowiedz się więcej o: błąd kompilatora C2150'
title: Błąd kompilatora C2150
ms.date: 11/04/2016
f1_keywords:
- C2150
helpviewer_keywords:
- C2150
ms.assetid: 21e82a10-c1d4-4c0d-9dc6-c5d92ea42a31
ms.openlocfilehash: 5a609edba74e2aee8e0d2a6275fa1ca40fafe5c6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223519"
---
# <a name="compiler-error-c2150"></a>Błąd kompilatora C2150

> "*Identyfikator*": pole bitowe musi mieć typ "int", "ze znakiem int" lub "unsigned int"

Typ podstawowy dla pola bitowego musi mieć wartość **`int`** , **`signed int`** , lub **`unsigned int`** .

## <a name="example"></a>Przykład

Ten przykład pokazuje, jak można napotkać C2150 oraz jak można go naprawić:

```cpp
// C2150.cpp
// compile with: /c
struct A {
   float a : 8;    // C2150
   int i : 8;      // OK
};
```
