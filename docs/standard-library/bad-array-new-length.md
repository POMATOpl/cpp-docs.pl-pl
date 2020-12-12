---
description: Dowiedz się więcej na temat klasy bad_array_new_length
title: Klasa bad_array_new_length
ms.date: 11/04/2016
f1_keywords:
- new/std::bad_array_new_length
helpviewer_keywords:
- bad_alloc class
ms.assetid: 6429a8e6-5a49-4907-8d56-f4a4ec8131d0
ms.openlocfilehash: e9de10b6fee215651ac8ff6ce2fce4af55ce6c82
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321643"
---
# <a name="bad_array_new_length-class"></a>Klasa bad_array_new_length

Klasa zawiera opis zgłoszonego wyjątku, aby wskazać, że żądanie alokacji nie zakończyło się niepowodzeniem z powodu rozmiaru tablicy mniejszego niż zero lub większego od jego limitu.

## <a name="syntax"></a>Składnia

```cpp
class bad_array_new_length : public bad_alloc {
    public: bad_array_new_length() noexcept;
    const char* what() const noexcept override;
};
```

## <a name="remarks"></a>Uwagi

Wartość zwrócona przez `what` to ciąg języka C zdefiniowany przez implementację. Żadna z funkcji Członkowskich nie zgłasza żadnych wyjątków.

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<new>

## <a name="see-also"></a>Zobacz też

[Klasa wyjątku](../standard-library/exception-class.md)\
[Bezpieczeństwo wątku w standardowej bibliotece języka C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
