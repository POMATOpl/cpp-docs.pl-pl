---
description: 'Dowiedz się więcej na temat: __addfsbyte, __addfsword, __addfsdword'
title: __addfsbyte, __addfsword, __addfsdword
ms.date: 09/02/2019
f1_keywords:
- __addfsbyte_cpp
- __addfsdword
- __addfsword_cpp
- __addfsbyte
- __addfsword
- __addfsdword_cpp
helpviewer_keywords:
- __addfsdword intrinsic
- __addfsword intrinsic
- __addfsbyte intrinsic
ms.assetid: 706c70df-6b52-4401-9268-2977ed8ad715
ms.openlocfilehash: 414327e93ac2d342842f161148453505d49dcce8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222518"
---
# <a name="__addfsbyte-__addfsword-__addfsdword"></a>__addfsbyte, __addfsword, __addfsdword

**Specyficzne dla firmy Microsoft**

Dodaj wartość do lokalizacji pamięci określonej przez przesunięcie względem początku `FS` segmentu.

## <a name="syntax"></a>Składnia

```C
void __addfsbyte(
   unsigned long Offset,
   unsigned char Data
);
void __addfsword(
   unsigned long Offset,
   unsigned short Data
);
void __addfsdword(
   unsigned long Offset,
   unsigned long Data
);
```

### <a name="parameters"></a>Parametry

*Przesunięcie*\
podczas Przesunięcie od początku `FS` .

*Data*\
podczas Wartość, która ma zostać dodana do lokalizacji pamięci.

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`__addfsbyte`|x86|
|`__addfsword`|x86|
|`__addfsdword`|x86|

**Plik nagłówka**\<intrin.h>

## <a name="remarks"></a>Uwagi

Te procedury są dostępne tylko jako elementy wewnętrzne.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[__incfsbyte, \_ _incfsword, \_ _incfsdword](../intrinsics/incfsbyte-incfsword-incfsdword.md)\
[__readfsbyte, \_ _readfsdword, \_ _readfsqword \_ _readfsword](../intrinsics/readfsbyte-readfsdword-readfsqword-readfsword.md)\
[__writefsbyte, \_ _writefsdword, \_ _writefsqword \_ _writefsword](../intrinsics/writefsbyte-writefsdword-writefsqword-writefsword.md)\
[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)
