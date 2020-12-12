---
description: 'Dowiedz się więcej na temat: błąd ewaluatora wyrażeń CXX0065'
title: Błąd CXX0065 programu Expression Evaluator
ms.date: 11/04/2016
f1_keywords:
- CXX0065
helpviewer_keywords:
- CAN0065
- CXX0065
ms.assetid: aac68f87-0b90-4c19-afa6-1c587625a5fd
ms.openlocfilehash: 8013bdc2541e2ab3719ef700413a87df49731983
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97173171"
---
# <a name="expression-evaluator-error-cxx0065"></a>Błąd CXX0065 programu Expression Evaluator

Zmienna wymaga ramki stosu

Wyrażenie zawiera zmienną, która istnieje w bieżącym zakresie, ale nie została jeszcze utworzona.

Ten błąd może wystąpić, gdy nastąpiło przeprowadzenie prologu funkcji, ale nie skonfigurowano jeszcze ramki stosu dla funkcji lub jeśli nastąpiło przeprowadzenie kodu zakończenia dla funkcji.

Przechodzenie przez kod prologu do momentu skonfigurowania ramki stosu przed rozpoczęciem oceny wyrażenia.

Ten błąd jest identyczny z CAN0065.
