---
description: 'Dowiedz się więcej o: LNK4253 narzędzi KONSOLIDATORA ostrzeżenia narzędzi konsolidatora'
title: Ostrzeżenie LNK4253 narzędzi konsolidatora
ms.date: 11/04/2016
f1_keywords:
- LNK4253
helpviewer_keywords:
- LNK4253
ms.assetid: ec7433a9-aa9c-495a-a9f2-075e7bc3e7bc
ms.openlocfilehash: 764d7698da8d724842b8387c9c4356bfce951079
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97244489"
---
# <a name="linker-tools-warning-lnk4253"></a>Ostrzeżenie LNK4253 narzędzi konsolidatora

sekcja "Section1" nie została scalona z "section2"; scalono już do "section3"

Konsolidator wykrył wiele, powodujących konflikt żądań scalania. Konsolidator zignoruje jeden z żądań.

Napotkano opcję **/merge** lub dyrektywę, a `from` sekcja została już scalona z inną sekcją ze względu na poprzednią opcję lub dyrektywę **/merge** (lub z powodu niejawnego scalania z konsolidatora).

Aby rozwiązać LNK4253 narzędzi KONSOLIDATORA, Usuń jedno z żądań scalenia.

W przypadku urządzeń docelowych z procesorami x86 i Windows CE (ARM, MIPS, SH4 i kciuk) z Visual C++,. Sekcja CRT jest teraz tylko do odczytu. Jeśli kod zależy od poprzedniego zachowania (. Sekcje CRT są do odczytu/zapisu, ale można zobaczyć nieoczekiwane zachowanie.

Aby uzyskać więcej informacji, zobacz,

- [/MERGE (Połącz sekcje)](../../build/reference/merge-combine-sections.md)

- [komentarz (C/C++)](../../preprocessor/comment-c-cpp.md)

## <a name="example"></a>Przykład

W poniższym przykładzie konsolidator jest polecany do scalenia `.rdata` części dwa razy, ale w różnych sekcjach. Poniższy przykład generuje LNK4253 narzędzi KONSOLIDATORA.

```cpp
// LNK4253.cpp
// compile with: /W1 /link /merge:.rdata=text2
// LNK4253 expected
#pragma comment(linker, "/merge:.rdata=.text")
int main() {}
```
