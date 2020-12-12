---
description: 'Dowiedz się więcej na temat: opcja/DISASM'
title: /DISASM
ms.date: 01/17/2018
f1_keywords:
- /disasm
helpviewer_keywords:
- -DISASM dumpbin option
- DISASM dumpbin option
- /DISASM dumpbin option
ms.openlocfilehash: 764754e017958a57afd53236b7fc1ffb6217d850
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192905"
---
# <a name="disasm"></a>/DISASM

Wydrukuj demontaż sekcji kodu w danych wyjściowych polecenia DUMPBIN.

## <a name="syntax"></a>Składnia

> **opcja/DISASM**{**:** \[ **bajtów** | **nobytes**]}

### <a name="arguments"></a>Argumenty

**SZYBKOŚĆ**<br/>
Zawiera instrukcje bajty wraz ze interpretowanymi opcode i argumentami w danych wyjściowych demontażu. Jest to domyślne ustawienie opcji.

**Nobajtów**<br/>
Nie zawiera instrukcji w bajtach w danych wyjściowych deasemblera.

## <a name="remarks"></a>Uwagi

Opcja **opcja/DISASM** wyświetla odzbiór sekcji kodu w pliku. Używa symboli debugowania, jeśli znajdują się w pliku.

**Opcja/DISASM** należy używać tylko w natywnych, niezarządzanych obrazach. Odpowiednikiem narzędzia dla kodu zarządzanego jest [Ildasm](/dotnet/framework/tools/ildasm-exe-il-disassembler).

Tylko opcja [/Headers](headers.md) polecenia DUMPBIN jest dostępna do użytku dla plików tworzonych przez opcję kompilatora [/GL (Optymalizacja całego programu)](gl-whole-program-optimization.md) .

## <a name="see-also"></a>Zobacz też

[Opcje polecenia DUMPBIN](dumpbin-options.md)
