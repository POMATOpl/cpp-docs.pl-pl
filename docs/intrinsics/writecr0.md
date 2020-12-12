---
description: 'Dowiedz się więcej na temat: __writecr0'
title: __writecr0
ms.date: 09/02/2019
f1_keywords:
- _writecr0
helpviewer_keywords:
- _writecr0 intrinsic
ms.assetid: a143d08d-0333-4e1b-91b4-4acb2ae91b5a
ms.openlocfilehash: 9a4cf4f30b5663b875ca27416b698eb8477938d4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97313102"
---
# <a name="__writecr0"></a>__writecr0

**Specyficzne dla firmy Microsoft**

Zapisuje wartość `Data` w rejestrze CR0.

## <a name="syntax"></a>Składnia

```C
void writecr0(
   unsigned __int64 Data
);
```

### <a name="parameters"></a>Parametry

*Data*\
podczas Wartość, która ma zostać zapisana w rejestrze CR0.

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|
|---------------|------------------|
|`__writecr0`|x86, x64|

**Plik nagłówka**\<intrin.h>

## <a name="remarks"></a>Uwagi

Ten element wewnętrzny jest dostępny tylko w trybie jądra, a procedura jest dostępna tylko jako wewnętrzna.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)
