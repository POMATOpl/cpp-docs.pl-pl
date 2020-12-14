---
description: 'Dowiedz się więcej na temat: raw_native_types Importowanie atrybutu'
title: raw_native_types atrybut importowania
ms.date: 08/29/2019
f1_keywords:
- raw_native_types
helpviewer_keywords:
- raw_native_types attribute
ms.assetid: 9f38daa8-8dc0-46a5-aff9-f1ff9c1e6f48
ms.openlocfilehash: 64eaadcbb3d9f07d47dd4a33bc16a222cae50f38
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97240536"
---
# <a name="raw_native_types-import-attribute"></a>raw_native_types atrybut importowania

**Specyficzne dla języka C++**

Wyłącza korzystanie z klas obsługi COM w funkcjach otoki wysokiego poziomu i wymusza użycie typów danych niskiego poziomu.

## <a name="syntax"></a>Składnia

> **#import** **raw_native_types** *biblioteki typów*

## <a name="remarks"></a>Uwagi

Domyślnie metody obsługi błędów wysokiego poziomu wykorzystują klasy obsługi COM [_bstr_t](../cpp/bstr-t-class.md) i [_variant_t](../cpp/variant-t-class.md) zamiast `BSTR` `VARIANT` typów danych i surowych wskaźników interfejsu com. Te klasy hermetyzowają szczegóły alokacji i cofania przydziału pamięci masowej dla tych typów danych oraz znacznie upraszczają Operacje rzutowania i konwersji typów.

**ZAKOŃCZENIE specyficzne dla języka C++**

## <a name="see-also"></a>Zobacz też

[Atrybuty #import](../preprocessor/hash-import-attributes-cpp.md)\
[#import — dyrektywa](../preprocessor/hash-import-directive-cpp.md)
