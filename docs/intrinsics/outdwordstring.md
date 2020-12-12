---
description: 'Dowiedz się więcej na temat: __outdwordstring'
title: __outdwordstring
ms.date: 09/02/2019
f1_keywords:
- __outdwordstring
helpviewer_keywords:
- outsd instruction
- __outdwordstring intrinsic
- rep outsd instruction
ms.assetid: 55b31a65-aab7-4b5c-b61d-d9e2fb0c497a
ms.openlocfilehash: 3fbba7dd128666b591305326695e656befd9cada
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97180397"
---
# <a name="__outdwordstring"></a>__outdwordstring

**Specyficzne dla firmy Microsoft**

Generuje `rep outsd` instrukcję, która wysyła `Count` doublewords, rozpoczynając od `Buffer` portu we/wy określonego przez `Port` .

## <a name="syntax"></a>Składnia

```C
void __outdwordstring(
   unsigned short Port,
   unsigned long* Buffer,
   unsigned long Count
);
```

### <a name="parameters"></a>Parametry

*Przewożąc*\
podczas Port, do którego mają zostać wysłane dane.

*Buforu*\
podczas Wskaźnik do danych, które mają zostać wysłane przez określony port.

*Liczbą*\
podczas Liczba doublewords do wysłania.

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`__outdwordstring`|x86, x64|

**Plik nagłówka**\<intrin.h>

## <a name="remarks"></a>Uwagi

Ta procedura jest dostępna tylko jako wewnętrzna.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)
