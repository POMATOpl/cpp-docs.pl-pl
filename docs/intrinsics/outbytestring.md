---
description: 'Dowiedz się więcej na temat: __outbytestring'
title: __outbytestring
ms.date: 09/02/2019
f1_keywords:
- __outbytestring
helpviewer_keywords:
- rep outsb instruction
- __outbytestring intrinsic
- outsb instruction
ms.assetid: c9150661-9c18-427f-bae8-710bba6ed78c
ms.openlocfilehash: feadb0b4275e370de88bfc04c8a10f90c41d0844
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222427"
---
# <a name="__outbytestring"></a>__outbytestring

**Specyficzne dla firmy Microsoft**

Generuje `rep outsb` instrukcję, która wysyła pierwsze `Count` bajty danych wskazywane przez `Buffer` port określony przez `Port` .

## <a name="syntax"></a>Składnia

```C
void __outbytestring(
   unsigned short Port,
   unsigned char* Buffer,
   unsigned long Count
);
```

### <a name="parameters"></a>Parametry

*Przewożąc*\
podczas Port, do którego mają zostać wysłane dane.

*Buforu*\
podczas Dane, które mają zostać wysłane przez określony port.

*Liczbą*\
podczas Liczba bajtów danych do wysłania.

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`__outbytestring`|x86, x64|

**Plik nagłówka**\<intrin.h>

## <a name="remarks"></a>Uwagi

Ta procedura jest dostępna tylko jako wewnętrzna.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)
