---
description: 'Dowiedz się więcej na temat: Błąd narzędzi konsolidatora LNK1179'
title: Błąd narzędzi konsolidatora LNK1179
ms.date: 11/04/2016
f1_keywords:
- LNK1179
helpviewer_keywords:
- LNK1179
ms.assetid: 4b1536d7-0d3d-4f29-a9c1-6fa5cf6cb665
ms.openlocfilehash: 691476eeffadece2436518c5249ca523adca51c2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97253445"
---
# <a name="linker-tools-error-lnk1179"></a>Błąd narzędzi konsolidatora LNK1179

nieprawidłowy lub uszkodzony plik: zduplikowana COMDAT "filename"

Moduł obiektu zawiera dwa lub więcej COMDAT o tej samej nazwie.

Ten błąd może być spowodowany użyciem wartości [/h](../../build/reference/h-restrict-length-of-external-names.md), która ogranicza długość nazw zewnętrznych i [/Gy](../../build/reference/gy-enable-function-level-linking.md), które pakiety funkcje w COMDAT.

## <a name="example"></a>Przykład

W poniższym kodzie `function1` i `function2` są identyczne w pierwszych osiem znaków. Kompilowanie za pomocą **/Gy** i **/H8** powoduje utworzenie błędu łącza.

```cpp
void function1(void);
void function2(void);

int main() {
    function1();
    function2();
}

void function1(void) {}
void function2(void) {}
```
