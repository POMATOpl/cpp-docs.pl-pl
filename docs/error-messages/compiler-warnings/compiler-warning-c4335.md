---
description: 'Dowiedz się więcej na temat: Ostrzeżenie kompilatora C4335'
title: Ostrzeżenie kompilatora C4335
ms.date: 11/04/2016
f1_keywords:
- C4335
helpviewer_keywords:
- C4335
ms.assetid: e66467ad-a10b-4438-8c7c-e8e8d11d39bb
ms.openlocfilehash: fc8f86036a299c41bc0cb1814b98372edc3b4d8f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97238313"
---
# <a name="compiler-warning-c4335"></a>Ostrzeżenie kompilatora C4335

Wykryto format pliku Mac: Skonwertuj plik źródłowy do formatu DOS lub UNIX

Znak zakończenia wiersza pierwszego wiersza pliku źródłowego to Macintosh Style ("\r") w przeciwieństwie do systemu UNIX ("\n") lub DOS ("\r\n").

To ostrzeżenie jest zawsze emitowane jako błąd.  Aby uzyskać informacje na temat sposobu wyłączania tego ostrzeżenia, zobacz pragma [ostrzeżenia](../../preprocessor/warning.md) .  To ostrzeżenie jest również wydawane tylko raz na jednostka kompilacji. W związku z tym, jeśli istnieje wiele `#include` dyrektyw, które określają pliki w formacie Macintosh, C4335 zostanie wystawiony tylko raz.

Jednym ze sposobów generowania plików w formacie komputerów Macintosh jest użycie **zaawansowanych opcji zapisywania** (w menu **plik** ) w programie Visual Studio.

## <a name="example"></a>Przykład

Poniższy przykład generuje C4335.

```cpp
// C4335 expected
#include "c4335.h"   // assume both include files are in Macintosh format
#include "c4335_2.h"
```
