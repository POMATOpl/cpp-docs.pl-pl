---
description: 'Dowiedz się więcej na temat: __readgsbyte, __readgsdword, __readgsqword __readgsword'
title: __readgsbyte, __readgsdword, __readgsqword, __readgsword
ms.date: 09/02/2019
f1_keywords:
- __readgsbyte
- __readgsdword
- __readgsqword
- __readgsword
helpviewer_keywords:
- __readgsword intrinsic
- __readgsdword intrinsic
- __readgsqword intrinsic
- __readgsbyte intrinsic
ms.assetid: f822632d-854c-4558-a71b-cdfc3eea2236
ms.openlocfilehash: fb1faf0e785f0d0983d7d3611e68a7515298e61c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340973"
---
# <a name="__readgsbyte-__readgsdword-__readgsqword-__readgsword"></a>__readgsbyte, __readgsdword, __readgsqword, __readgsword

**Specyficzne dla firmy Microsoft**

Odczytaj pamięć z lokalizacji określonej przez przesunięcie względem początku segmentu GS.

## <a name="syntax"></a>Składnia

```C
unsigned char __readgsbyte(
   unsigned long Offset
);
unsigned short __readgsword(
   unsigned long Offset
);
unsigned long __readgsdword(
   unsigned long Offset
);
unsigned __int64 __readgsqword(
   unsigned long Offset
);
```

### <a name="parameters"></a>Parametry

*Przesunięcie*\
podczas Przesunięcie od początku, z którego `GS` ma zostać odczytane.

## <a name="return-value"></a>Wartość zwracana

Zawartość pamięci, słowo, podwójne słowo lub quadword (wskazywane przez nazwę funkcji o nazwie) w lokalizacji `GS:[Offset]` .

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`__readgsbyte`|x64|
|`__readgsdword`|x64|
|`__readgsqword`|x64|
|`__readgsword`|x64|

**Plik nagłówka**\<intrin.h>

## <a name="remarks"></a>Uwagi

Te procedury są dostępne tylko jako wewnętrznie.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[__writegsbyte, \_ _writegsdword, \_ _writegsqword \_ _writegsword](../intrinsics/writegsbyte-writegsdword-writegsqword-writegsword.md)\
[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)
