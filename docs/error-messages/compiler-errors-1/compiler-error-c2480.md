---
description: 'Dowiedz się więcej o: błąd kompilatora C2480'
title: Błąd kompilatora C2480
ms.date: 11/04/2016
f1_keywords:
- C2480
helpviewer_keywords:
- C2480
ms.assetid: 1a58d1c2-971b-4084-96fa-f94aa51c02f1
ms.openlocfilehash: 0c7f73b7e1aa205d38577602b93907309935b216
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316547"
---
# <a name="compiler-error-c2480"></a>Błąd kompilatora C2480

"Identyfikator": "Thread" jest tylko prawidłowy dla elementów danych statycznego zakresu

Nie można użyć `thread` atrybutu z automatyczną zmienną, niestatyczną składową danych, parametrem funkcji ani deklaracjami lub definicjami funkcji.

Użyj `thread` atrybutu dla zmiennych globalnych, statycznych elementów członkowskich danych i lokalnych zmiennych statycznych.

Poniższy przykład generuje C2480:

```cpp
// C2480.cpp
// compile with: /c
__declspec( thread ) void func();   // C2480
__declspec( thread ) static int i;   // OK
```
