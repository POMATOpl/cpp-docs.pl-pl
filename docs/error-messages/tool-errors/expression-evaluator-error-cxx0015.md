---
description: 'Dowiedz się więcej na temat: błąd ewaluatora wyrażeń CXX0015'
title: Błąd CXX0015 programu Expression Evaluator
ms.date: 11/04/2016
f1_keywords:
- CXX0015
helpviewer_keywords:
- CXX0015
- CAN0015
ms.assetid: 35efaf77-d578-48d8-bfc5-fdeb2a46a8b5
ms.openlocfilehash: c5d6e0ba5407646b1e3c835053f1f115dabf4fe7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228329"
---
# <a name="expression-evaluator-error-cxx0015"></a>Błąd CXX0015 programu Expression Evaluator

wyrażenie jest zbyt złożone (przepełnienie stosu)

Wprowadzone wyrażenie jest zbyt złożone lub zagnieżdżone zbyt głęboko dla ilości miejsca do magazynowania dostępnego dla ewaluatora wyrażeń w języku C.

Przepełnienie występuje zwykle z powodu zbyt wielu oczekujących obliczeń.

Przemieść ponownie wyrażenie, aby można było ocenić każdy składnik wyrażenia w miarę jego napotkania, a nie trzeba czekać, aż pozostałe części wyrażenia mają zostać obliczone.

Podziel wyrażenie na wiele poleceń.

Ten błąd jest identyczny z CAN0015.
