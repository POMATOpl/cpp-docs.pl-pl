---
title: C2307 błąd kompilatora | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2307
dev_langs:
- C++
helpviewer_keywords:
- C2307
ms.assetid: ce6c8033-a673-4679-9883-bedec36ae385
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7136b5b49371c9181780bfa4a7bc7a17416a7ad2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2307"></a>C2307 błąd kompilatora
pragma "pragma" musi znajdować się poza funkcją Jeśli włączono kompilację przyrostową  
  
 Należy umieścić `data_seg` pragma pomiędzy funkcjami, jeśli używasz kompilacji przyrostowej.