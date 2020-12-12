---
description: 'Dowiedz się więcej na temat: Operatory rzutowania'
title: Operatory rzutowania
ms.custom: index-page
ms.date: 11/04/2016
helpviewer_keywords:
- operators [C++], casting
- casting operators [C++]
ms.assetid: 16240348-26bc-4f77-8eab-57253f00ce52
ms.openlocfilehash: 6ab19f1b30958f4d78a97be76c15373ed9c9b620
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97308552"
---
# <a name="casting-operators"></a>Operatory rzutowania

Istnieje kilka operatorów rzutowania specyficznych dla języka C++. Te operatory są przeznaczone do usuwania niektórych niejednoznaczności i niebezpieczeństwa związanych ze starym stylem rzutowania języka C. Są to następujące operatory:

- [dynamic_cast](../cpp/dynamic-cast-operator.md) Używane do konwersji typów polimorficznych.

- [static_cast](../cpp/static-cast-operator.md) Używane do konwersji typów niepolimorficznych.

- [const_cast](../cpp/const-cast-operator.md) Służy do usuwania **`const`** atrybutów, **`volatile`** i **`__unaligned`** .

- [reinterpret_cast](../cpp/reinterpret-cast-operator.md) Używane do prostej interpretacji bitów.

- [safe_cast](../extensions/safe-cast-cpp-component-extensions.md) Używane w języku C++/CLI do tworzenia zweryfikowanych MSIL.

Użyj **`const_cast`** i **`reinterpret_cast`** jako ostatni z nich, ponieważ te operatory mają takie same zagrożenia, jak w przypadku starych stylów. Jednak nadal są one niezbędne w celu całkowitego zastąpienia starych stylów.

## <a name="see-also"></a>Zobacz też

[Rzutowanie](../cpp/casting.md)
