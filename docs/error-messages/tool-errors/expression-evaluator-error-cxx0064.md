---
description: 'Dowiedz się więcej na temat: błąd ewaluatora wyrażeń CXX0064'
title: Błąd CXX0064 programu Expression Evaluator
ms.date: 11/04/2016
f1_keywords:
- CXX0064
helpviewer_keywords:
- CAN0064
- CXX0064
ms.assetid: aa509e71-0616-41ca-a94e-6c376b041e57
ms.openlocfilehash: 58356a48fc52ee479c92cf5d65494763c3fc4adb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97173197"
---
# <a name="expression-evaluator-error-cxx0064"></a>Błąd CXX0064 programu Expression Evaluator

nie można ustawić punktu przerwania dla powiązanej wirtualnej funkcji członkowskiej

Punkt przerwania został ustawiony dla wirtualnej funkcji składowej za pomocą wskaźnika do obiektu, takiego jak:

```
pClass->vfunc( int );
```

Punkt przerwania można ustawić dla funkcji wirtualnej, wprowadzając klasę, taką jak:

```
Class::vfunc( int );
```

Ten błąd jest identyczny z CAN0064.
