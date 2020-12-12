---
description: 'Dowiedz się więcej o programie: obliczanie wyrażeń (C)'
title: Szacowanie wyrażeń (C)
ms.date: 11/04/2016
helpviewer_keywords:
- expression evaluation
- expressions [C++], evaluating
ms.assetid: 9493f8cc-64a2-4284-9aaf-26eec11c4f40
ms.openlocfilehash: 740cb7a7bc14b598c45b3c8f45e719dcb85372e5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97196454"
---
# <a name="expression-evaluation-c"></a>Szacowanie wyrażeń (C)

Wyrażenia związane z przypisaniem, przyrostem jednoargumentowym, zmniejszeniem jednoargumentowym lub wywołaniem funkcji mogą mieć konsekwencje przypadkowe do oceny (skutki uboczne). Po osiągnięciu "punktu sekwencji" wszystkie elementy poprzedzające punkt sekwencji, w tym wszystkie efekty uboczne, są gwarantowane przed rozpoczęciem oceny, które zaczynają się od punktu sekwencji.

"Skutki uboczne" są zmianami spowodowanymi przez oszacowanie wyrażenia. Efekt uboczny występuje zawsze, gdy wartość zmiennej jest zmieniana przez oszacowanie wyrażenia. Wszystkie operacje przypisania mają efekty uboczne. Wywołania funkcji mogą także mieć skutki uboczne, jeśli zmieniają wartość widocznej zewnętrznie elementu przez przypisanie bezpośrednie lub przez przypisanie pośrednie przez wskaźnik.

## <a name="see-also"></a>Zobacz też

[Operandy i wyrażenia](../c-language/operands-and-expressions.md)
