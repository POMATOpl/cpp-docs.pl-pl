---
description: 'Dowiedz się więcej o programie: konwersje Function-Call'
title: Konwersje wywołania funkcji
ms.date: 11/04/2016
helpviewer_keywords:
- function calls, converting
- function calls, argument type conversions
- functions [C], argument conversions
ms.assetid: 04ea0f81-509a-4913-8b12-0937a81babcf
ms.openlocfilehash: f37cf2ef6c35cb8e7c856e1ab722a1efda2da61d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195960"
---
# <a name="function-call-conversions"></a>Konwersje wywołania funkcji

Typ konwersji wykonywanej na argumentach wywołania funkcji zależy od obecności prototypu funkcji (deklaracji do przodu) z zadeklarowanymi typami argumentów dla wywołanej funkcji.

Jeśli prototyp funkcji jest obecny i zawiera zadeklarowane typy argumentów, kompilator wykonuje sprawdzanie typu (zobacz [funkcje](../c-language/functions-c.md)).

Jeśli nie ma prototypu funkcji, tylko standardowe konwersje arytmetyczne są wykonywane na argumentach wywołania funkcji. Te konwersje są wykonywane niezależnie od każdego argumentu w wywołaniu. Oznacza to, że **`float`** wartość jest konwertowana na **`double`** ; a **`char`** lub **`short`** wartość jest konwertowana na **`int`** ; i **`unsigned char`** lub **`unsigned short`** jest konwertowana na **`unsigned int`** .

## <a name="see-also"></a>Zobacz też

[Konwersje typu](../c-language/type-conversions-c.md)
