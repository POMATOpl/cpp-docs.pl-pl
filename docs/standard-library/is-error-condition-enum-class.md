---
description: Dowiedz się więcej na temat klasy is_error_condition_enum
title: is_error_condition_enum — Klasa
ms.date: 11/04/2016
f1_keywords:
- system_error/std::is_error_condition_enum
helpviewer_keywords:
- is_error_condition_enum class
ms.assetid: 752bb87a-c61c-4304-9254-5aaf228b59c0
ms.openlocfilehash: 3fd4f95e06ebee66a1f4d7d0e7de039d26b9f1fe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323731"
---
# <a name="is_error_condition_enum-class"></a>is_error_condition_enum — Klasa

Reprezentuje predykat typu, który testuje [error_condition](../standard-library/error-condition-class.md) Wyliczenie.

## <a name="syntax"></a>Składnia

```cpp
template <_Enum>
    class is_error_condition_enum;
```

## <a name="remarks"></a>Uwagi

Wystąpienie tego [predykatu typu](../standard-library/type-traits.md) ma wartość true, jeśli typ `_Enum` jest wartością wyliczenia odpowiednią do przechowywania w obiekcie typu `error_condition` .

Dozwolone jest dodanie specjalizacji do tego typu dla typów zdefiniowanych przez użytkownika.

## <a name="see-also"></a>Zobacz też

[<type_traits>](../standard-library/type-traits.md)
