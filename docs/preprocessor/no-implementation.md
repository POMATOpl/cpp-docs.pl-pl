---
title: no_implementation — | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- no_implementation
dev_langs:
- C++
helpviewer_keywords:
- no_implementation attribute
ms.assetid: bdc67785-e131-409c-87bc-f4d2f4abb07b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c882a8d4eb2510969401b4280eb66116ad220c77
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/19/2018
ms.locfileid: "46440839"
---
# <a name="noimplementation"></a>no_implementation
**Określonego język C++**  
  
Powoduje pominięcie generowania nagłówka .tli, który zawiera implementacje funkcji elementów członkowskich otoki.  
  
## <a name="syntax"></a>Składnia  
  
```  
no_implementation  
```  
  
## <a name="remarks"></a>Uwagi  
 
Jeśli ten atrybut jest określony, nagłówku .tlh, za pomocą deklaracji do udostępnienia biblioteki typów elementów, zostanie wygenerowany bez `#include` instrukcję, aby uwzględnić plik nagłówka .tli.  
  
Ten atrybut jest używany w połączeniu z [implementation_only —](../preprocessor/implementation-only.md).  
  
**KONIEC określonego języka C++**  
  
## <a name="see-also"></a>Zobacz też  
 
[atrybuty #import](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import — dyrektywa](../preprocessor/hash-import-directive-cpp.md)