---
title: Błąd kompilatora C2692 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2692
dev_langs:
- C++
helpviewer_keywords:
- C2692
ms.assetid: 02ade3b4-b757-448b-b065-d7d71bc3f441
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 03a9006889c5853e77b5603484ea9d18f2474241
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46088374"
---
# <a name="compiler-error-c2692"></a>Błąd kompilatora C2692

"nazwa_funkcji": wymagano w pełni prototypowanych funkcji w kompilatorze języka C z "/ clr" opcja

W przypadku kodu zarządzanego kompilowania dla platformy .NET, kompilator języka C wymaga deklaracji funkcji ANSI. Ponadto, jeśli funkcja nie przyjmuje żadnych parametrów, go jawnie zadeklarować `void` jako typ parametru.