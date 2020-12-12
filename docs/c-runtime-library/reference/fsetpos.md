---
description: 'Dowiedz się więcej na temat: fsetpos'
title: fsetpos
ms.date: 4/2/2020
api_name:
- fsetpos
- _o_fsetpos
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
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- fsetpos
helpviewer_keywords:
- streams, setting position indicators
- fsetpos function
ms.assetid: 6d19ff48-1a2b-47b3-9f23-ed0a47b5a46e
ms.openlocfilehash: e8259bcf4dba951bf6603fb5d4984db6ece0e266
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97114224"
---
# <a name="fsetpos"></a>fsetpos

Ustawia wskaźnik pozycji strumienia.

## <a name="syntax"></a>Składnia

```C
int fsetpos(
   FILE *stream,
   const fpos_t *pos
);
```

### <a name="parameters"></a>Parametry

*produkcyjne*<br/>
Wskaźnik do struktury **pliku** .

*Terminal*<br/>
Miejsce — magazyn wskaźnika.

## <a name="return-value"></a>Wartość zwracana

W przypadku powodzenia funkcja **fsetpos** zwraca wartość 0. W przypadku niepowodzenia funkcja zwraca wartość różną od zera i ustawia **errno** na jedną z następujących stałych manifestu (zdefiniowanej w errno. H): **EBADF**, co oznacza, że plik nie jest dostępny lub obiekt, do *którego wskazuje,* że nie jest prawidłową strukturą pliku; lub **EINVAL**, co oznacza, że przekazano nieprawidłową wartość *strumienia* lub *punktu sprzedaży* . Jeśli przeszedł nieprawidłowy parametr, te funkcje wywołują procedurę obsługi nieprawidłowego parametru, zgodnie z opisem w [walidacji parametru](../../c-runtime-library/parameter-validation.md).

Aby uzyskać więcej informacji na temat tych i innych kodów powrotu, zobacz [_doserrno, errno, _sys_errlist i _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) .

## <a name="remarks"></a>Uwagi

Funkcja **fsetpos** ustawia wskaźnik położenia plików dla *strumienia* do wartości *punktu sprzedaży*, która jest uzyskiwana we wcześniejszej wywołaniu **fgetpos** względem *strumienia*. Funkcja czyści wskaźnik końca pliku i cofa wszystkie efekty [ungetc —](ungetc-ungetwc.md) w *strumieniu*. Po wywołaniu **fsetpos** kolejna operacja na *strumieniu* może być wartością wejściową lub wyjściową.

Domyślnie globalny stan tej funkcji jest objęty zakresem aplikacji. Aby to zmienić, zobacz [stan globalny w CRT](../global-state.md).

## <a name="requirements"></a>Wymagania

|Funkcja|Wymagany nagłówek|
|--------------|---------------------|
|**fsetpos**|\<stdio.h>|

Aby uzyskać dodatkowe informacje o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Przykład

Zobacz przykład dla [fgetpos](fgetpos.md).

## <a name="see-also"></a>Zobacz też

[We/Wy strumienia](../../c-runtime-library/stream-i-o.md)<br/>
[fgetpos](fgetpos.md)<br/>
