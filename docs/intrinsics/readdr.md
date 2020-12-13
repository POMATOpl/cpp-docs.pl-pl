---
description: 'Dowiedz się więcej na temat: __readdr'
title: __readdr
ms.date: 09/02/2019
f1_keywords:
- __readdr
helpviewer_keywords:
- __readdr intrinsic
ms.assetid: 061b05da-c85e-4052-b392-106f14bb84f1
ms.openlocfilehash: b3b5952d940db91b278344ab45edb3e8b914c094
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341012"
---
# <a name="__readdr"></a>__readdr

**Specyficzne dla firmy Microsoft**

Odczytuje wartość określonego rejestru debugowania.

## <a name="syntax"></a>Składnia

```C
unsigned         __readdr(unsigned int DebugRegister); /* x86 */
unsigned __int64 __readdr(unsigned int DebugRegister); /* x64 */
```

### <a name="parameters"></a>Parametry

*DebugRegister*\
podczas Stała od 0 do 7, która identyfikuje rejestr debugowania.

## <a name="return-value"></a>Wartość zwracana

Wartość określonego rejestru debugowania.

## <a name="remarks"></a>Uwagi

Te elementy wewnętrzne są dostępne tylko w trybie jądra, a procedury są dostępne tylko jako elementy wewnętrzne.

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`__readdr`|x86, x64|

**Plik nagłówka**\<intrin.h>

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)\
[__readeflags](../intrinsics/readeflags.md)
