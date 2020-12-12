---
description: 'Dowiedz się więcej na temat: błąd krytyczny C1190'
title: Błąd krytyczny C1190
ms.date: 11/04/2016
f1_keywords:
- C1190
helpviewer_keywords:
- C1190
ms.assetid: dee2266d-6c40-4f6e-91db-f01e65f8d2bc
ms.openlocfilehash: e351a04d548816999d61973276203d34745c0a75
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123607"
---
# <a name="fatal-error-c1190"></a>Błąd krytyczny C1190

zarządzany kod źródłowy wymaga opcji "/CLR"

Używasz konstrukcji środowiska CLR, ale nie określono opcji **/CLR**.

Aby uzyskać więcej informacji, zobacz [/CLR (Kompilacja środowiska uruchomieniowego języka wspólnego)](../../build/reference/clr-common-language-runtime-compilation.md).

Poniższy przykład generuje C1190:

```cpp
// C1190.cpp
// compile with: /c
__gc class A {};   // C1190
ref class A {};
```
