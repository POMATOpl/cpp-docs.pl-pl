---
description: 'Dowiedz się więcej na temat: _initterm, _initterm_e'
title: _initterm, _initterm_e
ms.date: 11/04/2016
api_name:
- _initterm_e
- _initterm
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-runtime-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _initterm_e
- initterm
- _initterm
- initterm_e
helpviewer_keywords:
- initterm function
- initterm_e function
- _initterm function
- _initterm_e function
ms.assetid: 85131efe-c747-429a-8897-bcdedb000172
ms.openlocfilehash: c9686504ae39f5aad1678430f4e4ad0054aabc36
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97296397"
---
# <a name="_initterm-_initterm_e"></a>_initterm, _initterm_e

Metody wewnętrzne, które przeprowadzą tabelę wskaźników funkcji i inicjują je.

Pierwszy wskaźnik jest początkową lokalizacją w tabeli, a drugi wskaźnik jest lokalizacją końcową.

## <a name="syntax"></a>Składnia

```C
void __cdecl _initterm(
   PVFV *,
   PVFV *
);

int __cdecl _initterm_e(
   PVFV *,
   PVFV *
);
```

## <a name="return-value"></a>Wartość zwracana

Niezerowy kod błędu, jeśli Inicjalizacja nie powiedzie się i zgłosi błąd; 0, jeśli nie wystąpi błąd.

## <a name="remarks"></a>Uwagi

Te metody są wywoływane tylko wewnętrznie podczas inicjowania programu C++. Nie wywołuj tych metod w programie.

Gdy te metody przeprowadzą tabelę wpisów funkcji, pomijają wpisy o **wartości null** i kontynuują.

## <a name="see-also"></a>Zobacz też

[Alfabetyczne zestawienie funkcji](crt-alphabetical-function-reference.md)<br/>
