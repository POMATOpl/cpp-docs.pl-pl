---
description: 'Dowiedz się więcej na temat: __writecr8'
title: __writecr8
ms.date: 09/02/2019
f1_keywords:
- _writecr8
helpviewer_keywords:
- _writecr8 intrinsic
ms.assetid: 6f8bd632-dddb-4335-971e-1acee24aa2b9
ms.openlocfilehash: b9c642d92cd5d5cfb861dbff3d159b5c98a1aa5d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331896"
---
# <a name="__writecr8"></a>__writecr8

**Specyficzne dla firmy Microsoft**

Zapisuje wartość `Data` w rejestrze CR8.

## <a name="syntax"></a>Składnia

```C
void writecr8(
   unsigned __int64 Data
);
```

### <a name="parameters"></a>Parametry

*Data*\
podczas Wartość, która ma zostać zapisana w rejestrze CR8.

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`__writecr8`|x64|

**Plik nagłówka**\<intrin.h>

## <a name="remarks"></a>Uwagi

Element `__writecr8` wewnętrzny jest dostępny tylko w trybie jądra, a procedura jest dostępna tylko jako wewnętrzna.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)
