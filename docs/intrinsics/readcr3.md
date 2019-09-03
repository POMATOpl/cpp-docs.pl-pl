---
title: __readcr3
ms.date: 09/02/2019
f1_keywords:
- __readcr3
helpviewer_keywords:
- __readcr3 intrinsic
ms.assetid: e24392c3-cad7-4788-8f31-94bf2e9e0053
ms.openlocfilehash: b03ff46fabc99839d9c0bbd5c72e1b76d25814c0
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/03/2019
ms.locfileid: "70221268"
---
# <a name="__readcr3"></a>__readcr3

**Microsoft Specific**

Odczytuje rejestr CR3 i zwraca jego wartość.

## <a name="syntax"></a>Składnia

```C
unsigned __int64 __readcr3(void);
```

## <a name="return-value"></a>Wartość zwracana

Wartość w rejestrze CR3.

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`__readcr3`|x86, x64|

**Plik nagłówka** \<intrin. h >

## <a name="remarks"></a>Uwagi

Element wewnętrzny jest dostępny tylko w trybie jądra, a procedura jest dostępna tylko jako wewnętrzna.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz także

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)
