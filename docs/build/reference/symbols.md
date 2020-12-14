---
description: Dowiedz się więcej na temat:/SYMBOLS
title: /SYMBOLS
ms.date: 09/05/2018
f1_keywords:
- /symbols
helpviewer_keywords:
- symbols, dumping
- public symbols
- symbols, displaying COFF symbol table
- symbol tables
- SYMBOLS dumpbin option
- /SYMBOLS dumpbin option
- -SYMBOLS dumpbin option
ms.assetid: 34bcae90-4561-4c77-a80c-065508dec39a
ms.openlocfilehash: f0cc213a8b37f99e0cb80f6df88967e4eb5204b0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230149"
---
# <a name="symbols"></a>/SYMBOLS

```
/SYMBOLS
```

Ta opcja powoduje wyświetlenie tabeli symboli COFF. Tabele symboli istnieją we wszystkich plikach obiektów. Tabela symboli COFF zostanie wyświetlona w pliku obrazu tylko wtedy, gdy jest ona połączona z opcji/Debug.

Poniżej znajduje się opis danych wyjściowych dla/SYMBOLS. Dodatkowe informacje na temat znaczenia/SYMBOLS danych wyjściowych można znaleźć, przeglądając plik Winnt. h (IMAGE_SYMBOL i IMAGE_AUX_SYMBOL) lub dokumentację COFF.

Pobrano następujący przykładowy zrzut:

```
Dump of file main.obj
File Type: COFF OBJECT

COFF SYMBOL TABLE
000 00000000 DEBUG    notype       Filename     | .file
    main.cpp
002 000B1FDB ABS      notype       Static       | @comp.id
003 00000000 SECT1    notype       Static       | .drectve
    Section length     26, #relocs    0, #linenums    0, checksum 722C964F
005 00000000 SECT2    notype       Static       | .text
    Section length     23, #relocs    1, #linenums    0, checksum 459FF65F, selection    1 (pick no duplicates)
007 00000000 SECT2    notype ()    External     | _main
008 00000000 UNDEF    notype ()    External     | ?MyDump@@YAXXZ (void __cdecl MyDump(void))

String Table Size = 0x10 bytes

  Summary

         26 .drectve
         23 .text
```

## <a name="remarks"></a>Uwagi

Następujący opis dla linii zaczynających się od numeru symbolu zawiera opis kolumn, które mają informacje istotne dla użytkowników:

- Numer pierwszej z trzech cyfr jest indeksem/liczbą symboli.

- Jeśli trzecia kolumna zawiera wystawki *x*, symbol jest zdefiniowany w tej sekcji pliku obiektu. Ale jeśli UNDEF pojawia się, nie jest zdefiniowana w tym obiekcie i musi być rozwiązany w innym miejscu.

- Piąta kolumna (statyczna, zewnętrzna) informuje, czy symbol jest widoczny tylko w obrębie tego obiektu, czy jest publiczny (widoczny zewnętrznie). Statyczny symbol _sym nie może być połączony z publicznym symbolem _sym; mogą to być dwa różne wystąpienia funkcji o nazwie _sym.

Ostatnią kolumną w numerowanym wierszu jest nazwa symbolu, zarówno dekoracyjne, jak i niedekoracyjne.

Tylko opcja [/Headers](headers.md) polecenia DUMPBIN jest dostępna do użycia w przypadku plików utworzonych przy użyciu opcji kompilatora [/GL](gl-whole-program-optimization.md) .

## <a name="see-also"></a>Zobacz też

[Opcje polecenia DUMPBIN](dumpbin-options.md)
