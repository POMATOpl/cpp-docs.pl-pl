---
description: Dowiedz się więcej o obniżyć liczby całkowite
title: Zwężanie liczb całkowitych
ms.date: 11/04/2016
helpviewer_keywords:
- demoting integers
ms.assetid: 51fb3654-60b0-4de7-80eb-bd910086c18a
ms.openlocfilehash: d80adff34223d8aa785fa6ffa079a54af198a309
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97186821"
---
# <a name="demotion-of-integers"></a>Zwężanie liczb całkowitych

**3.2.1.2 ANSI** Wynik konwersji liczby całkowitej na krótszą cyfrę całkowitą lub wynik konwersji liczby całkowitej bez znaku do podpisanej liczby całkowitej o równej długości, jeśli wartość nie może być reprezentowana

Gdy **`long`** Liczba całkowita jest rzutowana na obiekt **`short`** lub **`short`** jest rzutowana na **`char`** , są zachowywane najmniej znaczące bajty.

Na przykład ten wiersz

```
short x = (short)0x12345678L;
```

przypisuje wartość 0x5678 do `x` , a ten wiersz

```
char y = (char)0x1234;
```

przypisuje wartość 0x34 do `y` .

Gdy **`signed`** zmienne są konwertowane na **`unsigned`** i na odwrót, wzorce bitowe pozostają takie same. Na przykład rzutowanie-2 (0xFE) na **`unsigned`** wartość daje 254 (również 0xFE).

## <a name="see-also"></a>Zobacz też

[Liczby całkowite](../c-language/integers.md)
