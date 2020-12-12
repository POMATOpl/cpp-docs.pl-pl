---
description: 'Dowiedz się więcej o: funkcjach wbudowanych'
title: Funkcje śródwierszowe
ms.date: 10/16/2017
helpviewer_keywords:
- fast code
- inline functions, __inline keyword
- functions [C++], inline functions
ms.assetid: 00f4b2ff-8ad0-4165-9f4c-2ef157d03f31
ms.openlocfilehash: 616e85f2ac298420b3de174551ea2f6f879f24f1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97137557"
---
# <a name="inline-functions"></a>Funkcje śródwierszowe

**Specyficzne dla firmy Microsoft**

**`__inline`** Słowo kluczowe instruuje kompilator w celu zastąpienia kodu w definicji funkcji dla każdego wystąpienia wywołania funkcji. Jednak podstawianie następuje tylko według uznania kompilatora. Na przykład kompilator nie tworzy wbudowanej funkcji, jeśli jej adres jest zajęty lub jest zbyt duży do inline.

Aby funkcja była brana pod uwagę jako kandydat do tworzenia konspektu, musi używać definicji funkcji New-Style.

Użyj tego formularza, aby określić wbudowaną funkcję:

> **`__inline`***Typ* funkcji <sub>opt</sub> *-Definition*

Użycie funkcji wbudowanych generuje szybszy kod i czasami może generować mniejszy kod niż odpowiednik wywołania funkcji generowane z następujących powodów:

- Zapisuje czas wymagany do wykonania wywołań funkcji.

- Małe wbudowane funkcje, które mogą być trzy lub mniej, tworzą mniej kodu niż równoważne wywołanie funkcji, ponieważ kompilator nie generuje kodu do obsługi argumentów i wartości zwracanej.

- Funkcje wygenerowane wewnętrznie są uzależnione od optymalizacji kodu, które nie są dostępne dla normalnych funkcji, ponieważ kompilator nie wykonuje optymalizacji międzyproceduralnej.

Funkcji using **`__inline`** nie należy mylić z wbudowanym kodem asemblera. Aby uzyskać więcej informacji, zobacz [asembler wbudowany](../c-language/inline-assembler-c.md) .

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[inline, __inline, \_ _forceinline](../cpp/inline-functions-cpp.md)
