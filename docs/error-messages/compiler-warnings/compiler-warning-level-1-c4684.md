---
title: Kompilatora (poziom 1) ostrzeżenie C4684 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4684
dev_langs:
- C++
helpviewer_keywords:
- C4684
ms.assetid: e95f1a83-2784-4b05-ae94-12148e056e26
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cba83467e4705323eaecd990a7c5c32777990ffb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33280991"
---
# <a name="compiler-warning-level-1-c4684"></a>Kompilator C4684 ostrzegawcze (poziom 1)
'attribute': ostrzeżenie!! atrybut może powodować generowanie nieprawidłowego kodu: Używaj ostrożnie  
  
 Użyto atrybutu, który zwykle nie należy używać.  
  
 Poniższy przykład generuje C4684:  
  
```  
// C4684.cpp  
// compile with: /W1 /LD  
 [module(name="xx")]; // C4684 expected  
[no_injected_text];  
```