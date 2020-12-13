---
description: 'Dowiedz się więcej na temat: Błąd narzędzi konsolidatora LNK1200'
title: Błąd narzędzi konsolidatora LNK1200
ms.date: 11/04/2016
f1_keywords:
- LNK1200
helpviewer_keywords:
- LNK1200
ms.assetid: 55771145-915e-4006-ac6c-ac702041eb2f
ms.openlocfilehash: b8c380b16cef47a4b340e4a48853d58d1ab203e5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341649"
---
# <a name="linker-tools-error-lnk1200"></a>Błąd narzędzi konsolidatora LNK1200

błąd podczas odczytywania bazy danych programu "filename"

Nie można odczytać bazy danych programu (PDB).

Ten błąd może być spowodowany uszkodzeniem pliku.

Jeśli `filename` jest plikiem PDB dla pliku obiektu, Skompiluj ponownie plik obiektu za pomocą [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md).

Jeśli `filename` jest plikiem PDB dla głównego pliku wyjściowego i ten błąd wystąpił podczas przyrostowego łącza, usuń plik PDB i ponownie połącz.
