---
description: 'Dowiedz się więcej na temat: raw_interfaces_only Importowanie atrybutu'
title: raw_interfaces_only atrybut importowania
ms.date: 08/29/2019
f1_keywords:
- raw_interfaces_only
helpviewer_keywords:
- raw_interfaces_only attribute
ms.assetid: 87056c6d-3f34-4248-af58-f5775a35bfb7
ms.openlocfilehash: f043bef5cde0454ce9f08f45efb0417aa7fdbb2d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142743"
---
# <a name="raw_interfaces_only-import-attribute"></a>raw_interfaces_only atrybut importowania

**Specyficzne dla języka C++**

Pomija generowanie funkcji otoki obsługujących błędy i deklaracji [Właściwości](../cpp/property-cpp.md) , które korzystają z tych funkcji otoki.

## <a name="syntax"></a>Składnia

> **#import** **raw_interfaces_only** *biblioteki typów*

## <a name="remarks"></a>Uwagi

Atrybut **raw_interfaces_only** powoduje również, że domyślny prefiks używany do nadawania nazw funkcji niebędących właściwościami do usunięcia. Zwykle prefiks jest `raw_` . Jeśli ten atrybut jest określony, nazwy funkcji są pobierane bezpośrednio z biblioteki typów.

Ten atrybut umożliwia uwidocznienie tylko zawartości niskiego poziomu w bibliotece typów.

**ZAKOŃCZENIE specyficzne dla języka C++**

## <a name="see-also"></a>Zobacz też

[Atrybuty #import](../preprocessor/hash-import-attributes-cpp.md)\
[#import — dyrektywa](../preprocessor/hash-import-directive-cpp.md)
