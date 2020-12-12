---
description: 'Dowiedz się więcej o: błąd kompilatora C2838'
title: Błąd kompilatora C2838
ms.date: 11/04/2016
f1_keywords:
- C2838
helpviewer_keywords:
- C2838
ms.assetid: 176b2ad6-7a84-4019-b97e-328866054457
ms.openlocfilehash: 70bc1fa038df33cfe63fccd7dc3db8983950b525
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194400"
---
# <a name="compiler-error-c2838"></a>Błąd kompilatora C2838

"member": niedozwolona kwalifikowana nazwa w deklaracji składowej

Klasa, struktura lub Unia używa w pełni kwalifikowanej nazwy, aby ponownie zadeklarować element członkowski innej klasy, struktury lub Unii.

Poniższy przykład generuje C2838:

```cpp
// C2838.cpp
// compile with: /c
class Bellini {
public:
    void Norma();
};

class Bottesini {
   Bellini::Norma();  // C2838
};
```
