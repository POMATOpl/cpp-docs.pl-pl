---
description: 'Dowiedz się więcej na temat: błąd ewaluatora wyrażeń CXX0036'
title: Błąd CXX0036 programu Expression Evaluator
ms.date: 11/04/2016
f1_keywords:
- CXX0036
helpviewer_keywords:
- CXX0036
- CAN0036
ms.assetid: 383404be-df5b-4eec-b113-df21bb5d269d
ms.openlocfilehash: fa595c590b6e59b74d693f3b6ff777055b5af2c1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338534"
---
# <a name="expression-evaluator-error-cxx0036"></a>Błąd CXX0036 programu Expression Evaluator

zły kontekst {...} specyfikacja

Ten komunikat może być generowany przez dowolny z kilku błędów podczas korzystania z operatora kontekstu ( **{}** ).

- Nieprawidłowa składnia operatora kontekstu ( **{}** ).

   Składnia operatora kontekstu to:

     {*Function*,*module*,*dll*} *wyrażenie*

   Określa kontekst *wyrażenia*. Operator kontekstu ma takie samo pierwszeństwo i użycie jak rzutowanie typu.

   Końcowe przecinki można pominąć. Jeśli którakolwiek z *funkcji*, *modułów* lub *dll* zawiera przecinek literału, należy ująć całą nazwę w nawiasy.

- Nazwa funkcji została wpisana niepoprawnie lub nie istnieje w określonym module lub bibliotece dołączanej dynamicznie.

   Ponieważ język C jest rozróżniana wielkość liter, *Funkcja* musi być określona w dokładnie takim przypadku, jak jest zdefiniowana w źródle.

- Nie można znaleźć modułu lub biblioteki DLL.

   Sprawdź pełną nazwę ścieżki określonego modułu lub biblioteki DLL.

Ten błąd jest identyczny z CAN0036.
