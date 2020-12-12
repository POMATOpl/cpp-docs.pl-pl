---
description: 'Dowiedz się więcej o: LNK4105 narzędzi KONSOLIDATORA ostrzeżenia narzędzi konsolidatora'
title: Ostrzeżenie LNK4105 narzędzi konsolidatora
ms.date: 11/04/2016
f1_keywords:
- LNK4105
helpviewer_keywords:
- LNK4105
ms.assetid: 6c7bebf4-4ea6-4533-a6ed-e563d43abbd7
ms.openlocfilehash: 6536273a0b3e5b6e60b782e5953a70a7b3eb2798
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294421"
---
# <a name="linker-tools-warning-lnk4105"></a>Ostrzeżenie LNK4105 narzędzi konsolidatora

nie określono argumentu z opcją "Option"; Ignorowanie opcji

To ostrzeżenie występuje tylko wtedy, gdy opcja [/LIBPATH](../../build/reference/libpath-additional-libpath.md) jest ustawiona. Jeśli dla tej opcji nie określono katalogu, konsolidator zignoruje opcję i wygeneruje ten komunikat ostrzegawczy.

Jeśli nie musisz przesłonić istniejących ustawień biblioteki środowiskowej, Usuń opcję/LIBPATH z wiersza polecenia konsolidatora. Jeśli chcesz użyć alternatywnej ścieżki wyszukiwania dla bibliotek, określ alternatywną ścieżkę po opcji/LIBPATH.

## <a name="example"></a>Przykład

```
link /libpath:c:\filepath\lib bar.obj
```

nakazuje konsolidatorowi wyszukanie wymaganych bibliotek w programie `c:\filepath\lib` przed wyszukiwaniem w lokalizacjach domyślnych.
