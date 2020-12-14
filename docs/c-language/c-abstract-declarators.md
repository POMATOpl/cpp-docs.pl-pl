---
description: Dowiedz się więcej o Deklaratory abstrakcyjnym języka C
title: Deklaratory abstrakcyjne języka C
ms.date: 11/04/2016
helpviewer_keywords:
- declarators, abstract
- abstract declarations
ms.assetid: 6a556ad7-0555-421a-aa02-294d77cda8b5
ms.openlocfilehash: 9af51d96ac50222b9148060147812aecdf114b7d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97211612"
---
# <a name="c-abstract-declarators"></a>Deklaratory abstrakcyjne języka C

Abstrakcyjny deklarator to deklarator bez identyfikatora składający się z co najmniej jednego modyfikatora wskaźnika, tablicy lub funkcji. Modyfikator wskaźnika ( <strong>\*</strong> ) zawsze poprzedza identyfikator w modyfikatorze deklarator; Array (**[]**) i funkcji ( **()** ) podążać za identyfikatorem. Wiedząc, że identyfikator będzie widoczny w abstrakcyjnej deklarator i odpowiednio interpretuje deklarator. Zobacz [Interpretowanie bardziej złożonej Deklaratory](../c-language/interpreting-more-complex-declarators.md) , aby uzyskać dodatkowe informacje i przykłady złożonej Deklaratory. Zwykle **`typedef`** może służyć do uproszczenia Deklaratory. Zobacz [deklaracje typedef](../c-language/typedef-declarations.md).

Abstrakcyjny Deklaratory może być skomplikowany. Nawiasy w złożonej deklarator abstrakcyjnej określają konkretną interpretację, podobnie jak w przypadku złożonych Deklaratory w deklaracjach.

Przykłady te ilustrują abstrakcyjny Deklaratory:

```
int *         // The type name for a pointer to type int:

int *[3]      // An array of three pointers to int

int (*) [5]   // A pointer to an array of five int

int *()       // A function with no parameter specification
              // returning a pointer to int

// A pointer to a function taking no arguments and
// returning an int

int (*) ( void )

// An array of an unspecified number of constant pointers to
// functions each with one parameter that has type unsigned int
// and an unspecified number of other parameters returning an int

int (*const []) ( unsigned int, ... )
```

> [!NOTE]
> Abstrakcyjny deklarator składający się z zestawu pustych nawiasów **()** jest niedozwolony, ponieważ jest niejednoznaczny. Nie można ustalić, czy implikowany identyfikator należy do nawiasów (w którym przypadku jest to niemodyfikowany typ) czy przed nawiasami (w tym przypadku jest to typ funkcji).

## <a name="see-also"></a>Zobacz też

[Deklaratory i deklaracje zmiennych](../c-language/declarators-and-variable-declarations.md)
