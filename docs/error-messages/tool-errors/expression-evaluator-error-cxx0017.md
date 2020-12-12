---
description: 'Dowiedz się więcej na temat: błąd ewaluatora wyrażeń CXX0017'
title: Błąd CXX0017 programu Expression Evaluator
ms.date: 11/04/2016
f1_keywords:
- CXX0017
helpviewer_keywords:
- CAN0017
- CXX0017
ms.assetid: af74db02-a64d-49ca-8363-3e044a107580
ms.openlocfilehash: 0abb99422383f95e13d4137a5ad899730d485f87
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228277"
---
# <a name="expression-evaluator-error-cxx0017"></a>Błąd CXX0017 programu Expression Evaluator

nie znaleziono symbolu

Nie można znaleźć symbolu określonego w wyrażeniu.

Jedną z możliwych przyczyn tego błędu jest niezgodność wielkości liter w nazwie symbolu. Ponieważ w językach C i C++ jest rozróżniana wielkość liter, nazwa symbolu musi być określona w dokładnie takim przypadku, w którym jest zdefiniowana w źródle.

Ten błąd może wystąpić podczas próby rzutowanie zmiennej w celu obejrzenia zmiennej podczas debugowania. `typedef`Deklaruje nową nazwę dla typu, ale nie definiuje nowego typu. Rzutowaniea próba w debugerze wymaga nazwy zdefiniowanego typu.

Ten błąd jest identyczny z CAN0017.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aby rozwiązać ten problem, można użyć następujących rozwiązań

1. Upewnij się, że symbol jest już zadeklarowany w punkcie w programie, w którym jest używany.

1. Użyj rzeczywistej nazwy typu do rzutowania zmiennych w debugerze, a nie `typedef` zdefiniowanej nazwy.
