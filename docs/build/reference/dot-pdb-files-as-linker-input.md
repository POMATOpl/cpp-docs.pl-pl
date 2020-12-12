---
description: Dowiedz się więcej na temat:. Pliki PDB jako dane wejściowe konsolidatora
title: Pliki .Pdb — Wejście konsolidatora
ms.date: 11/04/2016
helpviewer_keywords:
- .pdb files, as linker input
- PDB files, as linker input
ms.assetid: c1071478-2369-4b03-9df8-71761cf82f3b
ms.openlocfilehash: 713d42e7e95b5d1e7e3b1f9be21203b75569cdbe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201160"
---
# <a name="pdb-files-as-linker-input"></a>Pliki .Pdb — Wejście konsolidatora

Pliki obiektu (. obj) skompilowane przy użyciu opcji/Zi zawierają nazwę bazy danych programu (PDB). Nazwa pliku PDB obiektu nie zostanie określona dla konsolidatora; LINK używa osadzonej nazwy, aby znaleźć plik PDB, jeśli jest to konieczne. Dotyczy to również obiektów możliwością debugowania znajdujących się w bibliotece; plik PDB dla biblioteki możliwością debugowania musi być dostępny dla konsolidatora wraz z biblioteką.

LINK używa również pliku PDB do przechowywania informacji debugowania dla pliku exe lub. dll. Plik PDB programu jest zarówno plikiem wyjściowym, jak i plikiem wejściowym, ponieważ LINK aktualizuje plik PDB podczas ponownego kompilowania programu.

## <a name="see-also"></a>Zobacz też

[Połącz pliki wejściowe](link-input-files.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
