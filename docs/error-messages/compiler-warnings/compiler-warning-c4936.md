---
description: 'Dowiedz się więcej na temat: Ostrzeżenie kompilatora C4936'
title: Ostrzeżenie kompilatora C4936
ms.date: 11/04/2016
f1_keywords:
- C4936
helpviewer_keywords:
- C4936
ms.assetid: 6676de35-bf1b-4d0b-a70f-b5734130336c
ms.openlocfilehash: e12cb789d3d008ec61672591cde78f1b7dc61da6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314987"
---
# <a name="compiler-warning-c4936"></a>Ostrzeżenie kompilatora C4936

> Ta __declspec jest obsługiwana tylko wtedy, gdy skompilowano z opcją/CLR lub/CLR: Pure

## <a name="remarks"></a>Uwagi

**/CLR: Pure** kompilator Option jest przestarzały w programie visual Studio 2015 i nieobsługiwany w programie visual Studio 2017.

**`__declspec`** Użyto modyfikatora, ale ten **`__declspec`** modyfikator jest prawidłowy tylko wtedy, gdy jest kompilowany z jedną z opcji [/CLR](../../build/reference/clr-common-language-runtime-compilation.md) .

Aby uzyskać więcej informacji, zobacz temat [AppDomain](../../cpp/appdomain.md) i [Process](../../cpp/process.md).

C4936 jest zawsze wystawiony jako błąd.  C4936 można wyłączyć za pomocą dyrektywy pragma [ostrzeżenia](../../preprocessor/warning.md) .

## <a name="example"></a>Przykład

Poniższy przykład generuje C4936:

```cpp
// C4936.cpp
// compile with: /c
// #pragma warning (disable : 4936)
__declspec(process) int i;   // C4936
__declspec(appdomain) int j;   // C4936
```
