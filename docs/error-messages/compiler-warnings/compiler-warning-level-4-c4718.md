---
title: "Kompilatora (poziom 4) ostrzeżenie C4718 | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4718
dev_langs: C++
helpviewer_keywords: C4718
ms.assetid: 29507f8a-b024-42c1-a3b8-f35d1f2641f3
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 214c481f4ad77a7a67190cd7427e0cd5775ccc8c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4718"></a>Kompilator C4718 ostrzegawcze (poziom 4)
"wywołanie funkcji": wywołanie cykliczne nie ma żadnych efektów ubocznych, usuwanie  
  
 Funkcja zawiera wywołanie cykliczne, ale w przeciwnym razie nie ma skutków ubocznych. Wywołanie tej funkcji jest usuwany. Nie dotyczy poprawność program, ale jest zachowanie. Natomiast pozostawienie wywołanie może spowodować wyjątek czasu wykonywania przepełnienie stosu, wywołanie usunięcie tej możliwości.