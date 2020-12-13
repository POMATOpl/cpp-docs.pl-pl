---
description: 'Dowiedz się więcej na temat: raw_property_prefixes Importowanie atrybutu'
title: raw_property_prefixes atrybut importowania
ms.date: 08/29/2019
f1_keywords:
- raw_property_prefixes
helpviewer_keywords:
- raw_property_prefixes attribute
ms.assetid: 03a0f48c-c460-4175-a762-9f7f8d84b12f
ms.openlocfilehash: 7289f9aeba249249ecf78ffb3ad3b32669ac9fe3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142717"
---
# <a name="raw_property_prefixes-import-attribute"></a>raw_property_prefixes atrybut importowania

**Specyficzne dla języka C++**

Określa alternatywne prefiksy dla trzech metod właściwości.

## <a name="syntax"></a>Składnia

> **#import** *raw_property_prefixes biblioteki typów* **(** "*getprefix*" **,** "*PutPrefix*" **,** "*PutRefPrefix*" **)**

### <a name="parameters"></a>Parametry

*Getprefix*\
Prefiks do użycia dla `propget` metod.

*PutPrefix*\
Prefiks do użycia dla `propput` metod.

*PutRefPrefix*\
Prefiks do użycia dla `propputref` metod.

## <a name="remarks"></a>Uwagi

Domyślnie, metody niskiego poziomu `propget` , `propput` i `propputref` są uwidaczniane przez funkcje Członkowskie o nazwach za pomocą prefiksów `get_` , `put_` i, `putref_` odpowiednio. Te prefiksy są zgodne z nazwami używanymi w plikach nagłówkowych generowanych przez MIDL.

**ZAKOŃCZENIE specyficzne dla języka C++**

## <a name="see-also"></a>Zobacz też

[Atrybuty #import](../preprocessor/hash-import-attributes-cpp.md)\
[#import — dyrektywa](../preprocessor/hash-import-directive-cpp.md)
