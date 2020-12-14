---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 4) C4001'
title: Ostrzeżenie kompilatora (poziom 4) C4001
ms.date: 11/04/2016
f1_keywords:
- C4001
helpviewer_keywords:
- C4001
ms.assetid: 414a47fe-d597-425e-9374-6a569231dc0a
ms.openlocfilehash: c28c1391b120983d72dc6e5b7a96faa937ee2598
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262220"
---
# <a name="compiler-warning-level-4-c4001"></a>Ostrzeżenie kompilatora (poziom 4) C4001

użyto niestandardowego rozszerzenia "Single line Comment"

> [!NOTE]
> To ostrzeżenie jest usuwane w programie Visual Studio 2017 w wersji 15,5, ponieważ Komentarze jednowierszowe są standardowe w C99.

Komentarze jednowierszowe są standardami w językach C++ i standard w języku C, zaczynając od C99.
W obszarze ścisła zgodność ANSI ([/za](../../build/reference/za-ze-disable-language-extensions.md)), pliki języka C, które zawierają jednowierszowe komentarze, generują C4001 z powodu użycia niestandardowego rozszerzenia. Ponieważ Komentarze jednowierszowe są standardowe w języku C++, pliki C zawierające Komentarze jednowierszowe nie generują C4001 podczas kompilowania przy użyciu rozszerzeń Microsoft (/ze).

## <a name="example"></a>Przykład

Aby wyłączyć ostrzeżenie, Usuń komentarz [#pragma ostrzeżenie (Wyłącz: 4001)](../../preprocessor/warning.md).

```cpp
// C4001.cpp
// compile with: /W4 /Za /TC
// #pragma warning(disable:4001)
int main()
{
   // single-line comment in main
   // C4001
}
```
