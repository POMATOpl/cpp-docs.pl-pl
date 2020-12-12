---
description: 'Dowiedz się więcej o: LNK4254 narzędzi KONSOLIDATORA ostrzeżenia narzędzi konsolidatora'
title: Ostrzeżenie LNK4254 narzędzi konsolidatora
ms.date: 11/04/2016
f1_keywords:
- LNK4254
helpviewer_keywords:
- LNK4254
ms.assetid: 6f41dfb3-ca21-40d3-bac7-b637e578efa4
ms.openlocfilehash: 410a904af6af2015a817ac9e254dff7f09811b72
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97244475"
---
# <a name="linker-tools-warning-lnk4254"></a>Ostrzeżenie LNK4254 narzędzi konsolidatora

sekcja "Section1" (offset) została scalona z elementem "section2" (offset) z różnymi atrybutami

Zawartość jednej sekcji została scalona w innej, ale atrybuty obu sekcji są różne. Program może dać nieoczekiwane wyniki. Na przykład dane, które mają być tylko do odczytu, mogą teraz znajdować się w sekcji możliwej do zapisu.

Aby rozwiązać LNK4254 narzędzi KONSOLIDATORA, zmodyfikuj lub Usuń żądanie scalenia.

W przypadku urządzeń docelowych z procesorami x86 i Windows CE (ARM, MIPS, SH4 i kciuk) z Visual C++,. Sekcja CRT jest tylko do odczytu. Jeśli kod zależy od poprzedniego zachowania (. Sekcje CRT są do odczytu/zapisu, ale można zobaczyć nieoczekiwane zachowanie.

Aby uzyskać więcej informacji, zobacz,

- [/MERGE (Połącz sekcje)](../../build/reference/merge-combine-sections.md)

- [komentarz (C/C++)](../../preprocessor/comment-c-cpp.md)

## <a name="example"></a>Przykład

Poniższy przykład generuje LNK4254 narzędzi KONSOLIDATORA.

```cpp
// LNK4254.cpp
// compile with: /W1 /link /WX
// LNK4254 expected
#pragma comment(linker, "/merge:.data=.text")
int main() {}
```
