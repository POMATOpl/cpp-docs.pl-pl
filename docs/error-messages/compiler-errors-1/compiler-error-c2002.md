---
description: 'Dowiedz się więcej o: błąd kompilatora C2002'
title: Błąd kompilatora C2002
ms.date: 11/04/2016
f1_keywords:
- C2002
helpviewer_keywords:
- C2002
ms.assetid: 91982314-203a-4de1-b884-94e39a623f61
ms.openlocfilehash: acf6e0679f2579d25d37ccf0c11965bc1d8b436a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298620"
---
# <a name="compiler-error-c2002"></a>Błąd kompilatora C2002

Nieprawidłowa stała znaku dwubajtowego

Stała znaków wielobajtowych jest nieprawidłowa.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aby rozwiązać ten problem, sprawdzając następujące możliwe przyczyny

1. Stała znaku dwubajtowego zawiera więcej bajtów niż oczekiwano.

1. Nie dołączono standardowego nagłówka STDDEF. h.

1. Znaki dwubajtowe nie mogą być łączone z zwykłymi literałami ciągu.

1. Stała znaku dwubajtowego musi być poprzedzona znakiem "L":

    ```
    L'mbconst'
    ```

1. W przypadku języka Microsoft C++ argumenty tekstowe dyrektywy preprocesora muszą mieć format ASCII. Na przykład dyrektywa `#pragma message(L"string")` nie jest prawidłowa.
