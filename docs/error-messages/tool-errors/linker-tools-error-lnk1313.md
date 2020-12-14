---
description: 'Dowiedz się więcej na temat: Błąd narzędzi konsolidatora LNK1313'
title: Błąd narzędzi konsolidatora LNK1313
ms.date: 11/04/2016
f1_keywords:
- LNK1313
helpviewer_keywords:
- LNK1313
ms.assetid: 5df0b72e-bb3f-428c-8d84-6084238f9827
ms.openlocfilehash: 1c10038def9a448645e80ae10fc47d4372769b58
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97310728"
---
# <a name="linker-tools-error-lnk1313"></a>Błąd narzędzi konsolidatora LNK1313

> Wykryto IJW/moduł macierzysty; nie można połączyć z czystymi modułami

## <a name="remarks"></a>Uwagi

Bieżąca wersja Visual C++ nie obsługuje łączenia natywnych lub mieszanych plików. obj z atrybutami. obj, które zostały skompilowane z **/CLR: Pure**.

**/CLR: Pure** kompilator Option jest przestarzały w programie visual Studio 2015 i nieobsługiwany w programie visual Studio 2017.

## <a name="examples"></a>Przykłady

```cpp
// LNK1313.cpp
// compile with: /c /clr:pure
// a pure module
int main() {}
```

```cpp
// LNK1313_b.cpp
// compile with: /c /clr
// an IJW module
void test(){}
```

Poniższy przykład generuje LNK1313.

```cpp
// LNK1313_c.cpp
// compile with: /link LNK1313.obj LNK1313_b.obj
// LNK1313 warning expected
```
