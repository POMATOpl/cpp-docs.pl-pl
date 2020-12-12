---
description: 'Dowiedz się więcej na temat: __writedr'
title: __writedr
ms.date: 09/02/2019
f1_keywords:
- __writedr
helpviewer_keywords:
- __writedr intrinsic
ms.assetid: ac55c1ee-df2f-41d4-a429-6f369d2a934d
ms.openlocfilehash: 3a52b8985a28268c430cbb1bfb7b2494e9004820
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331880"
---
# <a name="__writedr"></a>__writedr

**Specyficzne dla firmy Microsoft**

Zapisuje określoną wartość do określonego rejestru debugowania.

## <a name="syntax"></a>Składnia

```C
void __writedr(unsigned DebugRegister, unsigned DebugValue); /* x86 */
void __writedr(unsigned DebugRegister, unsigned __int64 DebugValue); /* x64 */
```

### <a name="parameters"></a>Parametry

*DebugRegister*\
podczas Liczba od 0 do 7, która identyfikuje rejestr debugowania.

*DebugValue*\
podczas Wartość do zapisu w rejestrze debugowania.

## <a name="remarks"></a>Uwagi

Te elementy wewnętrzne są dostępne tylko w trybie jądra, a procedury są dostępne tylko jako elementy wewnętrzne.

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`__writedr`|x86, x64|

**Plik nagłówka**\<intrin.h>

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)\
[__readdr](../intrinsics/readdr.md)
