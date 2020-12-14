---
description: 'Dowiedz się więcej o: błąd kompilatora C2011'
title: Błąd kompilatora C2011
ms.date: 11/04/2016
f1_keywords:
- C2011
helpviewer_keywords:
- C2011
ms.assetid: 992c9d51-e850-4d53-b86b-02e73b38249c
ms.openlocfilehash: c310495c570a2259cf5abe6acea951ca996bfb26
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97221023"
---
# <a name="compiler-error-c2011"></a>Błąd kompilatora C2011

"Identyfikator": typ "typ" — Definicja

Identyfikator został już zdefiniowany jako `type` . Sprawdź definicje ponownych identyfikatorów.

Możesz również uzyskać C2011 w przypadku zaimportowania pliku nagłówkowego lub biblioteki typów więcej niż raz do tego samego pliku. Aby uniemożliwić wielokrotne dołączanie typów zdefiniowanych w pliku nagłówkowym, należy użyć dyrektywy include Guard lub `#pragma` [raz](../../preprocessor/once.md) w pliku nagłówkowym.

Jeśli konieczne jest znalezienie początkowej deklaracji typu, można użyć flagi [/p](../../build/reference/p-preprocess-to-a-file.md) kompilatora, aby wygenerować wstępnie przetworzone dane wyjściowe przekazywane do kompilatora. Możesz użyć narzędzi wyszukiwania tekstu, aby znaleźć wystąpienia ponownie zdefiniowanego identyfikatora w pliku wyjściowym.

Poniższy przykład generuje C2011 i pokazuje jeden ze sposobów rozwiązania tego problemu:

```cpp
// C2011.cpp
// compile with: /c
struct S;
union S;   // C2011
union S2;   // OK
```
