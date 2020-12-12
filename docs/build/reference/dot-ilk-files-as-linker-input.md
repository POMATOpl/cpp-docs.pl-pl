---
description: Dowiedz się więcej na temat:. ILK pliki jako dane wejściowe konsolidatora
title: Pliki .Ilk — Wejście konsolidatora
ms.date: 11/04/2016
helpviewer_keywords:
- ILK files
- .ilk files
ms.assetid: 7324c104-9e5d-423d-b268-b59f92607bf2
ms.openlocfilehash: 0aaa5fac19cedb8d94fc6dc9ab03a0f23fa0e49b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192736"
---
# <a name="ilk-files-as-linker-input"></a>Pliki .Ilk — Wejście konsolidatora

Podczas łączenia przyrostowo, LINK aktualizuje plik stanu ILK, który został utworzony podczas pierwszego linku przyrostowego. Ten plik ma taką samą nazwę bazową jak plik exe lub plik. dll i ma rozszerzenie. ilk. Podczas kolejnych linków przyrostowych LINK aktualizuje plik. ilk. Jeśli brakuje pliku. ilk, LINK wykonuje pełny link i tworzy nowy plik. ilk. Jeśli plik. ilk nie nadaje się do użytku, LINK wykonuje łącze nieprzyrostowe. Aby uzyskać szczegółowe informacje na temat konsolidacji przyrostowej, zobacz [link przyrostowo (/Incremental)](incremental-link-incrementally.md) .

## <a name="see-also"></a>Zobacz też

[Połącz pliki wejściowe](link-input-files.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
