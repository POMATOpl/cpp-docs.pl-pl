---
title: "Kompilatora (poziom 4) ostrzeżenie C4611 | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4611
dev_langs: C++
helpviewer_keywords: C4611
ms.assetid: bd90d0a6-75f9-4e97-968d-dda6773e9fd8
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8f2ed128d37ff4c09247097d771bc62a97f6e757
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4611"></a>Kompilator C4611 ostrzegawcze (poziom 4)
Interakcja między "function" i zniszczeniem obiektu języka C++ nie jest przenośna  
  
 Na niektórych platformach, funkcje, które obejmują **catch** może nie obsługiwać semantyki obiektu C++ likwidacji, gdy znajdują się poza zakresem.  
  
 Aby uniknąć nieoczekiwanego zachowania, należy unikać **catch** w funkcje, które mają konstruktory i destruktory.  
  
 To ostrzeżenie zostanie wyświetlone tylko raz; zobacz [warning elementu pragma](../../preprocessor/warning.md).