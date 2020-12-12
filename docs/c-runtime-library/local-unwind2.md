---
description: 'Dowiedz się więcej na temat: _local_unwind2'
title: _local_unwind2
ms.date: 11/04/2016
api_name:
- _local_unwind2
api_location:
- msvcr110_clr0400.dll
- msvcrt.dll
- msvcr100.dll
- msvcr110.dll
- msvcr80.dll
- msvcr90.dll
- msvcr120.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _local_unwind2
- local_unwind2
helpviewer_keywords:
- _local_unwind2 function
- local_unwind2 function
ms.assetid: 44f1fa82-e01e-490f-a6e6-18fc6811c28c
ms.openlocfilehash: b2e3ca2f792abaa3ace54b25131d82c21aadf972
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97246412"
---
# <a name="_local_unwind2"></a>_local_unwind2

Wewnętrzna funkcja CRT. Uruchamia wszystkie programy obsługi zakończenia, które są wymienione w wskazanej tabeli zakresów.

## <a name="syntax"></a>Składnia

```cpp
void _local_unwind2(
   PEXCEPTION_REGISTRATION xr,
   int stop
);
```

#### <a name="parameters"></a>Parametry

*XR*<br/>
podczas Rekord rejestracji skojarzony z jedną tabelą zakresów.

*komunikat*<br/>
podczas Poziom leksykalny wskazujący, gdzie `_local_unwind2` powinien zostać zatrzymany.

## <a name="remarks"></a>Uwagi

Ta metoda jest używana tylko przez środowisko uruchomieniowe. Nie wywołuj metody w kodzie.

Gdy ta metoda wykonuje programy obsługi zakończenia, rozpocznie się na bieżącym poziomie leksykalnym i działa jak na poziomach leksykalnych do momentu osiągnięcia poziomu wskazanego przez `stop` . Nie wykonuje obsługi zakończenia na poziomie wskazywanym przez `stop` .

## <a name="see-also"></a>Zobacz też

[Alfabetyczne zestawienie funkcji](../c-runtime-library/reference/crt-alphabetical-function-reference.md)
