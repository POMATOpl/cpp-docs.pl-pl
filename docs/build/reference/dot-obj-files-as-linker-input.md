---
description: Dowiedz się więcej na temat:. Pliki obj jako dane wejściowe konsolidatora
title: Pliki .Obj — Wejście konsolidatora
ms.date: 12/29/2017
helpviewer_keywords:
- linker [C++], OBJ files as input
- object files, linker output
- OMF object files
- LINK tool [C++], .obj files
- COFF files
- OBJ files as linker input
- .obj files as linker input
ms.openlocfilehash: 33b4a9d9a23854766100d0b023713f7ecbc71e32
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192723"
---
# <a name="obj-files-as-linker-input"></a>Pliki .Obj — Wejście konsolidatora

Narzędzie konsolidatora (LINK.EXE) akceptuje pliki. obj, które znajdują się w popularnym formacie plików obiektów (COFF).

## <a name="remarks"></a>Uwagi

Firma Microsoft oferuje pełny opis typowego formatu pliku obiektu. Aby uzyskać więcej informacji, zobacz [Format PE](/windows/win32/Debug/pe-format).

## <a name="unicode-support"></a>Obsługa Unicode

Począwszy od programu Visual Studio 2005, kompilator Microsoft MSVC obsługuje znaki Unicode w identyfikatorach zgodnie ze standardami ISO/IEC C i C++. Poprzednie wersje kompilatora obsługują tylko znaki ASCII w identyfikatorach. Aby zapewnić obsługę Unicode w nazwach funkcji, klas i elementów statycznych, kompilator i konsolidator używają kodowania Unicode UTF-8 dla symboli COFF w plikach. obj. Kodowanie UTF-8 jest w większym zakresie zgodne z kodowaniem ASCII używanym przez wcześniejsze wersje programu Visual Studio.

Aby uzyskać więcej informacji na temat kompilatora i konsolidatora, zobacz [Obsługa standardu Unicode w kompilatorze i konsolidatorze](unicode-support-in-the-compiler-and-linker.md). Aby uzyskać więcej informacji na temat standardu Unicode, zobacz organizację [Unicode](https://home.unicode.org/) .

## <a name="see-also"></a>Zobacz też

[Połącz pliki wejściowe](link-input-files.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)<br/>
[Obsługa formatu Unicode](../../text/support-for-unicode.md)<br/>
[Obsługa formatu Unicode w kompilatorze i konsolidatorze](unicode-support-in-the-compiler-and-linker.md)<br/>
[Standard Unicode](https://home.unicode.org/)<br/>
[Format PE](/windows/win32/Debug/pe-format)
