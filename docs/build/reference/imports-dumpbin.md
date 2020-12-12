---
description: Dowiedz się więcej na temat:/IMPORTS — (polecenia DUMPBIN)
title: /IMPORTS (DUMPBIN)
ms.date: 11/04/2016
f1_keywords:
- /imports
helpviewer_keywords:
- IMPORTS dumpbin option
- /IMPORTS dumpbin option
- -IMPORTS dumpbin option
ms.assetid: 6a296216-2b1b-40f8-8736-cd4553a22456
ms.openlocfilehash: 86c428280bbca3a4957f7d7a0a640482607547de
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199795"
---
# <a name="imports-dumpbin"></a>/IMPORTS (DUMPBIN)

```
/IMPORTS[:file]
```

Ta opcja powoduje wyświetlenie listy bibliotek DLL (zarówno połączonych statycznie i [załadowane z opóźnieniem](linker-support-for-delay-loaded-dlls.md)), które są importowane do pliku wykonywalnego lub biblioteki DLL i wszystkich poszczególnych importów z każdej z tych bibliotek DLL.

Opcjonalna `file` Specyfikacja pozwala określić, że będą wyświetlane Importy tylko dla tej biblioteki DLL. Na przykład:

```
dumpbin /IMPORTS:msvcrt.dll
```

## <a name="remarks"></a>Uwagi

Dane wyjściowe wyświetlane przez tę opcję są podobne do danych wyjściowych [/exports](dash-exports.md) .

Tylko opcja [/Headers](headers.md) polecenia DUMPBIN jest dostępna do użycia w przypadku plików utworzonych przy użyciu opcji kompilatora [/GL](gl-whole-program-optimization.md) .

## <a name="see-also"></a>Zobacz też

[Opcje polecenia DUMPBIN](dumpbin-options.md)
