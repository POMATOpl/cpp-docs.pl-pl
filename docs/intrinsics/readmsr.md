---
description: 'Dowiedz się więcej na temat: __readmsr'
title: __readmsr
ms.date: 09/02/2019
f1_keywords:
- __readmsr
helpviewer_keywords:
- Read Model Specific Register
- rdmsr instruction
- __readmsr intrinsic
ms.assetid: 7ab1f8e8-72cb-4ce4-817d-3e728a3c9716
ms.openlocfilehash: 1a8acae272a450cb4470744e434277576cc8b9c4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97271918"
---
# <a name="__readmsr"></a>__readmsr

**Specyficzne dla firmy Microsoft**

Generuje `rdmsr` instrukcję, która odczytuje rejestr specyficzny dla modelu określony przez **`register`** i zwraca jego wartość.

## <a name="syntax"></a>Składnia

```C
__int64 __readmsr(
   int register
);
```

### <a name="parameters"></a>Parametry

*zarejestrować*\
podczas Rejestr specyficzny dla modelu, który ma zostać odczytany.

## <a name="return-value"></a>Wartość zwracana

Wartość w określonym rejestrze.

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`__readmsr`|x86, x64|

**Plik nagłówka**\<intrin.h>

## <a name="remarks"></a>Uwagi

Ta funkcja jest dostępna tylko w trybie jądra, a procedura jest dostępna tylko jako wewnętrzna.

Aby uzyskać więcej informacji, zobacz dokumentację AMD.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)
