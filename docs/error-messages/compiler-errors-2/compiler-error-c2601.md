---
description: 'Dowiedz się więcej o: błąd kompilatora C2601'
title: Błąd kompilatora C2601
ms.date: 11/04/2016
f1_keywords:
- C2601
helpviewer_keywords:
- C2601
ms.assetid: 88275582-5f37-45d7-807d-05f06ba00965
ms.openlocfilehash: 373ba519633034ddf63889eb82cd71dccfa4a743
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97119999"
---
# <a name="compiler-error-c2601"></a>Błąd kompilatora C2601

"Function": definicje funkcji lokalnych są niedozwolone

Kod próbuje zdefiniować funkcję w ramach funkcji.

Lub w kodzie źródłowym może być dodatkowy nawias klamrowy przed lokalizacją błędu C2601.

Poniższy przykład generuje C2601:

```cpp
// C2601.cpp
int main() {
   int i = 0;

   void funcname(int j) {   // C2601
      j++;
   }
}
```
