---
description: 'Dowiedz się więcej na temat: &lt; wykonywanie&gt;'
title: '&lt;działania&gt;'
ms.date: 04/18/2019
f1_keywords:
- <execution>
- std::<execution>
helpviewer_keywords:
- execution header
ms.openlocfilehash: ea444ab2f4fcf3211e85837701a8ea6a0c3ec81f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324412"
---
# <a name="ltexecutiongt"></a>&lt;działania&gt;

Opisuje zasady wykonywania dla algorytmów równoległych.

## <a name="syntax"></a>Składnia

```
namespace std {
    template<class T> inline constexpr bool is_execution_policy_v = is_execution_policy<T>::value;
}
namespace std::execution {
    inline constexpr sequenced_policy seq { unspecified };
    inline constexpr parallel_policy par { unspecified };
    inline constexpr parallel_unsequenced_policy par_unseq { unspecified };
}
```

### <a name="classes-and-structs"></a>Klasy i struktury

|Nazwa|Opis|
|-|-|
|[Struktura is_execution_policy](is-execution-policy-struct.md)|Wykrywa zasady wykonywania w celu wykluczania podpisów funkcji ze względu na niejednoznaczny udział w rozpoznawaniu przeciążenia.|
|[Klasa parallel_policy](parallel-policy-class.md)|Używany jako unikatowy typ niejednoznacznego przeciążenia algorytmu równoległego i wskazujący, że wykonywanie algorytmu równoległego może być równoległe.|
|[Klasa parallel_unsequenced_policy](parallel-unsequenced-policy-class.md)|Używany jako unikatowy typ niejednoznacznego przeciążenia algorytmu równoległego i wskazujący, że wykonywanie algorytmu równoległego może być równoległe i wektorowe.|
|[Klasa sequenced_policy](sequenced-policy-class.md)|Używany jako unikatowy typ odróżnienia przeciążenia algorytmu równoległego i wymaganie, aby wykonywanie algorytmu równoległego mogło nie być równoległe.|

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<execution>

**Przestrzeń nazw:** stdext

## <a name="see-also"></a>Zobacz też

[Dokumentacja plików nagłówkowych](cpp-standard-library-header-files.md)\
[Bezpieczeństwo wątku w standardowej bibliotece języka C++](thread-safety-in-the-cpp-standard-library.md)\
[Dokumentacja standardowej biblioteki języka C++](cpp-standard-library-reference.md)
