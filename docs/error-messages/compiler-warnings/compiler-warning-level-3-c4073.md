---
title: Kompilatora (poziom 3) ostrzeżenie C4073 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4073
dev_langs:
- C++
helpviewer_keywords:
- C4073
ms.assetid: 50081a6e-6acd-45ff-8484-9b1ea926cc5c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 93e3aae403b8dee41ef31c5d0c44e16702bc363b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-3-c4073"></a>Kompilator C4073 ostrzegawcze (poziom 3)
Inicjatory umieszczono w obszarze inicjalizacyjnym biblioteki  
  
 Tylko innych firm biblioteki Programiści powinni używać obszarze inicjalizacyjnym biblioteki, które jest określone przez [#pragma init_seg](../../preprocessor/init-seg.md). Poniższy przykład generuje C4073:  
  
```  
// C4073.cpp  
// compile with: /W3  
#pragma init_seg(lib)   // C4073  
  
// try this line to resolve the warning  
// #pragma init_seg(user)  
  
int main() {  
}  
```