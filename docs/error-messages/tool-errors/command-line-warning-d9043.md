---
description: 'Dowiedz się więcej na temat: Command-Line Warning D9043'
title: Ostrzeżenie D9043 dla wiersza polecenia
ms.date: 11/04/2016
f1_keywords:
- D9043
helpviewer_keywords:
- D9043
ms.assetid: 9263e28d-217b-414c-bfb6-86efd3c27a77
ms.openlocfilehash: ac61626f21465056ea96efe784e19405481f1b0f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97119752"
---
# <a name="command-line-warning-d9043"></a>Ostrzeżenie D9043 dla wiersza polecenia

Nieprawidłowa wartość "warning_level" dla "compiler_option"; Zakładając, że "4999"; Ostrzeżenia analizy kodu nie są skojarzone z poziomami ostrzeżeń

## <a name="example"></a>Przykład

Poniższy przykład generuje C9043.

```cpp
// D9043.cpp
// compile with: /analyze /w16001
// D9043 warning expected
int main() {}
```
