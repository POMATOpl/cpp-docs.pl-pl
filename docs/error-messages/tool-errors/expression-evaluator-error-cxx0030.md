---
description: 'Dowiedz się więcej na temat: błąd ewaluatora wyrażeń CXX0030'
title: Błąd CXX0030 programu Expression Evaluator
ms.date: 11/04/2016
f1_keywords:
- CXX0030
helpviewer_keywords:
- CAN0030
- CXX0030
ms.assetid: ada8b48c-09c8-49bf-ae23-313ed663c4fe
ms.openlocfilehash: d9679d260ce81c2cb9bb8be4c082ffe8c1cfc6a9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97237430"
---
# <a name="expression-evaluator-error-cxx0030"></a>Błąd CXX0030 programu Expression Evaluator

wyrażenie nie jest do oceny

Ewaluatora wyrażeń w debugerze nie może uzyskać wartości dla wyrażenia jako zapisania. Jedną z możliwych przyczyn jest to, że wyrażenie odwołuje się do pamięci, która znajduje się poza przestrzenią adresową programu (na przykład można wycofać wskaźnik o wartości null). System Windows nie zezwala na dostęp do pamięci spoza przestrzeni adresowej programu.

Możesz chcieć ponownie napisać wyrażenie przy użyciu nawiasów, aby kontrolować kolejność obliczeń.

Ten błąd jest identyczny z CAN0030.
