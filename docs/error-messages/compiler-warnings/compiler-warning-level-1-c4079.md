---
title: Kompilator ostrzeżenie (poziom 1) C4079 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4079
dev_langs:
- C++
helpviewer_keywords:
- C4079
ms.assetid: 549759f0-e168-47e9-8c9a-de93ac843689
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7de3eca54ddadd5c7a1687d4f7ebc5f6359a464e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46074012"
---
# <a name="compiler-warning-level-1-c4079"></a>Kompilator ostrzeżenie (poziom 1) C4079

Nieoczekiwany token 'token'

Token separatora nieoczekiwany występuje na liście argumentów pragmy. W pozostałej części pragma została zignorowana.

Poniższy przykład spowoduje wygenerowanie C4079:

```
// C4079.cpp
// compile with: /W1
#pragma warning(disable : 4081)
#pragma pack(c,16)   // C4079

int main() {
}
```