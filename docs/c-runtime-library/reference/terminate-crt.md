---
title: "Zakończenie (CRT) | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: terminate
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords: terminate
dev_langs: C++
helpviewer_keywords:
- terminate function
- exception handling, termination
ms.assetid: 90e67402-08e9-4b2a-962c-66a8afd3ccb4
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b04cd56f2239bcee291a0de37f23f7eb2e699f1a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="terminate-crt"></a>zakończenie (CRT)
Wywołania `abort` lub funkcję należy ją określić za pomocą `set_terminate`.  
  
## <a name="syntax"></a>Składnia  
  
```  
void terminate( void );  
```  
  
## <a name="remarks"></a>Uwagi  
 `terminate` Funkcja jest używana z C++, obsługa wyjątków i jest wywoływana w następujących przypadkach:  
  
-   Nie można odnaleźć pasującego obsługi catch dla zwrócony wyjątek C++.  
  
-   Wyjątek jest generowane przez funkcję destruktora podczas unwind stosu.  
  
-   Stos jest uszkodzony po zgłoszeniu wyjątku.  
  
 `terminate`wywołania `abort` domyślnie. To ustawienie domyślne można zmienić, pisanie funkcji zakończenia i wywołanie `set_terminate` z nazwą funkcji jako jej argument. `terminate`wywołuje ostatniej podany jako argument do funkcji `set_terminate`. Aby uzyskać więcej informacji, zobacz [nieobsługiwanych wyjątków C++](../../cpp/unhandled-cpp-exceptions.md).  
  
## <a name="requirements"></a>Wymagania  
  
|Procedura|Wymagany nagłówek|  
|-------------|---------------------|  
|`terminate`|\<EH.h >|  
  
 Aby uzyskać dodatkowe informacje o zgodności, zobacz [zgodności](../../c-runtime-library/compatibility.md) we wprowadzeniu.  
  
## <a name="example"></a>Przykład  
  
```  
// crt_terminate.cpp  
// compile with: /EHsc  
#include <eh.h>  
#include <process.h>  
#include <iostream>  
using namespace std;  
  
void term_func();  
  
int main()  
{  
    int i = 10, j = 0, result;  
    set_terminate( term_func );  
    try  
    {  
        if( j == 0 )  
            throw "Divide by zero!";  
        else  
            result = i/j;  
    }  
    catch( int )  
    {  
        cout << "Caught some integer exception.\n";  
    }  
    cout << "This should never print.\n";  
}  
  
void term_func()  
{  
    cout << "term_func() was called by terminate().\n";  
  
    // ... cleanup tasks performed here  
  
    // If this function does not exit, abort is called.  
  
    exit(-1);  
}  
```  
  
```Output  
term_func() was called by terminate().  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Obsługa wyjątków — procedury](../../c-runtime-library/exception-handling-routines.md)   
 [przerwania](../../c-runtime-library/reference/abort.md)   
 [_set_se_translator —](../../c-runtime-library/reference/set-se-translator.md)   
 [set_terminate —](../../c-runtime-library/reference/set-terminate-crt.md)   
 [set_unexpected —](../../c-runtime-library/reference/set-unexpected-crt.md)   
 [Nieoczekiwany](../../c-runtime-library/reference/unexpected-crt.md)