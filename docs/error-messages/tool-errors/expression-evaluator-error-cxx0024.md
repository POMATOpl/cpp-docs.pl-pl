---
description: 'Dowiedz się więcej na temat: błąd ewaluatora wyrażeń CXX0024'
title: Błąd CXX0024 programu Expression Evaluator
ms.date: 11/04/2016
f1_keywords:
- CXX0024
helpviewer_keywords:
- CXX0024
- CAN0024
ms.assetid: eca6adbd-8ff2-4f51-a1cc-a2e9d5d0a47d
ms.openlocfilehash: cb40199c217180b08e62d89dee551130eefefc35
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228082"
---
# <a name="expression-evaluator-error-cxx0024"></a>Błąd CXX0024 programu Expression Evaluator

operacja wymaga wartości l

Wyrażenie, które nie jest szacowane do wartości l, zostało określone dla operacji wymagającej wartości l.

Wartość l-wartości (tak zwana, ponieważ pojawia się po lewej stronie instrukcji przypisania) jest wyrażeniem odwołującym się do lokalizacji pamięci.

Na przykład `buffer[count]` jest prawidłową wartością l, ponieważ wskazuje na określoną lokalizację w pamięci. Porównanie logiczne `zed != 0` nie jest prawidłową wartością l, ponieważ daje w wyniku wartość PRAWDA lub FAŁSZ, a nie na adres pamięci.

Ten błąd jest identyczny z CAN0024.
