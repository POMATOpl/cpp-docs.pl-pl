---
description: 'Dowiedz się więcej na temat: _CrtSetReportFile'
title: _CrtSetReportFile
ms.date: 11/04/2016
api_name:
- _CrtSetReportFile
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- CrtSetReportFile
- _CrtSetReportFile
helpviewer_keywords:
- CrtSetReportFile function
- _CrtSetReportFile function
ms.assetid: 3126537e-511b-44af-9c1c-0605265eabc4
ms.openlocfilehash: 6b22a76a1a168239210a9f2b93d5cf17d073ec51
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97206958"
---
# <a name="_crtsetreportfile"></a>_CrtSetReportFile

Po użyciu [_CrtSetReportMode](crtsetreportmode.md) do określenia **_CRTDBG_MODE_FILE**, możesz określić uchwyt pliku, aby otrzymać tekst komunikatu. **_CrtSetReportFile** jest również używany przez [_CrtDbgReport, _CrtDbgReportW](crtdbgreport-crtdbgreportw.md) do określania miejsca docelowego tekstu (tylko wersja do debugowania).

## <a name="syntax"></a>Składnia

```C
_HFILE _CrtSetReportFile(
   int reportType,
   _HFILE reportFile
);
```

### <a name="parameters"></a>Parametry

*reportType*<br/>
Typ raportu: **_CRT_WARN**, **_CRT_ERROR** i **_CRT_ASSERT**.

*reportFile*<br/>
Nowy plik raportu dla elementu *reportType*.

## <a name="return-value"></a>Wartość zwracana

Po pomyślnym zakończeniu **_CrtSetReportFile** zwraca poprzedni plik raportu zdefiniowany dla typu raportu określonego w elemencie *reportType*. W przypadku przekazaniu nieprawidłowej wartości dla elementu *reportType* ta funkcja wywołuje procedurę obsługi nieprawidłowego parametru, zgodnie z opisem w [walidacji parametru](../../c-runtime-library/parameter-validation.md). Jeśli wykonanie może być kontynuowane, **errno** jest ustawiona na **EINVAL** , a funkcja zwraca **_CRTDBG_HFILE_ERROR**. Aby uzyskać więcej informacji, zobacz [errno, _doserrno, _sys_errlist i _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Uwagi

**_CrtSetReportFile** jest używana z funkcją [_CrtSetReportMode](crtsetreportmode.md) do definiowania miejsca docelowego lub lokalizacji docelowych dla określonego typu raportu generowanego przez **_CrtDbgReport**. Po wywołaniu **_CrtSetReportMode** , aby przypisać **_CRTDBG_MODE_FILE** tryb raportowania dla określonego typu raportu, **_CrtSetReportFile** powinien następnie zostać wywołana w celu zdefiniowania określonego pliku lub strumienia, który ma być używany jako miejsce docelowe. Gdy [_DEBUG](../../c-runtime-library/debug.md) nie jest zdefiniowany, wywołania do **_CrtSetReportFile** są usuwane podczas przetwarzania wstępnego.

Na poniższej liście przedstawiono dostępne opcje *reportFile* i wyniki działania **_CrtDbgReport**. Te opcje są zdefiniowane jako flagi bitowe w CRTDBG. h.

- **Dojście do pliku**

   Dojście do pliku, który będzie miejscem docelowym dla komunikatów. Nie podjęto próby zweryfikowania ważności dojścia. Musisz otworzyć i zamknąć uchwyt do pliku. Na przykład:

   ```C
   HANDLE hLogFile;
   hLogFile = CreateFile("c:\\log.txt", GENERIC_WRITE,
      FILE_SHARE_WRITE, NULL, CREATE_ALWAYS,
      FILE_ATTRIBUTE_NORMAL, NULL);
   _CrtSetReportMode(_CRT_WARN, _CRTDBG_MODE_FILE);
   _CrtSetReportFile(_CRT_WARN, hLogFile);

   _RPT0(_CRT_WARN,"file message\n");
   CloseHandle(hLogFile);
   ```

- **_CRTDBG_FILE_STDERR**

   Zapisuje komunikat do **stderr**, który można przekierować w następujący sposób:

   ```C
   freopen( "c:\\log2.txt", "w", stderr);
   _CrtSetReportMode(_CRT_ERROR, _CRTDBG_MODE_FILE);
   _CrtSetReportFile(_CRT_ERROR, _CRTDBG_FILE_STDERR);

   _RPT0(_CRT_ERROR,"1st message\n");
   ```

- **_CRTDBG_FILE_STDOUT**

   Zapisuje komunikat w strumieniu **stdout**, który można przekierować.

- **_CRTDBG_REPORT_FILE**

   Zwraca bieżący tryb raportu.

Plik raportu używany przez każdy typ raportu można kontrolować osobno. Na przykład można określić, że element *reporttype* **_CRT_ERROR** być raportowany do **stderr**, podczas gdy *raport typu raportu* **_CRT_ASSERT** być raportowany do dojścia do pliku lub strumienia zdefiniowanego przez użytkownika.

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|Opcjonalny nagłówek|
|-------------|---------------------|---------------------|
|**_CrtSetReportFile**|\<crtdbg.h>|\<errno.h>|

Konsola nie jest obsługiwana w aplikacjach platforma uniwersalna systemu Windows (platformy UWP). Standardowe uchwyty strumienia, które są skojarzone z konsolą, **stdin**, **stdout** i **stderr**, muszą zostać przekierowane przed użyciem funkcji języka C w aplikacjach platformy UWP. Aby uzyskać więcej informacji o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

**Biblioteki:** Debuguj tylko wersje [funkcji biblioteki CRT](../../c-runtime-library/crt-library-features.md) .

## <a name="see-also"></a>Zobacz też

[Procedury debugowania](../../c-runtime-library/debug-routines.md)<br/>
