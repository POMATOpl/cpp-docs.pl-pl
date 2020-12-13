---
description: 'Dowiedz się więcej o: LNK4217 narzędzi KONSOLIDATORA ostrzeżenia narzędzi konsolidatora'
title: Ostrzeżenie LNK4217 narzędzi konsolidatora
ms.date: 07/23/2019
f1_keywords:
- LNK4217
helpviewer_keywords:
- LNK4217
ms.assetid: 280dc03e-5933-4e8d-bb8c-891fbe788738
ms.openlocfilehash: d3ace3586cf11da4dd87f00a58543c6d60fc1a10
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97150595"
---
# <a name="linker-tools-warning-lnk4217"></a>Ostrzeżenie LNK4217 narzędzi konsolidatora

> Symbol "*symbol*" zdefiniowany w elemencie "*filename_1. obj*" został zaimportowany przez element "*filename_2. obj*" w funkcji "*Function*"

[__declspec (dllimport)](../../cpp/dllexport-dllimport.md) została określona dla symbolu, chociaż symbol jest zdefiniowany w pliku obiektu w tym samym obrazie. Usuń `__declspec(dllimport)` modyfikator, aby rozwiązać to ostrzeżenie.

## <a name="remarks"></a>Uwagi

*symbol* jest nazwą symbolu, który jest zdefiniowany w obrazie. *Funkcja* jest funkcją, która importuje symbol.

To ostrzeżenie nie pojawia się podczas kompilowania przy użyciu opcji [/CLR](../../build/reference/clr-common-language-runtime-compilation.md) .

LNK4217 narzędzi KONSOLIDATORA może również wystąpić, jeśli spróbujesz połączyć dwa moduły jednocześnie, gdy zamiast tego należy skompilować drugi moduł z biblioteką importu pierwszego modułu.

```cpp
// main.cpp
__declspec(dllimport) void func();

int main()
{
    func();
    return 0;
}

```

A następnie

```cpp
// tt.cpp
// compile with: /c
void func() {}
```

Próba skompilowania tych dwóch modułów, jak pokazano w tym miejscu, spowoduje LNK4217 narzędzi KONSOLIDATORA:

```cmd
cl.exe /c main.cpp tt.cpp
link.exe main.obj tt.obj
```

Aby naprawić ten błąd, po skompilowaniu dwóch plików, należy przekazać TT. obj do lib.exe, aby utworzyć plik. lib, a następnie połączyć Main. obj z TT. lib, jak pokazano poniżej:

```cmd
cl.exe /c main.cpp tt.cpp
lib.exe tt.obj /export:func /def
link.exe main.obj tt.lib
```

## <a name="see-also"></a>Zobacz też

[Ostrzeżenie narzędzi konsolidatora LNK4049 narzędzi KONSOLIDATORA](linker-tools-warning-lnk4049.md) \
[Ostrzeżenie narzędzi konsolidatora LNK4286](linker-tools-warning-lnk4286.md) \
[dllexport, dllimport](../../cpp/dllexport-dllimport.md)
