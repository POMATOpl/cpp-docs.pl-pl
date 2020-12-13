---
description: 'Dowiedz się więcej na temat: __svm_clgi'
title: __svm_clgi
ms.date: 09/02/2019
f1_keywords:
- __svm_clgi
helpviewer_keywords:
- CLGI instruction
- __svm_clgi intrinsic
ms.assetid: 6640f5ab-9472-46f9-a042-e15c4f1ff858
ms.openlocfilehash: d0b372e28b0b119d3576dd87b34f1edf883f1337
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336866"
---
# <a name="__svm_clgi"></a>__svm_clgi

**Specyficzne dla firmy Microsoft**

Czyści flagę globalnego przerwania.

## <a name="syntax"></a>Składnia

```C
void __svm_clgi( void );
```

## <a name="remarks"></a>Uwagi

`__svm_clgi`Funkcja jest równoważna z `CLGI` instrukcją maszyny. Flaga globalnego przerwania określa, czy mikroprocesor ignoruje, opóźnia lub obsługuje przerwania, ze względu na zdarzenia, takie jak ukończenie operacji we/wy, alert dotyczący temperatury sprzętu lub wyjątek debugowania.

Ta funkcja obsługuje interakcję z monitorem maszyny wirtualnej hosta z systemem operacyjnym gościa i jego aplikacjami. Aby uzyskać więcej informacji, wyszukaj frazę "rozgłośnuje programista architektury AMD64 2: Programowanie systemu" w witrynie [AMD Corporation](https://developer.amd.com/resources/developer-guides-manuals/) .

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`__svm_clgi`|x86, x64|

**Plik nagłówka**\<intrin.h>

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)\
[__svm_stgi](../intrinsics/svm-stgi.md)
