---
title: C2834 błąd kompilatora | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C2834
dev_langs:
- C++
helpviewer_keywords:
- C2834
ms.assetid: 28f9f6eb-ab2a-4e64-aaaa-9d14f955de41
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 616bb6fe351c7575bf04f319390d0a3cfcd3cc8a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2834"></a>C2834 błąd kompilatora
"operator operator" musi być globalnie kwalifikowany  
  
 `new` i `delete` operatory są powiązane z klasy, których są one przechowywane. Rozpoznawanie zakresów nie będzie można wybrać wersję `new` lub `delete` z innej klasy. Aby zaimplementować wiele form `new` lub `delete` operatora, utworzyć wersję operatora z bardzo formalnych parametrów.