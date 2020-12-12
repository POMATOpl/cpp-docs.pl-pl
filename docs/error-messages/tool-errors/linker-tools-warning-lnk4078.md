---
description: 'Dowiedz się więcej o: LNK4078 narzędzi KONSOLIDATORA ostrzeżenia narzędzi konsolidatora'
title: Ostrzeżenie LNK4078 narzędzi konsolidatora
ms.date: 11/04/2016
f1_keywords:
- LNK4078
helpviewer_keywords:
- LNK4078
ms.assetid: 5a16796d-6caf-42d9-8f65-b042843eafb8
ms.openlocfilehash: 3fd22316d0775561c18fc2662c2f2ca843e64977
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97210130"
---
# <a name="linker-tools-warning-lnk4078"></a>Ostrzeżenie LNK4078 narzędzi konsolidatora

znaleziono wiele sekcji "name" z różnymi atrybutami

LINK znalazł dwie lub więcej sekcji, które mają taką samą nazwę, ale inne atrybuty.

To ostrzeżenie może być spowodowane przez bibliotekę importu lub plik eksportu, który został utworzony przez poprzednią wersję LINKu lub LIB.

Ponownie utwórz plik i połącz go.

## <a name="example"></a>Przykład

LNK4078 narzędzi KONSOLIDATORA może również być spowodowany zmianą w wyniku zmiany: sekcja o nazwie [init_seg](../../preprocessor/init-seg.md) na x86 została odczytana/zapisu. jest teraz tylko do odczytu.

Poniższy przykład generuje LNK4078 narzędzi KONSOLIDATORA.

```cpp
// LNK4078.cpp
// compile with: /W1
// LNK4078 expected
#include <stdio.h>
#pragma warning(disable : 4075)
typedef void (__cdecl *PF)(void);
int cxpf = 0;   // number of destructors to call
PF pfx[200];   // pointers to destructors.

struct A { A() {} };

int myexit (PF pf) { return 0; }

#pragma section(".mine$a", read, write)
// try the following line instead
// #pragma section(".mine$a", read)
__declspec(allocate(".mine$a")) int ii = 1;

#pragma section(".mine$z", read, write)
// try the following line instead
// #pragma section(".mine$z", read)
__declspec(allocate(".mine$z")) int i = 1;

#pragma data_seg()
#pragma init_seg(".mine$m", myexit)
A bbbb;
A cccc;
int main() {}
```
