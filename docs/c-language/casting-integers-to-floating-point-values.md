---
description: 'Dowiedz się więcej: Rzutowanie liczb całkowitych na wartości Floating-Point'
title: Rzutowanie liczb całkowitych na wartości zmiennoprzecinkowe
ms.date: 11/04/2016
helpviewer_keywords:
- integers, casting to floating-point values
ms.assetid: 81fd5b7d-15eb-4c11-a8c8-e1621ff54fd3
ms.openlocfilehash: 2a1a3ce5bf7aac98148c70eb62cdb3c377ca54f3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97214021"
---
# <a name="casting-integers-to-floating-point-values"></a>Rzutowanie liczb całkowitych na wartości zmiennoprzecinkowe

**3.2.1.3 ANSI** Kierunek obcinania, gdy numer całkowity jest konwertowany na liczbę zmiennoprzecinkową, która nie może dokładnie reprezentować pierwotnej wartości

Gdy całkowita liczba jest rzutowana na wartość zmiennoprzecinkową, która nie może dokładnie reprezentować wartości, wartość jest zaokrąglana (w górę lub w dół) do najbliższej odpowiedniej wartości.

Na przykład rzutowanie **`unsigned long`** (o 32 bitów precyzji) do **`float`** (którego mantysy ma 23 bitów precyzji) zaokrągla liczbę do najbliższej wielokrotności 256. **`long`** Wartości od 4 294 966 913 do 4 294 967 167 są zaokrąglane do **`float`** wartości 4 294 967 040.

## <a name="see-also"></a>Zobacz też

[Obliczenia matematyczne zmiennoprzecinkowe](../c-language/floating-point-math.md)
