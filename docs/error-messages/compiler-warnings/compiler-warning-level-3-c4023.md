---
title: "Kompilatora (poziom 3) ostrzeżenie C4023 | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4023
dev_langs: C++
helpviewer_keywords: C4023
ms.assetid: 615d5374-d7c1-42eb-acfd-917c053270c8
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e22ba0ed3d91f75ba73e68817611302d15fa2039
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4023"></a>Kompilator C4023 ostrzegawcze (poziom 3)
"symbol": wskaźnik bazowy przekazany do funkcji bez prototypu: liczba parametrów  
  
 Przekazywanie oparte na wskaźnik do funkcji bez prototypu powoduje, że wskaźnik będą normalizowane może mieć nieprzewidywalne skutki.  
  
 Jeśli używasz prototypu funkcji, które są przekazywane wskaźniki typu based można ustalić to ostrzeżenie.