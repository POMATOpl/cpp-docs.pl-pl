---
description: 'Dowiedz się więcej na temat: &lt; typeindex&gt;'
title: '&lt;typeindex&gt;'
ms.date: 11/04/2016
f1_keywords:
- <typeindex>
ms.assetid: a9551137-f74b-4f02-af64-ff00214cea1f
ms.openlocfilehash: 0f5aee958aee01bcccc87145087001f093ab6749
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226444"
---
# <a name="lttypeindexgt"></a>&lt;typeindex&gt;

Dołącz standardowy nagłówek, \<typeindex> Aby zdefiniować klasę i funkcję, która obsługuje indeksowanie obiektów klasy [type_info](../cpp/type-info-class.md).

## <a name="syntax"></a>Składnia

```cpp
#include <typeindex>
```

## <a name="remarks"></a>Uwagi

[Struktura skrótu](../standard-library/hash-structure.md) definiuje `hash function` odpowiednie do mapowania wartości typu [type_index](../standard-library/type-index-class.md) na rozkład wartości indeksu.

`type_index`Klasa otacza wskaźnik do `type_info` obiektu, aby pomóc w indeksowaniu.

## <a name="see-also"></a>Zobacz też

[Dokumentacja plików nagłówkowych](../standard-library/cpp-standard-library-header-files.md)\
[Bezpieczeństwo wątku w standardowej bibliotece języka C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Dokumentacja standardowej biblioteki języka C++](../standard-library/cpp-standard-library-reference.md)
