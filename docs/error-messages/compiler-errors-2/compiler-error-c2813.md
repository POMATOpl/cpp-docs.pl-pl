---
description: 'Dowiedz się więcej o: błąd kompilatora C2813'
title: Błąd kompilatora C2813
ms.date: 11/04/2016
f1_keywords:
- C2813
helpviewer_keywords:
- C2813
ms.assetid: 6cf2135f-7b82-42d1-909a-5e864308a09c
ms.openlocfilehash: 51de4100da8c0dd1a3b2ad1857799769b2abea24
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278405"
---
# <a name="compiler-error-c2813"></a>Błąd kompilatora C2813

\#import nie jest obsługiwany z/MP

C2813 jest emitowany, jeśli w poleceniu kompilatora określono opcję kompilatora **/MP** i dwa lub więcej plików do skompilowania, a co najmniej jeden plik zawiera dyrektywę preprocesora [#import](../../preprocessor/hash-import-directive-cpp.md) . Dyrektywa [#import](../../preprocessor/hash-import-directive-cpp.md) generuje klasy języka C++ z typów w określonej bibliotece typów, a następnie zapisuje te klasy do dwóch plików nagłówkowych. Dyrektywa [#import](../../preprocessor/hash-import-directive-cpp.md) nie jest obsługiwana, ponieważ jeśli wiele jednostek kompilacji zaimportuje tę samą bibliotekę typów, te jednostki powodują konflikt w przypadku próby zapisu tych samych plików nagłówkowych w tym samym czasie.

Ten błąd kompilatora i opcja kompilatora **/MP** są nowe w programie Visual Studio 2008.

## <a name="example"></a>Przykład

Poniższy przykład generuje C2813. Wiersz polecenia w komentarzu "Kompiluj z:" wskazuje kompilatorowi, aby użyć opcji kompilatora **/MP** i **/c** do kompilowania kilku plików. Co najmniej jeden z plików zawiera dyrektywę [#import](../../preprocessor/hash-import-directive-cpp.md) . Ten sam plik jest używany dwa razy do testowania tego przykładu.

```cpp
// C2813.cpp
// compile with: /MP /c C2813.cpp C2813.cpp
#import "C:\windows\system32\stdole2.tlb"   // C2813
int main()
{
}
```
