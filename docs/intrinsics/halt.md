---
description: 'Dowiedz się więcej na temat: __halt'
title: __halt
ms.date: 09/02/2019
f1_keywords:
- __halt
- __halt_cpp
helpviewer_keywords:
- __halt intrinsic
- HLT instruction
ms.assetid: a074f44a-101c-45a5-8a5e-cfd223c34002
ms.openlocfilehash: e38478b14b59c910e6d6ac12f9cb69fa369e3459
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336973"
---
# <a name="__halt"></a>__halt

**Specyficzne dla firmy Microsoft**

Zatrzymuje mikroprocesor do momentu włączenia włączonego przerwania, przerwania niemaskowanego (NMI) lub zresetowania.

## <a name="syntax"></a>Składnia

```C
void __halt( void );
```

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`__halt`|x86, x64|

**Plik nagłówka**\<intrin.h>

## <a name="remarks"></a>Uwagi

`__halt`Funkcja jest równoważna z `HLT` instrukcją Machine i jest dostępna tylko w trybie jądra. Aby uzyskać więcej informacji, Wyszukaj dokument "Podręcznik Intel Architecture Software Developer, Tom 2: odwołanie do zestawu instrukcji" w witrynie [Intel Corporation](https://software.intel.com/articles/intel-sdm) .

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)
