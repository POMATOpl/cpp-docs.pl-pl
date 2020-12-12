---
description: Dowiedz się więcej na temat limitów liczb całkowitych
title: Limity liczb całkowitych
ms.date: 01/29/2018
helpviewer_keywords:
- integral limits
- limits, integer
- limits.h header file
- integer limits
ms.assetid: 6922bdbf-0f49-443b-bc03-ee182e4cbd57
ms.openlocfilehash: 78081f8af1c3d1e1f9f71e5d61dea4ee2bd7085c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345527"
---
# <a name="integer-limits"></a>Limity liczb całkowitych

**specyficzne dla firmy Microsoft**

Limity dla typów całkowitych są wymienione w poniższej tabeli. Makra preprocesora dla tych limitów są również definiowane po dołączeniu standardowego pliku nagłówkowego \<climits> .

## <a name="limits-on-integer-constants"></a>Limity dla stałych całkowitych

| Stała | Znaczenie | Wartość |
|--|--|--|
| `CHAR_BIT` | Liczba bitów w najmniejszej zmiennej, która nie jest polem bitowym. | 8 |
| `SCHAR_MIN` | Minimalna wartość dla zmiennej typu **`signed char`** . | -128 |
| `SCHAR_MAX` | Maksymalna wartość dla zmiennej typu **`signed char`** . | 127 |
| `UCHAR_MAX` | Maksymalna wartość dla zmiennej typu **`unsigned char`** . | 255 (0xFF) |
| `CHAR_MIN` | Minimalna wartość dla zmiennej typu **`char`** . | -128; 0, jeśli **`/J`** użyto opcji |
| `CHAR_MAX` | Maksymalna wartość dla zmiennej typu **`char`** . | 127; 255, jeśli **`/J`** użyto opcji |
| `MB_LEN_MAX` | Maksymalna liczba bajtów w stałej wieloznakowej. | 5 |
| `SHRT_MIN` | Minimalna wartość dla zmiennej typu **`short`** . | -32768 |
| `SHRT_MAX` | Maksymalna wartość dla zmiennej typu **`short`** . | 32767 |
| `USHRT_MAX` | Maksymalna wartość dla zmiennej typu **`unsigned short`** . | 65535 (0xFFFF) |
| `INT_MIN` | Minimalna wartość dla zmiennej typu **`int`** . | -2147483648 |
| `INT_MAX` | Maksymalna wartość dla zmiennej typu **`int`** . | 2147483647 |
| `UINT_MAX` | Maksymalna wartość dla zmiennej typu **`unsigned int`** . | 4294967295 (0xffffffff) |
| `LONG_MIN` | Minimalna wartość dla zmiennej typu **`long`** . | -2147483648 |
| `LONG_MAX` | Maksymalna wartość dla zmiennej typu **`long`** . | 2147483647 |
| `ULONG_MAX` | Maksymalna wartość dla zmiennej typu **`unsigned long`** . | 4294967295 (0xffffffff) |
| `LLONG_MIN` | Minimalna wartość dla zmiennej typu **`long long`** | -zakresu od |
| `LLONG_MAX` | Maksymalna wartość dla zmiennej typu **`long long`** | 9223372036854775807 |
| `ULLONG_MAX` | Maksymalna wartość dla zmiennej typu **`unsigned long long`** | 18446744073709551615 są (0xFFFFFFFFFFFFFFFF) |

Jeśli wartość przekracza największą reprezentację całkowitą, kompilator firmy Microsoft generuje błąd.

## <a name="see-also"></a>Zobacz też

[Limity zmiennoprzecinkowe](../cpp/floating-limits.md)
