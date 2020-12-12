---
description: 'Dowiedz się więcej o: błąd kompilatora C3675'
title: Błąd kompilatora C3675
ms.date: 11/04/2016
f1_keywords:
- C3675
helpviewer_keywords:
- C3675
ms.assetid: 87461613-6633-430b-b95d-c7cb1bb63776
ms.openlocfilehash: 0e8ea8d3450cd7a145e596f7122a5d2cbb31c5fd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228745"
---
# <a name="compiler-error-c3675"></a>Błąd kompilatora C3675

"Function": jest zarezerwowana, ponieważ zdefiniowano Właściwość "Property"

Gdy deklarujesz prostą właściwość, kompilator generuje metody dostępu get i Set, a te nazwy są obecne w zakresie programu.  Nazwy wygenerowane przez kompilator są tworzone przez oczekujące get_ i set_ do nazwy właściwości.  W związku z tym nie można zadeklarować funkcji o takiej samej nazwie jak dla metod dostępu generowanych przez kompilator.

Aby uzyskać więcej informacji, zobacz [Właściwość](../../extensions/property-cpp-component-extensions.md) .

## <a name="example"></a>Przykład

Poniższy przykład generuje C3675.

```cpp
// C3675.cpp
// compile with: /clr /c
ref struct C {
public:
   property int Size;
   int get_Size() { return 0; }   // C3675
};
```
