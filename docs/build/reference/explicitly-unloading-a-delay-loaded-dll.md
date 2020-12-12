---
description: 'Dowiedz się więcej na temat: jawne zwalnianie Delay-Loaded DLL'
title: Jawne zwalnianie bibliotek DLL załadowanych z opóźnieniem
ms.date: 11/04/2016
helpviewer_keywords:
- /DELAY:UNLOAD linker option
- DELAY:UNLOAD linker option
- __FUnloadDelayLoadedDLL2
- delayed loading of DLLs, unloading
ms.assetid: 1c4c5172-fd06-45d3-9e4f-f12343176b3c
ms.openlocfilehash: 03df08487acc1be05226021d6b7c1593eb0f031b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192385"
---
# <a name="explicitly-unloading-a-delay-loaded-dll"></a>Jawne zwalnianie bibliotek DLL załadowanych z opóźnieniem

Opcja konsolidatora [/delay](delay-delay-load-import-settings.md): Unload umożliwia zwolnienie biblioteki DLL, która została załadowana z opóźnieniem. Domyślnie, gdy kod zwalnia bibliotekę DLL (przy użyciu/Delay: unload i **__FUnloadDelayLoadedDLL2**), Importy ładowane z opóźnieniem pozostają w tabeli adresów importu (IAT). Jeśli jednak używasz/Delay: Unload w wierszu polecenia konsolidatora, funkcja pomocnika będzie obsługiwać jawne wyładowywanie biblioteki DLL, resetowanie IAT do jego oryginalnej postaci; wskaźniki teraz są zastępowane. IAT to pole w [ImgDelayDescr](calling-conventions-parameters-and-return-type.md) , które zawiera adres kopii oryginalnego IAT (jeśli istnieje).

## <a name="example"></a>Przykład

### <a name="code"></a>Kod

```
// link with /link /DELAYLOAD:MyDLL.dll /DELAY:UNLOAD
#include <windows.h>
#include <delayimp.h>
#include "MyDll.h"
#include <stdio.h>

#pragma comment(lib, "delayimp")
#pragma comment(lib, "MyDll")
int main()
{
    BOOL TestReturn;
    // MyDLL.DLL will load at this point
    fnMyDll();

    //MyDLL.dll will unload at this point
    TestReturn = __FUnloadDelayLoadedDLL2("MyDll.dll");

    if (TestReturn)
        printf_s("\nDLL was unloaded");
    else
        printf_s("\nDLL was not unloaded");
}
```

### <a name="comments"></a>Komentarze

Ważne uwagi dotyczące zwalniania biblioteki DLL załadowanej z opóźnieniem:

- Implementację funkcji **__FUnloadDelayLoadedDLL2** można znaleźć w pliku \VC7\INCLUDE\DELAYHLP. CPP.

- Parametr name funkcji **__FUnloadDelayLoadedDLL2** musi dokładnie pasować (włącznie z uwzględnieniem wielkości liter), jaka Biblioteka importowana zawiera (ten ciąg znajduje się również w tabeli import na obrazie). Zawartość biblioteki Import można wyświetlić za pomocą [polecenia DUMPBIN/DEPENDENTS](dependents.md). Jeśli pożądane jest dopasowanie ciągu bez uwzględniania wielkości liter, można zaktualizować **__FUnloadDelayLoadedDLL2** , aby użyć jednej z funkcji ciągów CRT lub wywołania interfejsu API systemu Windows.

Aby uzyskać więcej informacji [, zobacz zwalnianie Delay-Loaded dll](unloading-a-delay-loaded-dll.md) .

## <a name="see-also"></a>Zobacz też

[Obsługa konsolidatora dla Delay-Loaded bibliotek DLL](linker-support-for-delay-loaded-dlls.md)
