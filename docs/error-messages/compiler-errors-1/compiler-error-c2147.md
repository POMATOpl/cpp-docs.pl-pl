---
description: 'Dowiedz się więcej o: błąd kompilatora C2147'
title: Błąd kompilatora C2147
ms.date: 11/04/2016
f1_keywords:
- C2147
helpviewer_keywords:
- C2147
ms.assetid: d1adb3bf-7ece-4815-922c-ad7492fb6670
ms.openlocfilehash: 499b90ddad659a2a36652e783901b25f97eb76f4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97235375"
---
# <a name="compiler-error-c2147"></a>Błąd kompilatora C2147

Błąd składniowy: element "identifier" jest nowym słowem kluczowym

Użyto identyfikatora, który jest teraz zastrzeżonym słowem kluczowym w języku.

Poniższy przykład generuje C2147:

```cpp
// C2147.cpp
// compile with: /clr
int main() {
   int gcnew = 0;   // C2147
   int i = 0;   // OK
}
```
