---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 4) C4233'
title: Ostrzeżenie kompilatora (poziom 4) C4233
ms.date: 10/25/2017
f1_keywords:
- C4233
helpviewer_keywords:
- C4233
ms.assetid: 9aa51fc6-8ef3-43b5-bafb-c9333cf60de3
ms.openlocfilehash: 3e797bcefeaeee615014ea8e0bd109e4cf4ffbef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344019"
---
# <a name="compiler-warning-level-4-c4233"></a>Ostrzeżenie kompilatora (poziom 4) C4233

> użyto niestandardowego rozszerzenia: słowo kluczowe "*Keyword*" jest obsługiwane tylko w języku C++, a nie C

Kompilator skompilowano kod źródłowy jako C, a nie C++, i użyto słowa kluczowego, które jest prawidłowe tylko w języku C++. Kompilator kompiluje plik źródłowy jako C, jeśli rozszerzenie pliku źródłowego to. C lub używasz [/TC](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md).

To ostrzeżenie jest automatycznie podwyższana do błędu. Jeśli chcesz zmodyfikować to zachowanie, użyj [#pragma ostrzeżenie](../../preprocessor/warning.md). Na przykład, aby C4233 na problem z ostrzeżeniem poziomu 4, Dodaj ten wiersz do pliku kodu źródłowego:

```cpp
#pragma warning(4:4233)
```
