---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 4) C4431'
title: Ostrzeżenie kompilatora (poziom 4) C4431
ms.date: 11/04/2016
f1_keywords:
- C4431
helpviewer_keywords:
- C4431
ms.assetid: 58434ab6-dd8d-427b-953a-602fb7453ae6
ms.openlocfilehash: 47e83f5e49ec8a4e54f4cda62267d01bd42f1ce7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97251495"
---
# <a name="compiler-warning-level-4-c4431"></a>Ostrzeżenie kompilatora (poziom 4) C4431

brak specyfikatora typu — zakładany int. Uwaga: C nie obsługuje już domyślnego int

Ten błąd może zostać wygenerowany w wyniku działania kompilatora, który został wykonany dla programu Visual Studio 2005: Visual C++ nie tworzy już identyfikatorów bez typu jako int. Typ identyfikatora musi być jawnie określony.

To ostrzeżenie jest domyślnie wyłączone. Aby uzyskać więcej informacji [, zobacz ostrzeżenia kompilatora, które są domyślnie wyłączone](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

## <a name="example"></a>Przykład

Poniższy przykład generuje C4431.

```c
// C4431.c
// compile with: /c /W4
#pragma warning(default:4431)
i;   // C4431
int i;   // OK
```
