---
description: 'Dowiedz się więcej o: błąd kompilatora C2692'
title: Błąd kompilatora C2692
ms.date: 11/04/2016
f1_keywords:
- C2692
helpviewer_keywords:
- C2692
ms.assetid: 02ade3b4-b757-448b-b065-d7d71bc3f441
ms.openlocfilehash: 5a9666bf437d65c54d0cb8c460054b2b3ebd0b55
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326687"
---
# <a name="compiler-error-c2692"></a>Błąd kompilatora C2692

"function_name": funkcje w pełni prototypowe wymagane w kompilatorze języka C z opcją "/CLR"

Podczas kompilowania kodu zarządzanego .NET kompilator języka C wymaga deklaracji funkcji ANSI. Ponadto, jeśli funkcja nie przyjmuje żadnych parametrów, musi jawnie zadeklarować **`void`** jako typ parametru.
