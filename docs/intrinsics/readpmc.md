---
description: 'Dowiedz się więcej na temat: __readpmc'
title: __readpmc
ms.date: 09/02/2019
f1_keywords:
- __readpmc
helpviewer_keywords:
- Read Performance Monitoring Counters instruction
- __readpmc intrinsic
- rdpmc instruction
ms.assetid: 14ed45a6-28b6-4635-8437-a597c04b43d4
ms.openlocfilehash: ceff8522d4895f69a47cf429e59d267c671e3a66
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294135"
---
# <a name="__readpmc"></a>__readpmc

**Specyficzne dla firmy Microsoft**

Generuje `rdpmc` instrukcję, która odczytuje licznik monitorowania wydajności określony przez *licznik*.

## <a name="syntax"></a>Składnia

```C
unsigned __int64 __readpmc(
   unsigned long counter
);
```

### <a name="parameters"></a>Parametry

*przeciw*\
podczas Licznik wydajności, który ma zostać odczytany.

## <a name="return-value"></a>Wartość zwracana

Wartość określonego licznika wydajności.

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`__readpmc`|x86, x64|

**Plik nagłówka**\<intrin.h>

## <a name="remarks"></a>Uwagi

Element wewnętrzny jest dostępny tylko w trybie jądra, a procedura jest dostępna tylko jako wewnętrzna.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)
