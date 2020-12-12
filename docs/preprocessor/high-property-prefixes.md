---
description: 'Dowiedz się więcej na temat: high_property_prefixes Importowanie atrybutu'
title: high_property_prefixes atrybut importowania
ms.date: 08/29/2019
f1_keywords:
- high_property_prefixes
helpviewer_keywords:
- high_property_prefixes attribute
ms.assetid: 91c6cc2b-19b6-4aba-8831-d9e5cccb58b5
ms.openlocfilehash: af6835f5835c23dceadbb5152e36b0dabcbb8c98
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167477"
---
# <a name="high_property_prefixes-import-attribute"></a>high_property_prefixes atrybut importowania

**Specyficzne dla języka C++**

Określa alternatywne prefiksy dla trzech metod właściwości.

## <a name="syntax"></a>Składnia

> **#import** *high_property_prefixes biblioteki typów* **(** "*getprefix*" **,** "*PutPrefix*" **,** "*PutRefPrefix*" **)**

### <a name="parameters"></a>Parametry

*Getprefix*\
Prefiks, który ma być używany dla `propget` metod.

*PutPrefix*\
Prefiks, który ma być używany dla `propput` metod.

*PutRefPrefix*\
Prefiks, który ma być używany dla `propputref` metod.

## <a name="remarks"></a>Uwagi

Domyślnie metody obsługi błędów wysokiego poziomu `propget` , `propput` , i `propputref` są uwidaczniane przez funkcje Członkowskie o nazwach z prefiksami `Get` , `Put` i, `PutRef` odpowiednio.

**ZAKOŃCZENIE specyficzne dla języka C++**

## <a name="see-also"></a>Zobacz też

[Atrybuty #import](../preprocessor/hash-import-attributes-cpp.md)\
[#import — dyrektywa](../preprocessor/hash-import-directive-cpp.md)
