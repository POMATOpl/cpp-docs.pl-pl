---
title: "_chdir —, _wchdir — | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wchdir
- _chdir
apilocation:
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- tchdir
- _chdir
- _wchdir
- _tchdir
- wchdir
dev_langs: C++
helpviewer_keywords:
- _tchdir function
- _chdir function
- _wchdir function
- tchdir function
- wchdir function
- chdir function
- directories [C++], changing
ms.assetid: 85e9393b-62ac-45d5-ab2a-fa2217f6152e
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 343121b4484f97e0778098991c71731ed3c6ef2e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="chdir-wchdir"></a>_chdir, _wchdir
Zmienia bieżący katalog roboczy.  
  
## <a name="syntax"></a>Składnia  
  
```  
int _chdir(   
   const char *dirname   
);  
int _wchdir(   
   const wchar_t *dirname   
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dirname`  
 Ścieżka katalogu roboczego nowych.  
  
## <a name="return-value"></a>Wartość zwracana  
 Funkcje te zwracają wartość 0 w przypadku powodzenia. Zwracana wartość -1 oznacza błąd. Jeśli nie można odnaleźć określonej ścieżki, `errno` ma ustawioną wartość `ENOENT`. Jeśli `dirname` ma wartość NULL, program obsługi nieprawidłowych parametrów zostanie wywołany, zgodnie z opisem w [sprawdzanie poprawności parametru](../../c-runtime-library/parameter-validation.md). Jeśli jest dozwolone wykonywanie, aby kontynuować, `errno` ustawiono `EINVAL` i funkcja zwraca wartość -1.  
  
## <a name="remarks"></a>Uwagi  
 `_chdir` Funkcja zmienia bieżący katalog roboczy na katalog określony przez `dirname`. `dirname` Parametru musi odwoływać się do istniejącego katalogu. Tej funkcji można zmienić bieżący katalog roboczy na dowolnym dysku. Jeśli określono litera dysku w `dirname`, również zmiany domyślną literę dysku. Na przykład A to litera dysku domyślne \BIN jest bieżący katalog roboczy, następujące wywołanie zmiany bieżącego katalogu roboczego na dysku C i ustanawia C jako nowego dysku domyślne:  
  
```  
_chdir("c:\\temp");  
```  
  
 Jeśli używasz opcjonalne ukośnika odwrotnego (`\`) w ścieżkach, należy umieścić dwa razy (`\\`) ciągu C do reprezentowania pojedynczego ukośnika odwrotnego (`\`).  
  
 `_wchdir`jest to wersja znaków dwubajtowych `_chdir`; `dirname` argument `_wchdir` jest ciągiem znaków dwubajtowych`. _wchdir` i `_chdir` zachowują się tak samo w przeciwnym razie wartość.  
  
### <a name="generic-text-routine-mapping"></a>Rutynowe mapowanie — zwykły tekst:  
  
|Procedura tchar.h|_UNICODE i _MBCS niezdefiniowane|_MBCS zdefiniowano|_UNICODE zdefiniowano|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tchdir`|`_chdir`|`_chdir`|`_wchdir`|  
  
## <a name="requirements"></a>Wymagania  
  
|Procedura|Wymagany nagłówek|Opcjonalne nagłówki|  
|-------------|---------------------|---------------------|  
|`_chdir`|\<Direct.h >|\<errno.h >|  
|`_wchdir`|\<Direct.h > lub \<wchar.h >|\<errno.h >|  
  
 Aby uzyskać więcej informacji o zgodności, zobacz [zgodności](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Przykład  
  
```  
// crt_chdir.c  
// arguments: C:\WINDOWS  
  
/* This program uses the _chdir function to verify  
   that a given directory exists. */  
  
#include <direct.h>  
#include <stdio.h>  
#include <stdlib.h>  
#include <errno.h>  
  
int main( int argc, char *argv[] )  
{  
  
   if(_chdir( argv[1] ) )  
   {  
      switch (errno)  
      {  
      case ENOENT:  
         printf( "Unable to locate the directory: %s\n", argv[1] );  
         break;  
      case EINVAL:  
         printf( "Invalid buffer.\n");  
         break;  
      default:  
         printf( "Unknown error.\n");  
      }  
   }  
   else  
      system( "dir *.exe");  
}  
```  
  
```Output  
Volume in drive C has no label.  
 Volume Serial Number is 2018-08A1  
  
 Directory of c:\windows  
  
08/29/2002  04:00 AM         1,004,032 explorer.exe  
12/17/2002  04:43 PM            10,752 hh.exe  
03/03/2003  09:24 AM            33,792 ieuninst.exe  
10/29/1998  04:45 PM           306,688 IsUninst.exe  
08/29/2002  04:00 AM            66,048 NOTEPAD.EXE  
03/03/2003  09:24 AM            33,792 Q330994.exe  
08/29/2002  04:00 AM           134,144 regedit.exe  
02/28/2003  06:26 PM            46,352 setdebug.exe  
08/29/2002  04:00 AM            15,360 TASKMAN.EXE  
08/29/2002  04:00 AM            49,680 twunk_16.exe  
08/29/2002  04:00 AM            25,600 twunk_32.exe  
08/29/2002  04:00 AM           256,192 winhelp.exe  
08/29/2002  04:00 AM           266,752 winhlp32.exe  
              13 File(s)      2,249,184 bytes  
               0 Dir(s)  67,326,029,824 bytes free  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Kontrola katalogu](../../c-runtime-library/directory-control.md)   
 [_mkdir —, _wmkdir —](../../c-runtime-library/reference/mkdir-wmkdir.md)   
 [_rmdir —, _wrmdir —](../../c-runtime-library/reference/rmdir-wrmdir.md)   
 [System, _wsystem —](../../c-runtime-library/reference/system-wsystem.md)