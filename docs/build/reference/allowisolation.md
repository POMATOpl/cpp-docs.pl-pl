---
description: Dowiedz się więcej na temat:/ALLOWISOLATION
title: /ALLOWISOLATION
ms.date: 11/04/2016
f1_keywords:
- /ALLOWISOLATION_EDITBIN
helpviewer_keywords:
- -ALLOWISOLATION editbin option
- /ALLOWISOLATION editbin option
- ALLOWISOLATION editbin option
ms.assetid: 91430344-f64f-491a-a5a5-7ea3b21cbe68
ms.openlocfilehash: 7d935bc122b5f32bb8f1193feae58b5fc61e7faa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179593"
---
# <a name="allowisolation"></a>/ALLOWISOLATION

Określa zachowanie wyszukiwania manifestu.

## <a name="syntax"></a>Składnia

```

/ALLOWISOLATION[:NO]
```

## <a name="remarks"></a>Uwagi

**/ALLOWISOLATION** powoduje, że system operacyjny przeszukiwanie i ładowanie manifestu.

Wartość domyślna to **/ALLOWISOLATION** .

**/ALLOWISOLATION: nie** wskazuje, że pliki wykonywalne są ładowane tak, jakby nie było manifestu, i powoduje [odwołanie polecenia EDITBIN](editbin-reference.md) do ustawiania `IMAGE_DLLCHARACTERISTICS_NO_ISOLATION` bitu w polu opcjonalnego nagłówka `DllCharacteristics` .

Gdy izolacja jest wyłączona dla pliku wykonywalnego, moduł ładujący systemu Windows nie próbuje znaleźć manifestu aplikacji dla nowo utworzonego procesu. Nowy proces nie ma domyślnego kontekstu aktywacji, nawet jeśli istnieje manifest w samym pliku wykonywalnym lub jeśli istnieje manifest o nazwie *Executable-Name*. exe. manifest.

## <a name="see-also"></a>Zobacz też

[Opcje polecenia EDITBIN](editbin-options.md)<br/>
[/ALLOWISOLATION (odnośnik manifestu)](allowisolation-manifest-lookup.md)<br/>
[Dokumentacja plików manifestu](/windows/win32/SbsCs/manifest-files-reference)
