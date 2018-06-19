---
title: Ostrzeżenie LNK4105 narzędzi konsolidatora | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4105
dev_langs:
- C++
helpviewer_keywords:
- LNK4105
ms.assetid: 6c7bebf4-4ea6-4533-a6ed-e563d43abbd7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0ffdd8953e08f38d36bdfc2e68ad6cb8e06fb85b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33304417"
---
# <a name="linker-tools-warning-lnk4105"></a>Ostrzeżenie LNK4105 narzędzi konsolidatora
Brak argumentu określona z opcją "option"; Ignorowanie opcji  
  
 To ostrzeżenie występuje tylko gdy [/libpath](../../build/reference/libpath-additional-libpath.md) opcja jest ustawiona. Jeśli nie określono katalogu przy użyciu tej opcji, konsolidator ignoruje opcję i generuje ten komunikat ostrzegawczy.  
  
 Jeśli musisz zastąpić istniejące ustawienia środowiska biblioteki, Usuń opcję/libpath z wiersza polecenia konsolidatora. Jeśli chcesz użyć ścieżki alternatywnej wyszukiwania dla bibliotek, określ ścieżkę alternatywną, zgodnie z opcją/libpath.  
  
## <a name="example"></a>Przykład  
  
```  
link /libpath:c:\filepath\lib bar.obj  
```  
  
 czy bezpośrednie konsolidator, aby wyszukać wymaganych bibliotek w `c:\filepath\lib` przed wyszukiwaniem w lokalizacji domyślnej.