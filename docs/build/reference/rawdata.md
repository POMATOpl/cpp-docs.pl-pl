---
description: Dowiedz się więcej na temat:/RAWDATA
title: /RAWDATA
ms.date: 11/04/2016
f1_keywords:
- /rawdata
helpviewer_keywords:
- RAWDATA dumpbin option
- raw data
- -RAWDATA dumpbin option
- /RAWDATA dumpbin option
ms.assetid: 41cba845-5e1f-415e-9fe4-604a52235983
ms.openlocfilehash: efe2001c0170b8539b98902591849dedaf0fb819
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225378"
---
# <a name="rawdata"></a>/RAWDATA

```
/RAWDATA[:{1|2|4|8|NONE[,number]]
```

## <a name="remarks"></a>Uwagi

Ta opcja wyświetla nieprzetworzoną zawartość każdej sekcji w pliku. Argumenty kontrolują format wyświetlania, jak pokazano poniżej:

|Argument|Wynik|
|--------------|------------|
|1|Domyślnie. Zawartość jest wyświetlana w bajtach szesnastkowych, a także jako znaki ASCII, jeśli mają wydrukowaną reprezentację.|
|2|Zawartość jest wyświetlana jako szesnastkowe wartości 2-bajtowe.|
|4|Zawartość jest wyświetlana jako szesnastkowe wartości 4-bajtowe.|
|8|Zawartość jest wyświetlana jako szesnastkowe wartości 8-bajtowe.|
|DAWAJ|Nieprzetworzone dane są pomijane. Ten argument jest przydatny do kontrolowania danych wyjściowych/ALL.|
|*Liczba*|Wyświetlane wiersze są ustawione na szerokość, która przechowuje `number` wartości w wierszu.|

Tylko opcja [/Headers](headers.md) polecenia DUMPBIN jest dostępna do użycia w przypadku plików utworzonych przy użyciu opcji kompilatora [/GL](gl-whole-program-optimization.md) .

## <a name="see-also"></a>Zobacz też

[Opcje polecenia DUMPBIN](dumpbin-options.md)
