---
description: 'Dowiedz się więcej na temat: Błąd narzędzi konsolidatora LNK2028'
title: Błąd narzędzi konsolidatora LNK2028
ms.date: 11/04/2016
f1_keywords:
- LNK2028
helpviewer_keywords:
- LNK2028
ms.assetid: e2b03293-6066-464d-a050-ce747bcf7f0e
ms.openlocfilehash: 31b20cc572a44b1260f58eb03519b60050c0246c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97275727"
---
# <a name="linker-tools-error-lnk2028"></a>Błąd narzędzi konsolidatora LNK2028

"*exported_function*" (*decorated_name*) przywoływany w funkcji "*function_containing_function_call*" (*decorated_name*)

## <a name="remarks"></a>Uwagi

Podczas próby zaimportowania funkcji natywnej do czystego obrazu należy pamiętać, że niejawne konwencje wywoływania różnią się między natywnymi i czystymi kompilacjami.

**/CLR: Pure** kompilator Option jest przestarzały w programie visual Studio 2015 i nieobsługiwany w programie visual Studio 2017.

## <a name="examples"></a>Przykłady

Ten przykładowy kod generuje składnik z wyeksportowaną, natywną funkcją, której Konwencja wywołania jest niejawnie [__cdecl](../../cpp/cdecl.md).

```cpp
// LNK2028.cpp
// compile with: /LD
__declspec(dllexport) int func() {
   return 3;
}
```

Poniższy przykład tworzy czysty klient korzystający z funkcji natywnej. Jednakże Konwencja wywoływania w opcji **/CLR: Pure** jest [__clrcall](../../cpp/clrcall.md). Poniższy przykład generuje LNK2028.

```cpp
// LNK2028_b.cpp
// compile with: /clr:pure lnk2028.lib
// LNK2028 expected
int func();

int main() {
   return func();
}
```
