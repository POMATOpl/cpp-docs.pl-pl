---
title: "Kompilatora (poziom 4) ostrzeżenie C4207 | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4207
dev_langs:
- C++
helpviewer_keywords:
- C4207
ms.assetid: f4e09e3e-ac87-4489-8e3f-c8f76b82e721
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 31211fb7eb8d71bf214d41d5649cc91a92c9b7fb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4207"></a>Kompilator C4207 ostrzegawcze (poziom 4)
użyto niestandardowego rozszerzenia: rozszerzony formularz inicjatora  
  
 Rozszerzenia Microsoft (/Ze), można zainicjować bez określonego rozmiaru tablicy `char` za pomocą ciągu w nawiasach klamrowych.  
  
## <a name="example"></a>Przykład  
  
```  
// C4207.c  
// compile with: /W4  
char c[] = { 'a', 'b', "cdefg" }; // C4207  
  
int main()  
{  
}  
```  
  
 Takie inicjalizacji są nieprawidłowe w obszarze Zgodność ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).