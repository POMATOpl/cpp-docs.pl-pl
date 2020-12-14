---
description: 'Dowiedz się więcej o: konwersje typów (C)'
title: Konwersje typu (C)
ms.date: 11/04/2016
helpviewer_keywords:
- conversions, type
- type conversion
- converting types
- integral promotions
- type casts, when performed
ms.assetid: d130ee7c-03c3-48f4-af7b-1fdba0d3b086
ms.openlocfilehash: e352a311c586631db08dc1f3e678d4242afdd797
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242863"
---
# <a name="type-conversions-c"></a>Konwersje typu (C)

Konwersje typów zależą od określonego operatora i typu operandu lub operatorów. Konwersje typów są wykonywane w następujących przypadkach:

- Gdy wartość jednego typu jest przypisana do zmiennej innego typu lub operator konwertuje typ operandu lub operandów przed wykonaniem operacji

- Gdy wartość jednego typu jest jawnie rzutowana na inny typ

- Gdy wartość jest przekazana jako argument do funkcji lub gdy typ jest zwracany przez funkcję

Znak, krótka liczba całkowita lub pole bitowe całkowite, wszystkie podpisane lub Nielub obiekt typu wyliczeniowy, może być używane w wyrażeniu wszędzie tam, gdzie można użyć liczby całkowitej. Jeśli **`int`** może reprezentować wszystkie wartości oryginalnego typu, wartość jest konwertowana na **`int`** ; w przeciwnym razie jest konwertowana na **`unsigned int`** . Ten proces jest nazywany "promocją integralną". Wartość zachowywania całkowitych promocji. Oznacza to, że wartość po podwyższeniu poziomu jest taka sama jak przed podwyższeniem poziomu. Aby uzyskać więcej informacji, zobacz [typowe konwersje arytmetyczne](../c-language/usual-arithmetic-conversions.md) .

## <a name="see-also"></a>Zobacz też

[Wyrażenia i przydziały](../c-language/expressions-and-assignments.md)
