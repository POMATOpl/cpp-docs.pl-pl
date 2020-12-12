---
description: 'Dowiedz się więcej na temat: rename_namespace Importowanie atrybutu'
title: rename_namespace atrybut importowania
ms.date: 08/29/2019
f1_keywords:
- rename_namespace
helpviewer_keywords:
- rename_namespace attribute
ms.assetid: 45006d2b-36cd-4bec-98b9-3b8ec45299e3
ms.openlocfilehash: 402d9c9cd8dee5979dd71e16fec1a606d8b4b996
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167386"
---
# <a name="rename_namespace-import-attribute"></a>rename_namespace atrybut importowania

**Specyficzne dla języka C++**

Zmienia nazwę przestrzeni nazw, która zawiera zawartość biblioteki typów.

## <a name="syntax"></a>Składnia

> **#import** rename_namespace *biblioteki typów* **(** "*newname*" **)**

### <a name="parameters"></a>Parametry

*NewName*\
Nowa nazwa przestrzeni nazw.

## <a name="remarks"></a>Uwagi

Atrybut **rename_namespace** przyjmuje jeden argument, *nowa_nazwa*, który określa nową nazwę przestrzeni nazw.

Aby usunąć przestrzeń nazw, zamiast tego użyj atrybutu [no_namespace](../preprocessor/no-namespace.md) .

**ZAKOŃCZENIE specyficzne dla języka C++**

## <a name="see-also"></a>Zobacz też

[Atrybuty #import](../preprocessor/hash-import-attributes-cpp.md)\
[#import — dyrektywa](../preprocessor/hash-import-directive-cpp.md)
