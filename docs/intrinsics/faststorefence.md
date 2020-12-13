---
description: 'Dowiedz się więcej na temat: __faststorefence'
title: __faststorefence
ms.date: 09/02/2019
f1_keywords:
- __faststorefence_cpp
- __faststorefence
helpviewer_keywords:
- __faststorefence intrinsic
- sfence instruction
ms.assetid: 6c6eb973-3cf0-4306-b3af-cfde9b0210a5
ms.openlocfilehash: f12d16232e034c562f564d851da08c62cb59c34f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337028"
---
# <a name="__faststorefence"></a>__faststorefence

**Specyficzne dla firmy Microsoft**

Gwarantuje, że każde poprzednie odwołanie do pamięci, łącznie z odwołaniami do pamięci ładowania i zapisu, jest widoczne globalnie przed wszelkimi kolejnymi odwołaniami do pamięci.

## <a name="syntax"></a>Składnia

```C
void __faststorefence();
```

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`__faststorefence`|x64|

**Plik nagłówka**\<intrin.h>

## <a name="remarks"></a>Uwagi

Generuje pełną sekwencję instrukcji z barierą pamięci, która gwarantuje, że operacje ładowania i przechowywania są wydawane przed kontynuowaniem wykonywania. Efekt jest porównywalny z szybkością, ale większą niż `_mm_mfence` wewnętrzna na wszystkich platformach x64.

Na platformie AMD64 ta procedura generuje instrukcję, która jest szybszym ogrodzeniem magazynu niż `sfence` instrukcja. W przypadku kodu o kluczowym znaczeniu należy używać tego wewnętrznego zamiast `_mm_sfence` tylko na platformach amd64. Na platformach Intel x64 `_mm_sfence` instrukcje są szybsze.

Ta procedura jest dostępna tylko jako wewnętrzna.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)
