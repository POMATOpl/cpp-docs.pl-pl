---
title: "Kompilatora (poziom 1) ostrzeżenie C4067 | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4067
dev_langs: C++
helpviewer_keywords: C4067
ms.assetid: 1d10353e-8cd5-4b01-9184-a06189b965a4
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 90c29e7bc63096a6e46d4febda9c66d2759bb06a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4067"></a>Kompilator C4067 ostrzegawcze (poziom 1)
nieoczekiwane tokeny dyrektywie preprocesora - oczekiwano nowego wiersza  
  
 Kompilator znalezione i zignorowane dodatkowe znaki po dyrektywie preprocesora. To ostrzeżenie jest wyświetlane tylko w obszarze Zgodność ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).  
  
```  
// C4067a.cpp  
// compile with: /DX /Za /W1  
#pragma warning(default:4067)  
#if defined(X)  
#else  
#endif v   // C4067  
int main()  
{  
}  
```  
  
### <a name="to-resolve-this-warning-try-the-following"></a>Aby usunąć to ostrzeżenie, należy spróbować wykonać następujące czynności:  
  
1.  Kompiluj z użyciem **/Ze**.  
  
2.  Używać ograniczników do komentarzy:  
  
```  
// C4067b.cpp  
// compile with: /DX /Za /W1  
#if defined(X)  
#else  
#endif  
int main()  
{  
}  
```