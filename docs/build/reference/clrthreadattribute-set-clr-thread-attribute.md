---
description: Dowiedz się więcej o:/CLRTHREADATTRIBUTE (ustaw atrybut wątku CLR)
title: /CLRTHREADATTRIBUTE (Ustaw atrybut wątku CTR)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.CLRThreadAttribute
helpviewer_keywords:
- /CLRTHREADATTRIBUTE linker option
- -CLRTHREADATTRIBUTE linker option
ms.assetid: 4907e9ef-5031-446c-aecf-0a0b32fae1e8
ms.openlocfilehash: 119797ee10ed0c08477b8e08635605e4299ffd41
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179125"
---
# <a name="clrthreadattribute-set-clr-thread-attribute"></a>/CLRTHREADATTRIBUTE (Ustaw atrybut wątku CTR)

Jawnie określ atrybut wątkowości dla punktu wejścia programu CLR.

## <a name="syntax"></a>Składnia

```
/CLRTHREADATTRIBUTE:{STA|MTA|NONE}
```

#### <a name="parameters"></a>Parametry

**MTA**<br/>
Stosuje atrybut MTAThreadAttribute do punktu wejścia programu.

**DAWAJ**<br/>
Analogicznie jak nieokreślanie/CLRTHREADATTRIBUTE.  Umożliwia ustawienie domyślnego atrybutu Threading środowiska uruchomieniowego języka wspólnego (CLR).

**STA**<br/>
Stosuje atrybut STAThreadAttribute do punktu wejścia programu.

## <a name="remarks"></a>Uwagi

Ustawienie atrybutu wątku jest prawidłowe tylko w przypadku kompilowania pliku. exe, ponieważ ma wpływ na punkt wejścia głównego wątku.

Jeśli używasz domyślnego punktu wejścia (na przykład Main lub wmain), określ model wątkowości za pomocą/CLRTHREADATTRIBUTE lub przez umieszczenie atrybutu Threading (STAThreadAttribute lub MTAThreadAttribute) w funkcji default entry.

W przypadku użycia punktu wejścia innego niż domyślny należy określić model wątkowości przy użyciu/CLRTHREADATTRIBUTE lub poprzez umieszczenie atrybutu Threading w funkcji wprowadzania niedomyślnego, a następnie określić niedomyślny punkt wejścia z [/entry](entry-entry-point-symbol.md).

Jeśli model wątkowości określony w kodzie źródłowym nie zgadza się z modelem wątkowości określonym za pomocą/CLRTHREADATTRIBUTE, konsolidator zignoruje/CLRTHREADATTRIBUTE i zastosuje model wątkowości określony w kodzie źródłowym.

Będzie to konieczne, aby można było używać jednowątkowego, na przykład jeśli program CLR hostuje obiekt COM używający jednowątkowego.  Jeśli program CLR używa wielowątkowości, nie może hostować obiektu COM, który używa jednowątkowego.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Rozwiń węzeł **Właściwości konfiguracji** .

1. Rozwiń węzeł **konsolidatora** .

1. Wybierz stronę właściwości **Zaawansowane** .

1. Zmodyfikuj właściwość **atrybutu wątku CLR** .

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

1. Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRThreadAttribute%2A>.

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
