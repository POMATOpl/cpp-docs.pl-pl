---
description: 'Dowiedz się więcej na temat: Command-Line błędu D8037'
title: Błąd D8037 wiersza polecenia
ms.date: 11/04/2016
f1_keywords:
- D8037
helpviewer_keywords:
- D8037
ms.assetid: acddaaa0-bd84-426f-a37b-8f680b379c9d
ms.openlocfilehash: a3f01828bbe8d1df98260ebec2b5646442ec65e1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97136187"
---
# <a name="command-line-error-d8037"></a>Błąd D8037 wiersza polecenia

nie można utworzyć pliku tymczasowego Il; Oczyść katalog Temp starych plików Il

Za mało miejsca, aby utworzyć tymczasowe pliki pośrednie kompilatora. Aby naprawić ten błąd, Usuń wszelkie stare pliki MSIL w katalogu określonym przez zmienną środowiskową **tmp** . Te pliki będą mieć postać _CL_hhhhhhhh. SS, gdzie h reprezentuje losową cyfrę szesnastkową, a SS reprezentuje typ pliku IL. Pamiętaj również, aby zaktualizować maszynę przy użyciu najnowszych poprawek systemu operacyjnego.

## <a name="see-also"></a>Zobacz też

[Błędy wiersza polecenia od D8000 do D9999](../../error-messages/tool-errors/command-line-errors-d8000-through-d9999.md)<br/>
[Opcje kompilatora MSVC](../../build/reference/compiler-options.md)
