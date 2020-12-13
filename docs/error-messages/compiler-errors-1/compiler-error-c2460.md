---
description: 'Dowiedz się więcej o: błąd kompilatora C2460'
title: Błąd kompilatora C2460
ms.date: 11/04/2016
f1_keywords:
- C2460
helpviewer_keywords:
- C2460
ms.assetid: d969fca9-3ac5-4e4e-88fc-df05510e2093
ms.openlocfilehash: 6a6b521b356d4005906e97b085271369f2624c46
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341857"
---
# <a name="compiler-error-c2460"></a>Błąd kompilatora C2460

"Identifier1": używa "identifier2", który jest definiowany

Klasa lub struktura ( `identifier2` ) jest zadeklarowana jako element członkowski samego siebie ( `identifier1` ). Definicje cykliczne klas i struktur są niedozwolone.

Poniższy przykład generuje C2460:

```cpp
// C2460.cpp
class C {
   C aC;    // C2460
};
```

Zamiast tego należy użyć odwołania do wskaźnika w klasie.

```cpp
// C2460.cpp
class C {
   C * aC;    // OK
};
```
