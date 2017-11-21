---
title: -DYNAMICBASE | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /dynamicbase
dev_langs: C++
helpviewer_keywords:
- -DYNAMICBASE editbin option
- DYNAMICBASE editbin option
- /DYNAMICBASE editbin option
ms.assetid: edb3df90-7b07-42fb-a94a-f5a4c1d325d6
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8b5af34353db3c5b7cebaf02e8ce6b1bd9518cc8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="dynamicbase"></a>/DYNAMICBASE
Określa, czy obraz wykonywalny może być losowo przebazowanych w czasie ładowania przy użyciu randomizacji układu przestrzeni adresowej (ASLR).  
  
## <a name="syntax"></a>Składnia  
  
```  
  
/DYNAMICBASE[:NO]  
```  
  
## <a name="remarks"></a>Uwagi  
 Domyślnie ustawia konsolidator **/DYNAMICBASE** opcji.  
  
 Ta opcja modyfikuje nagłówek obrazu wykonywalnego, aby wskazać, czy moduł ładujący mogą losowo rebase obrazu w czasie ładowania.  
  
 ASLR jest obsługiwana w systemach Windows Vista, Windows Server 2008, Windows 7, Windows 8 i Windows Server 2012.  
  
## <a name="see-also"></a>Zobacz też  
 [Opcje polecenia EDITBIN](../../build/reference/editbin-options.md)   
 [Poziom ochrony oprogramowania niezależnego dostawcy oprogramowania systemu Windows](http://msdn.microsoft.com/library/bb430720.aspx)