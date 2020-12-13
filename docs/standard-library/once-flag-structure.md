---
description: Dowiedz się więcej na temat struktury once_flag
title: once_flag — Struktura
ms.date: 09/17/2018
f1_keywords:
- mutex/std::once_flag
ms.assetid: 71bfb88d-ca8c-4082-a6e1-ff52151e8629
ms.openlocfilehash: 4419353e68da5929d8abed9b2c718438855057e0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338007"
---
# <a name="once_flag-structure"></a>once_flag — Struktura

Reprezentuje **`struct`** , który jest używany z funkcją szablonu [call_once](../standard-library/mutex-functions.md#call_once) , aby upewnić się, że kod inicjalizacji jest wywoływany tylko raz, nawet w obecności wielu wątków wykonania.

## <a name="syntax"></a>Składnia

Struktura once_flag {constexpr once_flag () noexcept;};

## <a name="remarks"></a>Uwagi

`once_flag` **`struct`** Ma tylko domyślny Konstruktor.

Obiekty typu `once_flag` można tworzyć, ale nie mogą być kopiowane.

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<mutex>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[Dokumentacja plików nagłówkowych](../standard-library/cpp-standard-library-header-files.md)\
[\<mutex>](../standard-library/mutex.md)
