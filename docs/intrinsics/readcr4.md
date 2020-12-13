---
description: 'Dowiedz się więcej na temat: __readcr4'
title: __readcr4
ms.date: 09/02/2019
f1_keywords:
- __readcr4
helpviewer_keywords:
- __readcr4 intrinsic
ms.assetid: b841a27b-fe0d-4ee9-b76b-f91d3eb061fa
ms.openlocfilehash: 3e1d3999f488d4b7c155fd2c475a2070f29f6cda
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341038"
---
# <a name="__readcr4"></a>__readcr4

**Specyficzne dla firmy Microsoft**

Odczytuje rejestr CR4 i zwraca jego wartość.

## <a name="syntax"></a>Składnia

```C
unsigned __int64 __readcr4(void);
```

## <a name="return-value"></a>Wartość zwracana

Wartość w rejestrze CR4.

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`__readcr4`|x86, x64|

**Plik nagłówka**\<intrin.h>

## <a name="remarks"></a>Uwagi

Element wewnętrzny jest dostępny tylko w trybie jądra, a procedura jest dostępna tylko jako wewnętrzna.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)
