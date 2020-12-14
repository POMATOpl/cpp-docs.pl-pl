---
description: Dowiedz się więcej na temat:/LINKERMEMBER
title: /LINKERMEMBER
ms.date: 11/04/2016
f1_keywords:
- /linkermember
helpviewer_keywords:
- /LINKERMEMBER dumpbin option
- LINKERMEMBER dumpbin option
- -LINKERMEMBER dumpbin option
ms.assetid: c96868c1-d70e-4651-ae36-c55b58b16406
ms.openlocfilehash: 76c842bcc2299b4245847e7d4e9a64656e88d2d9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199392"
---
# <a name="linkermember"></a>/LINKERMEMBER

```
/LINKERMEMBER[:{1|2}]
```

## <a name="remarks"></a>Uwagi

Ta opcja powoduje wyświetlenie symboli publicznych zdefiniowanych w bibliotece. Określ 1 argument, aby wyświetlić symbole w kolejności obiektów, wraz z ich przesunięciami. Określ 2 argument, aby wyświetlić przesunięcia i numery indeksów obiektów, a następnie wyświetlić listę symboli w kolejności alfabetycznej, wraz z indeksem obiektów dla każdego z nich. Aby uzyskać dane wyjściowe, należy określić/LINKERMEMBER bez argumentu Number.

Tylko opcja [/Headers](headers.md) polecenia DUMPBIN jest dostępna do użycia w przypadku plików utworzonych przy użyciu opcji kompilatora [/GL](gl-whole-program-optimization.md) .

## <a name="see-also"></a>Zobacz też

[Opcje polecenia DUMPBIN](dumpbin-options.md)
