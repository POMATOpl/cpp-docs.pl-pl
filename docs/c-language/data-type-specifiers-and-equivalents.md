---
title: Specyfikatory typu danych i odpowiedniki
description: Opisuje Specyfikatory typu danych Microsoft Visual C i ich odpowiedniki.
ms.date: 11/04/2016
helpviewer_keywords:
- type specifiers [C++], list
- widening integers
- data types [C++], equivalents
- sign-extending integral types
- zero-extending
- identifiers, data type
- data types [C++], specifiers
- simple types, names
- type names [C++], simple
ms.openlocfilehash: 6a1231bc19617dddf1cc01d4c5e7db2863f1055f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207049"
---
# <a name="data-type-specifiers-and-equivalents"></a>Specyfikatory typu danych i odpowiedniki

Ta dokumentacja zazwyczaj używa formularzy specyfikatorów typu wymienionych w poniższej tabeli, a nie na długich formularzach. Przyjęto również założenie, że **`char`** Typ jest podpisany domyślnie. W tej dokumentacji **`char`** jest równoważne **`signed char`** .

## <a name="type-specifiers-and-equivalents"></a>Specyfikatory typów i równoważne

| Specyfikator typu | Równoważne |
|--|--|
| **`signed char`**<sup>jedno</sup> | **`char`** |
| **`signed int`** | **`signed`**, **`int`** |
| **`signed short int`** | **`short`**, **`signed short`** |
| **`signed long int`** | **`long`**, **`signed long`** |
| **`unsigned char`** | — |
| **`unsigned int`** | **`unsigned`** |
| **`unsigned short int`** | **`unsigned short`** |
| **`unsigned long int`** | **`unsigned long`** |
| **`float`** | — |
| **`long double`**<sup>dwóch</sup> | — |

<sup>1</sup> w przypadku wybrania **`char`** typu bez znaku domyślnie (przez określenie **`/J`** opcji kompilatora) nie można skrócić **`signed char`** **`char`** .

<sup>2</sup> w 32-bitowych i 64-bitowych systemach operacyjnych kompilator języka Microsoft C mapuje **`long double`** do typu **`double`** .

**Specyficzne dla firmy Microsoft**

Możesz określić **`/J`** opcję kompilatora, aby zmienić domyślny **`char`** Typ z **`signed char`** na **`unsigned char`** . Gdy ta opcja jest stosowana, **`char`** oznacza to samo, co **`unsigned char`** , i musisz użyć **`signed`** słowa kluczowego, aby zadeklarować wartość znaku ze znakiem. Jeśli **`char`** wartość jest zadeklarowana jawnie **`signed`** , ta **`/J`** opcja nie ma wpływu na ją, a wartość jest podwyższenie poziomu, gdy zostanie powiększona do **`int`** typu. **`char`** Typ ma wartość zero-Extended, gdy zostanie rozszerzony do **`int`** typu.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Specyfikatory typu C](../c-language/c-type-specifiers.md)
