---
description: 'Dowiedz się więcej na temat: __svm_stgi'
title: __svm_stgi
ms.date: 09/02/2019
f1_keywords:
- __svm_stgi
helpviewer_keywords:
- __svm_stgi intrinsic
- STGI instruction
ms.assetid: 96488da4-5587-4e99-8674-627a9e51be84
ms.openlocfilehash: 8a6c7c221ed0bbf71a00685e8a0545818dd507a1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336849"
---
# <a name="__svm_stgi"></a>__svm_stgi

**Specyficzne dla firmy Microsoft**

Ustawia flagę globalnego przerwania.

## <a name="syntax"></a>Składnia

```C
void __svm_stgi(void);
```

## <a name="remarks"></a>Uwagi

`__svm_stgi`Funkcja jest równoważna z `STGI` instrukcją maszyny. Flaga globalnego przerwania określa, czy mikroprocesor ignoruje, opóźnia lub obsługuje przerwania, ze względu na zdarzenia, takie jak ukończenie operacji we/wy, alert dotyczący temperatury sprzętu lub wyjątek debugowania.

Ta funkcja obsługuje interakcję z monitorem maszyny wirtualnej hosta z systemem operacyjnym gościa i jego aplikacjami. Aby uzyskać więcej informacji, wyszukaj frazę "rozgłośnuje programista architektury AMD64 2: Programowanie systemu" w witrynie [AMD Corporation](https://developer.amd.com/resources/developer-guides-manuals/) .

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`__svm_stgi`|x86, x64|

**Plik nagłówka**\<intrin.h>

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)\
[__svm_clgi](../intrinsics/svm-clgi.md)
