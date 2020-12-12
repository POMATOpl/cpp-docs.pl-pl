---
description: 'Dowiedz się więcej na temat: błąd ewaluatora wyrażeń CXX0019'
title: Błąd CXX0019 programu Expression Evaluator
ms.date: 11/04/2016
f1_keywords:
- CXX0019
helpviewer_keywords:
- CXX0019
- CAN0019
ms.assetid: 4c6431fd-3310-4a61-934d-58b070b330fe
ms.openlocfilehash: 1caf4714c1fc719883ee889c14225e4f69e961a9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228238"
---
# <a name="expression-evaluator-error-cxx0019"></a>Błąd CXX0019 programu Expression Evaluator

nieprawidłowe rzutowanie typu

Ewaluatora wyrażenia języka C nie może wykonać rzutowania typu jako zapisaną.

Ten błąd jest identyczny z CAN0019.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aby rozwiązać ten problem, sprawdzając następujące możliwe przyczyny

1. Określony typ jest nieznany.

1. Wystąpiło zbyt wiele poziomów typu wskaźnika. Na przykład typ rzutowania

    ```
    (char **)h_message
    ```

   nie można obliczyć przy użyciu ewaluatora wyrażeń języka C.
