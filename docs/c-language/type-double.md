---
description: 'Dowiedz się więcej na temat: typ Double'
title: Typ double
ms.date: 11/04/2016
helpviewer_keywords:
- mantissas, floating-point variables
- type double
- portability [C++], type double
- double data type
ms.assetid: 17c85b24-1475-4d41-a03c-ddf2d6561d34
ms.openlocfilehash: c30af4ef432251ddf38be2172102ff7a63254940
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242850"
---
# <a name="type-double"></a>Typ double

Wartości podwójnej precyzji o podwójnym typie mają 8 bajtów. Format jest podobny do formatu zmiennoprzecinkowego, z tą różnicą, że ma 11-bitowy przekroczenie 1023 wykładnika i 52-bitowy mantysy, plus implikowana 1 bit o wysokiej kolejności. Ten format daje zakres około 1.7 E-308 do 1.7 E + 308 dla typu Double.

**Specyficzne dla firmy Microsoft**

Podwójny typ zawiera 64 bitów: 1 dla znaku, 11 dla wykładnika i 52 dla mantysy. Jego zakresem jest +/-1.7E308 z dokładnością co najmniej 15 cyfr.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Magazyn typów podstawowych](../c-language/storage-of-basic-types.md)
