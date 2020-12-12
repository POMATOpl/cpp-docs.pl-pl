---
description: Dowiedz się więcej o strukturze biostanowej
title: Struktura półprzewodnikowa
ms.date: 04/04/2019
f1_keywords:
- variant/std::monostate
helpviewer_keywords:
- monostate struct
ms.openlocfilehash: 93b21f399761970129a495590e0821aa911a0408
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97115160"
---
# <a name="monostate-struct"></a>Struktura półprzewodnikowa

Półprzewodnikowa Klasa służy jako typ alternatywny dla wariantu, aby typ Variant konstrukcyjną domyślny.

## <a name="syntax"></a>Składnia

```cpp
struct monostate;

constexpr bool operator<(monostate, monostate) noexcept;
constexpr bool operator>(monostate, monostate) noexcept;
constexpr bool operator<=(monostate, monostate) noexcept;
constexpr bool operator>=(monostate, monostate) noexcept;
constexpr bool operator==(monostate, monostate) noexcept;
constexpr bool operator!=(monostate, monostate) noexcept;
```
