---
description: Dowiedz się więcej na temat:/PDBPATH
title: /PDBPATH
ms.date: 11/04/2016
f1_keywords:
- /pdbpath
helpviewer_keywords:
- .pdb files, path
- -PDBPATH dumpbin option
- /PDBPATH dumpbin option
- PDBPATH dumpbin option
- PDB files, path
ms.assetid: ccf67dcd-0b23-4250-ad47-06c48acbe82b
ms.openlocfilehash: 41207d7cfce3d72ecb9517d9ad3af8bcd3f901d7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226054"
---
# <a name="pdbpath"></a>/PDBPATH

```
/PDBPATH[:VERBOSE] filename
```

### <a name="parameters"></a>Parametry

*Nazwa pliku*<br/>
Nazwa pliku DLL lub exe, dla którego chcesz znaleźć pasujący plik. pdb.

**: Verbose**<br/>
Obowiązkowe Raportuje wszystkie katalogi, w których podjęto próbę zlokalizowania pliku. pdb.

## <a name="remarks"></a>Uwagi

/PDBPATH przeszuka komputer w tych samych ścieżkach, które debuger wyszuka plik. pdb, a następnie zgłosi, które pliki. pdb odpowiadają plikowi określonemu w *pliku filename*.

W przypadku korzystania z debugera programu Visual Studio może wystąpić problem spowodowany faktem, że debuger używa pliku. pdb dla innej wersji debugowanego pliku.

/PDBPATH wyszukuje pliki. pdb wzdłuż następujących ścieżek:

- Sprawdź lokalizację, w której znajduje się plik wykonywalny.

- Sprawdź lokalizację PDB zapisaną w pliku wykonywalnym. Zwykle jest to lokalizacja w czasie, gdy obraz został połączony.

- Sprawdź ścieżkę wyszukiwania skonfigurowaną w środowisku IDE programu Visual Studio.

- Sprawdź ścieżki w _NT_SYMBOL_PATH i _NT_ALT_SYMBOL_PATH zmiennych środowiskowych.

- Zaewidencjonuj katalog systemu Windows.

## <a name="see-also"></a>Zobacz też

[Opcje polecenia DUMPBIN](dumpbin-options.md)<br/>
[/PDBALTPATH (Użyj alternatywnej ścieżki PDB)](pdbaltpath-use-alternate-pdb-path.md)
