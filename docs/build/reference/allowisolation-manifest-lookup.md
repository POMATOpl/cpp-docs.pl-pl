---
description: Dowiedz się więcej o:/ALLOWISOLATION (odnośnik manifestu)
title: /ALLOWISOLATION (Przeszukiwanie manifestu)
ms.date: 11/04/2016
f1_keywords:
- /ALLOWISOLATION
- VC.Project.VCLinkerTool.AllowIsolation
helpviewer_keywords:
- -ALLOWISOLATION linker option
- /ALLOWISOLATION linker option
ms.assetid: 6d41851e-b3c1-4bdf-beaa-031773089d6f
ms.openlocfilehash: 659c908e4de910941ca71c9f40814608df19c6d4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187224"
---
# <a name="allowisolation-manifest-lookup"></a>/ALLOWISOLATION (Przeszukiwanie manifestu)

Określa zachowanie wyszukiwania manifestu.

## <a name="syntax"></a>Składnia

```
/ALLOWISOLATION[:NO]
```

## <a name="remarks"></a>Uwagi

**/ALLOWISOLATION: nie** wskazuje, że biblioteki DLL są załadowane tak, jakby nie było żadnego manifestu i powodują, że konsolidator ustawi `IMAGE_DLLCHARACTERISTICS_NO_ISOLATION` bit w polu opcjonalnego nagłówka `DllCharacteristics` .

**/ALLOWISOLATION** powoduje, że system operacyjny przeszukiwanie i ładowanie manifestu.

Wartość domyślna to **/ALLOWISOLATION** .

Gdy izolacja jest wyłączona dla pliku wykonywalnego, moduł ładujący systemu Windows nie będzie podejmować próby znalezienia manifestu aplikacji dla nowo utworzonego procesu. Nowy proces nie będzie miał domyślnego kontekstu aktywacji, nawet jeśli w pliku wykonywalnym lub umieszczonym w tym samym katalogu, w którym znajduje się plik wykonywalny o nazwie <em>Executable-Name</em>**. exe. manifest**.

Aby uzyskać więcej informacji, zobacz [Dokumentacja plików manifestu](/windows/win32/SbsCs/manifest-files-reference).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz pozycję **Właściwości konfiguracji**  >    >  Strona właściwości **pliku manifestu** konsolidatora.

1. Zmodyfikuj właściwość **Zezwalaj na izolację** .

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
