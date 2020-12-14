---
description: 'Dowiedz się więcej na temat: Błąd narzędzi konsolidatora LNK2039'
title: Błąd narzędzi konsolidatora LNK2039
ms.date: 11/04/2016
f1_keywords:
- LNK2039
helpviewer_keywords:
- LNK2039
ms.assetid: eaa296bd-4901-41f6-8410-6d03ee827144
ms.openlocfilehash: 34bddbd456e8e588ff6f7818d8db1d3522ccd06a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97275636"
---
# <a name="linker-tools-error-lnk2039"></a>Błąd narzędzi konsolidatora LNK2039

Importowanie klasy referencyjnej " \<type> ", która jest zdefiniowana w innym obiekcie. obj; powinna zostać zaimportowana lub zdefiniowana, ale nie obie

Klasa referencyjna "<`type`>" została zaimportowana do określonego pliku. obj, ale jest również zdefiniowana w innym pliku. obj. Ten stan może spowodować awarię środowiska uruchomieniowego lub inne nieoczekiwane zachowanie.

### <a name="to-correct-this-error"></a>Aby poprawić ten błąd

1. Sprawdź, czy element " `type` " musi być zdefiniowany w innym pliku. obj i sprawdź, czy należy go zaimportować z pliku winmd.

1. Usuń definicję lub import.

## <a name="see-also"></a>Zobacz też

[Błędy i ostrzeżenia narzędzi konsolidatora](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)<br/>
[LNK1332 błędu narzędzi konsolidatora](../../error-messages/tool-errors/linker-tools-error-lnk1332.md)
