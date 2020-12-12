---
description: 'Dowiedz się więcej na temat: wykluczanie atrybutu import'
title: Wyklucz Importowanie atrybutu
ms.date: 08/29/2019
f1_keywords:
- exclude
helpviewer_keywords:
- exclude attribute
ms.assetid: 0883248a-d4bf-420e-9848-807b28fa976e
ms.openlocfilehash: e856544f812fd5d0b14676beb8423c4350e40da1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97269318"
---
# <a name="exclude-import-attribute"></a>Wyklucz Importowanie atrybutu

**Specyficzne dla języka C++**

Wyklucza elementy z generowanych plików nagłówkowych biblioteki typów.

## <a name="syntax"></a>Składnia

> **#import wykluczenia** *biblioteki typów* **(** "*Name1*" [ **,** "*NAME2*"...] **)**

### <a name="parameters"></a>Parametry

*Name1*\
Pierwszy element, który ma zostać wykluczony.

*NAME2*\
Obowiązkowe Elementy sekundowe i późniejsze do wykluczenia, w razie potrzeby.

## <a name="remarks"></a>Uwagi

Biblioteki typów mogą zawierać definicje elementów zdefiniowanych w nagłówkach systemowych lub innych bibliotekach typów. Ten atrybut może przyjmować dowolną liczbę argumentów, gdzie każda z nich jest elementem biblioteki typu najwyższego poziomu, który ma zostać wykluczony.

**ZAKOŃCZENIE specyficzne dla języka C++**

## <a name="see-also"></a>Zobacz też

[Atrybuty #import](../preprocessor/hash-import-attributes-cpp.md)\
[#import — dyrektywa](../preprocessor/hash-import-directive-cpp.md)
