---
description: 'Dowiedz się więcej na temat: TLBID — atrybut importowania'
title: TLBID — atrybut importowania
ms.date: 08/29/2019
f1_keywords:
- tlbid
helpviewer_keywords:
- tlbid attribute
ms.assetid: 54b06785-191b-4e77-a9a5-485f2b4acb09
ms.openlocfilehash: 9bbf15f64c1813013fcd839a2d4f0a34c9872aff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339043"
---
# <a name="tlbid-import-attribute"></a>TLBID — atrybut importowania

**Specyficzne dla języka C++**

Umożliwia ładowanie bibliotek poza podstawową biblioteką typów.

## <a name="syntax"></a>Składnia

> **#import** *Type-Library-dll* **TLBID (** *Liczba* **)**

### <a name="parameters"></a>Parametry

*Liczba*\
Liczba bibliotek typów w *bibliotece typów*.

## <a name="remarks"></a>Uwagi

Jeśli wiele bibliotek typów jest wbudowanych w jedną bibliotekę DLL, można załadować biblioteki inne niż podstawowe biblioteki typów za pomocą **TLBID**.

Na przykład:

```cpp
#import <MyResource.dll> tlbid(2)
```

jest równoważne:

```cpp
LoadTypeLib("MyResource.dll\\2");
```

**ZAKOŃCZENIE specyficzne dla języka C++**

## <a name="see-also"></a>Zobacz też

[Atrybuty #import](../preprocessor/hash-import-attributes-cpp.md)\
[#import — dyrektywa](../preprocessor/hash-import-directive-cpp.md)
