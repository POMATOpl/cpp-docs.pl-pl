---
title: C2873 błąd kompilatora | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2873
dev_langs:
- C++
helpviewer_keywords:
- C2873
ms.assetid: 7a10036b-400e-4364-bd2f-dcd7370c5e28
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 94a04d650729bdda949754c5070a6c307d390929
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33244381"
---
# <a name="compiler-error-c2873"></a>C2873 błąd kompilatora
"symbol": symbol nie może zostać użyty w deklaracji using  
  
 A `using` brakuje dyrektywy [przestrzeni nazw](../../cpp/namespaces-cpp.md) — słowo kluczowe. Powoduje to, że kompilator błędnie interpretuje kodu jako [za pomocą deklaracji](../../cpp/using-declaration.md) zamiast [dyrektywa using](../../cpp/namespaces-cpp.md#using_directives).