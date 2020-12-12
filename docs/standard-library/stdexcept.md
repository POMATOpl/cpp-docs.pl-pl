---
description: 'Dowiedz się więcej na temat: &lt; stdexcept&gt;'
title: '&lt;stdexcept&gt;'
ms.date: 11/04/2016
f1_keywords:
- <stdexcept>
helpviewer_keywords:
- stdexcept header
ms.assetid: 495c10b1-1e60-4514-9f8f-7fda11a2f522
ms.openlocfilehash: 07ab90442630c6dfb5a96604ba7c0cb6b214f605
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97169089"
---
# <a name="ltstdexceptgt"></a>&lt;stdexcept&gt;

Definiuje kilka klas standardowych używanych do raportowania wyjątków. Klasy tworzą hierarchię pochodną wszystkie pochodne od [wyjątku](../standard-library/exception-class.md) klasy i zawierają dwa typy ogólne wyjątków: Błędy logiczne i błędy czasu wykonywania. Błędy logiczne są spowodowane błędami programisty. Pochodzą one z klasy bazowej logic_error i obejmują:

- `domain_error`

- `invalid_argument`

- `length_error`

- `out_of_range`

Błędy w czasie wykonywania występują z powodu błędów w funkcjach biblioteki lub w systemie czasu wykonywania. Pochodzą one z klasy bazowej runtime_error i obejmują:

- `overflow_error`

- `range_error`

- `underflow_error`

### <a name="classes"></a>Klasy

|Klasa|Opis|
|-|-|
|[Klasa domain_error](../standard-library/domain-error-class.md)|Klasa służy jako klasa bazowa dla wszystkich wyjątków zgłoszonych w celu zgłaszania błędu domeny.|
|[Klasa invalid_argument](../standard-library/invalid-argument-class.md)|Klasa służy jako klasa bazowa dla wszystkich wyjątków zgłoszonych w celu zgłoszenia nieprawidłowego argumentu.|
|[Klasa length_error](../standard-library/length-error-class.md)|Klasa służy jako klasa bazowa dla wszystkich wyjątków zgłoszonych w celu zgłoszenia próby wygenerowania obiektu zbyt długo.|
|[Klasa logic_error](../standard-library/logic-error-class.md)|Klasa służy jako klasa bazowa dla wszystkich wyjątków zgłoszonych w celu zgłaszania błędów, które są wykrywalne przed wykonaniem programu, na przykład naruszenia logicznych warunków wstępnych.|
|[Klasa out_of_range](../standard-library/out-of-range-class.md)|Klasa służy jako klasa bazowa dla wszystkich wyjątków zgłoszonych w celu zgłoszenia argumentu, który jest poza prawidłowym zakresem.|
|[Klasa overflow_error](../standard-library/overflow-error-class.md)|Klasa służy jako klasa bazowa dla wszystkich wyjątków zgłoszonych do zgłaszania przepełnienia arytmetycznego.|
|[Klasa range_error](../standard-library/range-error-class.md)|Klasa służy jako klasa bazowa dla wszystkich wyjątków zgłoszonych w celu zgłaszania błędu zakresu.|
|[Klasa runtime_error](../standard-library/runtime-error-class.md)|Klasa służy jako klasa bazowa dla wszystkich wyjątków zgłoszonych w celu zgłaszania błędów, które mogą być wykrywalne tylko wtedy, gdy program jest wykonywany.|
|[Klasa underflow_error](../standard-library/underflow-error-class.md)|Klasa służy jako klasa bazowa dla wszystkich wyjątków zgłoszonych do zgłaszania niedopełnienia arytmetycznego.|

## <a name="see-also"></a>Zobacz też

[Dokumentacja plików nagłówkowych](../standard-library/cpp-standard-library-header-files.md)\
[Bezpieczeństwo wątku w standardowej bibliotece języka C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
