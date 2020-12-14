---
description: 'Dowiedz się więcej na temat: Praca z bibliotekami importu i eksportowanie plików'
title: Praca z bibliotekami importowanymi oraz plikami eksportowanymi
ms.date: 11/04/2016
helpviewer_keywords:
- LIB [C++], /DEF option
- import libraries
- LIB [C++], import libraries and export files
- export files
- import libraries, creating
ms.assetid: d8175596-9773-4c2f-959d-b05b065a5161
ms.openlocfilehash: b6e1664aedf5fa87d269e0ff250e6c52d9d18259
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258801"
---
# <a name="working-with-import-libraries-and-export-files"></a>Praca z bibliotekami importowanymi oraz plikami eksportowanymi

Do utworzenia biblioteki Import i pliku eksportu można użyć LIB z opcją/DEF. LINK używa pliku eksportu do kompilowania programu zawierającego eksporty (zazwyczaj biblioteki dołączanej dynamicznie (DLL)) i używa biblioteki importu do rozwiązywania odwołań do tych eksportów w innych programach.

Należy pamiętać, że jeśli utworzysz bibliotekę importu w ramach wstępnego kroku przed utworzeniem biblioteki. dll, musisz przekazać ten sam zestaw plików obiektów podczas kompilowania biblioteki.

W większości sytuacji nie trzeba używać LIB, aby utworzyć bibliotekę importu. Po połączeniu programu (pliku wykonywalnego lub biblioteki DLL) zawierającego eksporty, LINK automatycznie tworzy bibliotekę importu opisującą eksporty. Później podczas łączenia programu, który odwołuje się do tych eksportów, należy określić bibliotekę importu.

Jednak w przypadku eksportowania biblioteki DLL do programu, który również się importuje, bezpośrednio lub pośrednio, należy użyć LIB, aby utworzyć jedną z bibliotek importu. Gdy LIB tworzy bibliotekę importu, tworzy również plik eksportu. Należy użyć pliku eksportu podczas łączenia jednej z bibliotek DLL.

## <a name="see-also"></a>Zobacz też

[Dokumentacja biblioteki LIB](lib-reference.md)
