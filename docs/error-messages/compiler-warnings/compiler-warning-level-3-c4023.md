---
title: Kompilatora (poziom 3) ostrzeżenie C4023 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4023
dev_langs:
- C++
helpviewer_keywords:
- C4023
ms.assetid: 615d5374-d7c1-42eb-acfd-917c053270c8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 213d72e39575b447787c3e0ead7910baedc8e815
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33290000"
---
# <a name="compiler-warning-level-3-c4023"></a>Kompilator C4023 ostrzegawcze (poziom 3)
"symbol": wskaźnik bazowy przekazany do funkcji bez prototypu: liczba parametrów  
  
 Przekazywanie oparte na wskaźnik do funkcji bez prototypu powoduje, że wskaźnik będą normalizowane może mieć nieprzewidywalne skutki.  
  
 Jeśli używasz prototypu funkcji, które są przekazywane wskaźniki typu based można ustalić to ostrzeżenie.