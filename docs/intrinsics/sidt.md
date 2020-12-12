---
description: 'Dowiedz się więcej na temat: __sidt'
title: __sidt
ms.date: 09/02/2019
f1_keywords:
- __sidt
helpviewer_keywords:
- sidt instruction
- __sidt intrinsic
ms.assetid: 01e83d14-6e63-4dea-8f64-5a0339d69641
ms.openlocfilehash: 075351bc10981dd8453381e9ce9393a046dfd884
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97306966"
---
# <a name="__sidt"></a>__sidt

**Specyficzne dla firmy Microsoft**

Przechowuje wartość rejestru tabeli deskryptorów przerwań (IDTR) w określonej lokalizacji pamięci.

## <a name="syntax"></a>Składnia

```C
void __sidt(void * Destination);
```

### <a name="parameters"></a>Parametry

*Punktu*\
podczas Wskaźnik do lokalizacji pamięci, w której jest przechowywany IDTR.

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`__sidt`|x86, x64|

**Plik nagłówka**\<intrin.h>

## <a name="remarks"></a>Uwagi

`__sidt`Funkcja jest równoważna z `SIDT` instrukcją maszyny. Aby uzyskać więcej informacji, Wyszukaj dokument "Podręcznik Intel Architecture Software Developer, Tom 2: odwołanie do zestawu instrukcji" w witrynie [Intel Corporation](https://software.intel.com/articles/intel-sdm) .

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)\
[__lidt](../intrinsics/lidt.md)
