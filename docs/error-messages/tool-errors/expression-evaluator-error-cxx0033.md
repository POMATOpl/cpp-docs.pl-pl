---
description: 'Dowiedz się więcej na temat: błąd ewaluatora wyrażeń CXX0033'
title: Błąd CXX0033 programu Expression Evaluator
ms.date: 11/04/2016
f1_keywords:
- CXX0033
helpviewer_keywords:
- CAN0033
- CXX0033
ms.assetid: 0bd62c5b-de89-481f-9b12-88fe84805afe
ms.openlocfilehash: 714499d8d1bc0812395576fe27be690997982065
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97160327"
---
# <a name="expression-evaluator-error-cxx0033"></a>Błąd CXX0033 programu Expression Evaluator

błąd w informacjach o typie OMF

Plik wykonywalny nie ma prawidłowego formatu modułu obiektów (OMF) na potrzeby debugowania.

Ten błąd jest identyczny z CAN0033.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aby rozwiązać ten problem, sprawdzając następujące możliwe przyczyny

1. Plik wykonywalny nie został utworzony za pomocą konsolidatora wydanego w tej wersji programu Visual C++. Ponownie połącz kod obiektu przy użyciu bieżącej wersji LINK.exe.

1. Plik. exe mógł zostać uszkodzony. Ponownie skompiluj i ponownie połącz program.
