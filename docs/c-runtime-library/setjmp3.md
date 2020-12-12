---
description: 'Dowiedz się więcej na temat: _setjmp3'
title: _setjmp3
ms.date: 11/04/2016
api_name:
- _setjmp3
api_location:
- msvcrt.dll
- msvcr90.dll
- msvcr110.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcr120.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- setjmp3
- _setjmp3
helpviewer_keywords:
- _setjmp3 function
- setjmp3 function
ms.assetid: 6129c2f3-8bac-4fdb-a827-44e1eebba500
ms.openlocfilehash: 07a84601a6f57eca3e7dc71638a964428579b1c7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97277066"
---
# <a name="_setjmp3"></a>_setjmp3

Wewnętrzna funkcja CRT. Nowa implementacja `setjmp` funkcji.

## <a name="syntax"></a>Składnia

```
int _setjmp3(
   OUT jmp_buf env,
   int count,
   (optional parameters)
);
```

#### <a name="parameters"></a>Parametry

*kopert*<br/>
określoną Adres buforu do przechowywania informacji o stanie.

*liczbą*<br/>
podczas Liczba dodatkowych `DWORD` informacji, które są przechowywane w `optional parameters` .

*Parametry opcjonalne*<br/>
podczas Dodatkowe dane wypychane przez `setjmp` wewnętrznie. Pierwszy `DWORD` to wskaźnik funkcji, który jest używany do odwinięcia dodatkowych danych i powrotu do nietrwałego stanu rejestru. Drugi `DWORD` to poziom try, który ma zostać przywrócony. Wszelkie dalsze dane są zapisywane w ogólnej tablicy danych w `jmp_buf` .

## <a name="return-value"></a>Wartość zwracana

Zawsze zwraca wartość 0.

## <a name="remarks"></a>Uwagi

Nie należy używać tej funkcji w programie C++. Jest to funkcja wewnętrzna, która nie obsługuje języka C++. Aby uzyskać więcej informacji o sposobach korzystania z programu `setjmp` , zobacz [using setjmp/longjmp](../cpp/using-setjmp-longjmp.md).

## <a name="requirements"></a>Wymagania

## <a name="see-also"></a>Zobacz też

[Alfabetyczne zestawienie funkcji](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[setjmp](../c-runtime-library/reference/setjmp.md)
