---
description: Dowiedz się więcej na temat:/RANGE
title: /RANGE
ms.date: 11/04/2016
f1_keywords:
- /RANGE
helpviewer_keywords:
- /RANGE dumpbin option
- -RANGE dumpbin option
ms.assetid: 7eeba266-32be-49cc-a350-96bdf541f98a
ms.openlocfilehash: 9af54bddde977e92b5256f0835c31afbff1405d4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225404"
---
# <a name="range"></a>/RANGE

Modyfikuje dane wyjściowe elementu polecenia DUMPBIN, gdy jest używany z innymi opcjami polecenia DUMPBIN, takimi jak/RAWDATA lub/DISASM.

## <a name="syntax"></a>Składnia

```
/RANGE:vaMin[,vaMax]
```

## <a name="parameters"></a>Parametry

*vaMin*<br/>
Adres wirtualny, na którym ma zostać rozpoczęta operacja polecenia DUMPBIN.

*vaMax*<br/>
Obowiązkowe Adres wirtualny, na którym ma zostać zakończona operacja polecenia DUMPBIN. Jeśli nie zostanie określony, polecenia DUMPBIN rozpocznie się na końcu pliku.

## <a name="remarks"></a>Uwagi

Aby wyświetlić adresy wirtualne dla obrazu, użyj pliku mapy dla obrazu (RVA + Base), **opcja/DISASM** lub **/Headers** opcji polecenia DUMPBIN lub okna demontażu w debugerze programu Visual Studio.

## <a name="example"></a>Przykład

W tym przykładzie **/Range** służy do modyfikowania wyświetlania opcji **opcja/DISASM** . W tym przykładzie wartość początkowa jest wyrażona jako liczba dziesiętna, a wartość końcowa jest określana jako liczba szesnastkowa.

```
dumpbin /disasm /range:4219334,0x004061CD t.exe
```

## <a name="see-also"></a>Zobacz też

[Opcje polecenia DUMPBIN](dumpbin-options.md)
