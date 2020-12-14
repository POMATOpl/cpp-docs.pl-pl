---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4010'
title: Ostrzeżenie kompilatora (poziom 1) C4010
ms.date: 11/04/2016
f1_keywords:
- C4010
helpviewer_keywords:
- C4010
ms.assetid: d607a9ff-8f8f-45c0-b07b-3b2f439e5485
ms.openlocfilehash: 899e34e0835cce02ab5d11b6c64ae604369f93d9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97241589"
---
# <a name="compiler-warning-level-1-c4010"></a>Ostrzeżenie kompilatora (poziom 1) C4010

Komentarz jednowierszowy zawiera znak kontynuacji wiersza

Jednowierszowy komentarz, który jest wprowadzany przez//, zawiera ukośnik odwrotny ( \\ ), który służy jako znak kontynuacji wiersza. Kompilator traktuje następny wiersz jako kontynuację i traktuje go jako komentarz.

Niektóre redaktory skierowane do składni nie wskazują wiersza następującego po znaku kontynuacji jako komentarza. Ignoruj kolorowanie składni dla wszystkich wierszy, które powodują to ostrzeżenie.

Poniższy przykład generuje C4010:

```cpp
// C4010.cpp
// compile with: /WX
int main() {
   // the next line is also a comment because of the backslash \
   int a = 3; // C4010
   a++;
}
```
