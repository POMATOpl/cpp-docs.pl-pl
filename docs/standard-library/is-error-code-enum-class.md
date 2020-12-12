---
description: Dowiedz się więcej na temat klasy is_error_code_enum
title: is_error_code_enum — Klasa
ms.date: 11/04/2016
f1_keywords:
- system_error/std::is_error_code_enum
helpviewer_keywords:
- is_error_code_enum class
ms.assetid: cee5be2d-7c20-4cec-a352-1ab8b7d32601
ms.openlocfilehash: 359f15c3d809435df81408a721a0c9ad11c1e7e5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323758"
---
# <a name="is_error_code_enum-class"></a>is_error_code_enum — Klasa

Reprezentuje predykat typu, który testuje [error_code](../standard-library/error-code-class.md) Wyliczenie.

## <a name="syntax"></a>Składnia

```cpp
template <_Enum>
    class is_error_code_enum;
```

## <a name="remarks"></a>Uwagi

Wystąpienie tego [predykatu typu](../standard-library/type-traits.md) ma wartość true, jeśli typ `_Enum` jest wartością wyliczenia odpowiednią do przechowywania w obiekcie typu `error_code` .

Dozwolone jest dodanie specjalizacji do tego typu dla typów zdefiniowanych przez użytkownika.

## <a name="see-also"></a>Zobacz też

[<type_traits>](../standard-library/type-traits.md)
