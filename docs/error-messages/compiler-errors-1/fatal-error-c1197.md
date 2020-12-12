---
description: 'Dowiedz się więcej na temat: błąd krytyczny C1197'
title: Błąd krytyczny C1197
ms.date: 11/04/2016
f1_keywords:
- C1197
helpviewer_keywords:
- C1197
ms.assetid: 22b801b7-e792-41f6-a461-973c03c69f25
ms.openlocfilehash: c61cbd71fa8f17dc787fd9ee5eabd0f073aafb39
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97268174"
---
# <a name="fatal-error-c1197"></a>Błąd krytyczny C1197

nie można odwołać się do "mscorlib.dll_1", ponieważ do programu istnieje już odwołanie "mscorlib.dll_2"

Kompilator jest zgodny z wersją środowiska uruchomieniowego języka wspólnego.  Jednak podjęto próbę odwołania się do wersji pliku środowiska uruchomieniowego języka wspólnego z poprzedniej wersji.

Aby rozwiązać ten problem, należy tylko odwoływać się do plików z wersji środowiska uruchomieniowego języka wspólnego, która została dostarczona z wersją Visual C++ kompilowaną za pomocą programu.

## <a name="example"></a>Przykład

Poniższy przykład generuje C1197:

```cpp
// C1197.cpp
// compile with: /clr /c
// processor: x86
#using "C:\Windows\Microsoft.NET\Framework\v1.1.4322\mscorlib.dll"   // C1197
// try the following line instead
// #using "mscorlib.dll"
```
