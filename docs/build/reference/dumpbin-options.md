---
title: Opcje DUMPBIN
description: Przewodnik referencyjny dotyczący opcji wiersza polecenia narzędzia Microsoft polecenia DUMPBIN.
ms.date: 02/09/2020
helpviewer_keywords:
- DUMPBIN program, options
ms.assetid: 563b696e-7599-4480-94b9-014776289ec8
ms.openlocfilehash: 54f5a22808026f4442f85d5e53a0805702e05868
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440038"
---
# <a name="dumpbin-options"></a>Opcje DUMPBIN

Opcja składa się ze *specyfikatora opcji*, który jest kreską (`-`) lub ukośnikiem (`/`), po którym następuje nazwa opcji. Nazwy opcji nie mogą być skracane. Niektóre opcje przyjmują argumenty, określone po dwukropku (`:`). W specyfikacji opcji nie można używać spacji ani tabulatorów. Użyj co najmniej jednej spacji lub kart, aby oddzielić specyfikacje opcji w wierszu polecenia. Nazwy opcji i ich słowa kluczowego lub nazwy pliku nie są rozróżniane wielkości liter. Większość opcji stosuje się do wszystkich plików binarnych, ale tylko dla niektórych typów plików. Domyślnie polecenia DUMPBIN wysyła informacje do wyjścia standardowego. Użyj opcji [/out](out-dumpbin.md) , aby wysłać dane wyjściowe do pliku.

## <a name="options-list"></a>Lista opcji

POLECENIA DUMPBIN z następującymi opcjami:

- [/ALL](all.md)

- [/ARCHIVEMEMBERS](archivemembers.md)

- [/CLRHEADER](clrheader.md)

- [/DEPENDENTS](dependents.md)

- [/DIRECTIVES](directives.md)

- [Opcja/DISASM\[: {BAJTy\|nobytes}\]](disasm.md)

- [/errorReport: {none | MONITUJ | KOLEJka | Wyślij}](errorreport-dumpbin-exe.md) (przestarzałe)

- [/EXPORTS](dash-exports.md)

- [/FPO](fpo.md)

- [/HEADERS](headers.md)

- [/IMPORTS —\[: filename\]](imports-dumpbin.md)

- [/LINENUMBERS](linenumbers.md)

- [/LINKERMEMBER\[: {1 | 2}\]](linkermember.md)

- [/LOADCONFIG](loadconfig.md)

- [/NOPDB](nopdb.md)

- [/OUT: filename](out-dumpbin.md)

- [/PDATA](pdata.md)

- [/PDBPATH\[: verbose\]](pdbpath.md)

- [/RANGEE: vaMin\[, vaMax\]](range.md)

- [/RAWDATA\[: {NONE\|1\|2\|4\|8}\[, #\]\]](rawdata.md)

- [/RELOCATIONS](relocations.md)

- [/SECTION: Nazwa](section-dumpbin.md)

- [/SUMMARY](summary.md)

- [/SYMBOLS](symbols.md)

- [/TLS](tls.md)

Aby wyświetlić listę opcji obsługiwanych przez polecenia DUMPBIN w wierszu polecenia, użyj **/?** zaznaczyć.

## <a name="see-also"></a>Zobacz też

[Dodatkowe\ narzędzia kompilacji MSVC](c-cpp-build-tools.md)
\ [wiersza polecenia polecenia DUMPBIN](dumpbin-command-line.md)
[Odwołanie polecenia DUMPBIN](dumpbin-reference.md)
