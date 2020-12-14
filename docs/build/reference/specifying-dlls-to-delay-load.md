---
description: 'Dowiedz się więcej na temat: Określanie bibliotek DLL do opóźnienia ładowania'
title: Określanie bibliotek DLL w celu opóźnienia ładowania
ms.date: 11/04/2016
helpviewer_keywords:
- DELAYLOAD linker option
- delayed loading of DLLs
- delayed loading of DLLs, specifying
- /DELAYLOAD linker option
ms.assetid: 94cbecfe-7a42-40d1-a618-9f2786bac0d8
ms.openlocfilehash: ece96ea6f818c7e0bc6b6e032ce523e96a9f4ecb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224547"
---
# <a name="specifying-dlls-to-delay-load"></a>Określanie bibliotek DLL w celu opóźnienia ładowania

Można określić, które biblioteki dll należy opóźnić ładowanie za pomocą opcji [/DELAYLOAD](delayload-delay-load-import.md): `dllname` konsolidatora. Jeśli nie planujesz używania własnej wersji funkcji pomocnika, musisz również połączyć program z delayimp. lib (dla aplikacji klasycznych) lub dloadhelper. lib (dla aplikacji ze sklepu).

Poniżej przedstawiono prosty przykład opóźnienia ładowania biblioteki DLL:

```
// cl t.cpp user32.lib delayimp.lib  /link /DELAYLOAD:user32.dll
#include <windows.h>
// uncomment these lines to remove .libs from command line
// #pragma comment(lib, "delayimp")
// #pragma comment(lib, "user32")

int main() {
   // user32.dll will load at this point
   MessageBox(NULL, "Hello", "Hello", MB_OK);
}
```

Kompiluj wersję debugowania projektu. Przechodzenie przez kod przy użyciu debugera i Zauważ, że user32.dll jest ładowany tylko wtedy, gdy nastąpi wywołanie `MessageBox` .

## <a name="see-also"></a>Zobacz też

[Obsługa konsolidatora dla Delay-Loaded bibliotek DLL](linker-support-for-delay-loaded-dlls.md)
