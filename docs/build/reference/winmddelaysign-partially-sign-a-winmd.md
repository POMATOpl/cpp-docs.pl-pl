---
description: Dowiedz się więcej o:/WINMDDELAYSIGN (częściowo Podpisz element winmd)
title: /WINMDDELAYSIGN (podpisz częściowo winmd)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.WINMDDelaySign
ms.assetid: 445cd602-62cb-400a-8e3a-4beb6572724d
ms.openlocfilehash: 801b172f52a9beb9d09617644b3096e460359724
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97259061"
---
# <a name="winmddelaysign-partially-sign-a-winmd"></a>/WINMDDELAYSIGN (podpisz częściowo winmd)

Włącza częściowe podpisywanie pliku metadanych środowisko wykonawcze systemu Windows (WinMD) przez umieszczenie klucza publicznego w pliku.

```
/WINMDDELAYSIGN[:NO]
```

## <a name="remarks"></a>Uwagi

Przypomina opcję konsolidatora [/delaysign](delaysign-partially-sign-an-assembly.md) , która jest stosowana do pliku winmd. Użyj **/WINMDDELAYSIGN** , jeśli chcesz umieścić tylko klucz publiczny w pliku winmd. Domyślnie konsolidator działa tak, jakby **/WINMDDELAYSIGN: nie** zostały określone; oznacza to, że nie podpisuje pliku winmd.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz folder **konsolidatora** .

1. Wybierz stronę właściwości **metadanych systemu Windows** .

1. Z listy rozwijanej **Opóźnij metadane systemu Windows** wybierz żądaną opcję.

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
