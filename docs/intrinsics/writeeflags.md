---
description: 'Dowiedz się więcej na temat: __writeeflags'
title: __writeeflags
ms.date: 09/02/2019
f1_keywords:
- __writeeflags
helpviewer_keywords:
- __writeeflags intrinsics
ms.assetid: a62a522c-d7fa-4f10-a620-a3b32bdf3f17
ms.openlocfilehash: 9c439194782f52b474ec6c6365705ebd8756c6b2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331860"
---
# <a name="__writeeflags"></a>__writeeflags

**Specyficzne dla firmy Microsoft**

Zapisuje określoną wartość do rejestru stan programu i kontrola (EFLAGS).

## <a name="syntax"></a>Składnia

```C
void __writeeflags(unsigned Value); /* x86 */
void __writeeflags(unsigned __int64 Value); /* x64 */
```

### <a name="parameters"></a>Parametry

*Wartościami*\
podczas Wartość, która ma zostać zapisana w rejestrze EFLAGS. `Value`Parametr jest 32 bity long dla platformy 32-bitowej i 64 bity long dla platformy 64-bitowej.

## <a name="remarks"></a>Uwagi

Te procedury są dostępne tylko jako elementy wewnętrzne.

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`__writeeflags`|x86, x64|

**Plik nagłówka**\<intrin.h>

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)\
[__readeflags](../intrinsics/readeflags.md)
