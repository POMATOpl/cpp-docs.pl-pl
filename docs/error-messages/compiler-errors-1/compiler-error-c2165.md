---
description: 'Dowiedz się więcej o: błąd kompilatora C2165'
title: Błąd kompilatora C2165
ms.date: 11/04/2016
f1_keywords:
- C2165
helpviewer_keywords:
- C2165
ms.assetid: b108313b-b8cb-4dce-b2ec-f2b31c9cdc87
ms.openlocfilehash: 6c019a1f2fe9edd92d1ebd57b67fd65da262accf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97274635"
---
# <a name="compiler-error-c2165"></a>Błąd kompilatora C2165

"słowo kluczowe": nie można modyfikować wskaźników do danych

**`__stdcall`**, **`__cdecl`** , Lub **`__fastcall`** słowo kluczowe próbuje zmodyfikować wskaźnik do danych.

Poniższy przykład generuje C2165:

```cpp
// C2165.cpp
// compile with: /c
char __cdecl *p;   // C2165
char *p;   // OK
```
