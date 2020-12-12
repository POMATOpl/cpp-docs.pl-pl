---
description: Dowiedz się więcej na temat:. Pliki EXP jako dane wejściowe konsolidatora
title: Pliki .Exp — Wejście konsolidatora
ms.date: 11/04/2016
helpviewer_keywords:
- exporting functions
- import libraries, linker files
- linking [C++], exports
- exporting functions, information about exported functions
- exporting data, export (.exp) files
- functions [C++], exporting
- .exp files [C++]
- EXP files
ms.assetid: 399f5636-0a4d-462e-b500-5f5b9ae5ad22
ms.openlocfilehash: 03104d6b4265484e54373484b6c9bbdabf0e1afc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192814"
---
# <a name="exp-files-as-linker-input"></a>Pliki .Exp — Wejście konsolidatora

Pliki eksportu (. EXP) zawierają informacje dotyczące wyeksportowanych funkcji i elementów danych. Gdy LIB tworzy bibliotekę importu, tworzy również plik. EXP. Plik EXP jest używany podczas łączenia programu, który zarówno eksportuje, jak i importuje z innego programu — bezpośrednio lub pośrednio. Jeśli połączysz się z plikiem. EXP, LINK nie tworzy biblioteki importu, ponieważ zakłada, że LIB już ją utworzono. Aby uzyskać szczegółowe informacje na temat plików. exp i importowanych bibliotek, zobacz [Praca z bibliotekami importu i eksportowanie plików](working-with-import-libraries-and-export-files.md).

## <a name="see-also"></a>Zobacz też

[Połącz pliki wejściowe](link-input-files.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
