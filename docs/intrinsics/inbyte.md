---
description: 'Dowiedz się więcej na temat: __inbyte'
title: __inbyte
ms.date: 09/02/2019
f1_keywords:
- __inbyte
- __inbyte_cpp
helpviewer_keywords:
- in instruction
- __inbyte intrinsic
ms.assetid: 03b61799-2a08-474d-adc4-2cbf7c81a4d5
ms.openlocfilehash: 77cc1cfb792ffa2f6aef9879820e644372895193
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337016"
---
# <a name="__inbyte"></a>__inbyte

**Specyficzne dla firmy Microsoft**

Generuje `in` instrukcję, zwracając pojedynczy bajt odczytany z portu określonego przez `Port` .

## <a name="syntax"></a>Składnia

```C
unsigned char __inbyte(
   unsigned short Port
);
```

### <a name="parameters"></a>Parametry

*Przewożąc*\
podczas Port, z którego ma zostać odczytany.

## <a name="return-value"></a>Wartość zwracana

Bajt odczytany z określonego portu.

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`__inbyte`|x86, x64|

**Plik nagłówka**\<intrin.h>

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="remarks"></a>Uwagi

Ta procedura jest dostępna tylko jako wewnętrzna.

## <a name="see-also"></a>Zobacz też

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)
