---
description: 'Dowiedz się więcej o: błąd kompilatora C2396'
title: Błąd kompilatora C2396
ms.date: 11/04/2016
f1_keywords:
- C2396
helpviewer_keywords:
- C2396
ms.assetid: 1b515ef6-7af4-400f-b4ed-564313ea15f6
ms.openlocfilehash: 654b812fbd152a6effb60e6f0919f99bf5039a1b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97145395"
---
# <a name="compiler-error-c2396"></a>Błąd kompilatora C2396

"your_type:: operator'type" ": zdefiniowana przez użytkownika konwersja CLR lub WinRT functionnot prawidłowa. Należy wykonać konwersję z lub przekonwertować do: "t ^", "^%", "^&", gdzie T = "your_type"

Funkcja konwersji w środowisko wykonawcze systemu Windows lub typie zarządzanym nie ma co najmniej jednego parametru, którego typ jest taki sam jak typ zawierający funkcję konwersji.

Poniższy przykład generuje C2396 i pokazuje, jak to naprawić:

```cpp
// C2396.cpp
// compile with: /clr /c

ref struct Y {
   static operator int(char c);   // C2396

   // OK
   static operator int(Y^ hY);
   // or
   static operator Y^(char c);
};
```
