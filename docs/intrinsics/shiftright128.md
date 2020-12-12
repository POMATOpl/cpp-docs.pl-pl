---
description: 'Dowiedz się więcej na temat: __shiftright128'
title: __shiftright128
ms.date: 09/02/2019
f1_keywords:
- __shiftright128
helpviewer_keywords:
- __shiftright128 intrinsic
ms.assetid: 5419a6c4-0de1-43fb-b314-4faa5b2d051f
ms.openlocfilehash: 71f8a0d9b740ebfef5e930715e07d1ec31950269
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97306979"
---
# <a name="__shiftright128"></a>__shiftright128

**Specyficzne dla firmy Microsoft**

Przenosi ilość 128-bitową, reprezentowaną jako 2 64-bitowe ilości `LowPart` i `HighPart` , po prawej stronie przez liczbę bitów określoną przez `Shift` , i zwraca niskie 64 bitów wyniku.

## <a name="syntax"></a>Składnia

```C
unsigned __int64 __shiftright128(
   unsigned __int64 LowPart,
   unsigned __int64 HighPart,
   unsigned char Shift
);
```

### <a name="parameters"></a>Parametry

*LowPart*\
podczas Niska 64 bitów ilości 128-bitowej do przesunięcia.

*HighPart*\
podczas Wysoka 64 bitów 128-bitowej liczby do przesunięcia.

*Nocn*\
podczas Liczba bitów do przesunięcia.

## <a name="return-value"></a>Wartość zwracana

Niska 64 bitów wyniku.

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`__shiftright128`|x64|

**Plik nagłówka**\<intrin.h>

## <a name="remarks"></a>Uwagi

`Shift`Wartość jest zawsze modulo 64, tak więc, na przykład, jeśli wywołasz `__shiftright128(0, 1, 64)` , funkcja zmieni górną część `0` bitów w prawo i zwróci niską część, `0` a nie `1` jako nieoczekiwaną.

## <a name="example"></a>Przykład

Aby zapoznać się z przykładem, zobacz [__shiftleft128](../intrinsics/shiftleft128.md).

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[__shiftleft128](../intrinsics/shiftleft128.md)\
[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)
