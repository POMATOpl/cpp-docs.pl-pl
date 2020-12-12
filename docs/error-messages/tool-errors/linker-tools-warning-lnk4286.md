---
description: 'Dowiedz się więcej o: LNK4286 ostrzeżenia narzędzi konsolidatora'
title: Ostrzeżenie narzędzi konsolidatora LNK4286
ms.date: 04/15/2019
f1_keywords:
- LNK4286
helpviewer_keywords:
- LNK4286
ms.openlocfilehash: 6a1e397967857ae3f982bf8f5e55f4bf74c9abe4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97244449"
---
# <a name="linker-tools-warning-lnk4286"></a>Ostrzeżenie narzędzi konsolidatora LNK4286

> Symbol "*symbol*" zdefiniowany w elemencie "*filename_1. obj*" został zaimportowany przez element "*filename_2. obj*"

[__declspec (dllimport)](../../cpp/dllexport-dllimport.md) została określona dla *symbolu* , chociaż symbol jest zdefiniowany w pliku obiektu *filename_1. obj* w tym samym obrazie. Usuń `__declspec(dllimport)` modyfikator, aby rozwiązać to ostrzeżenie.

## <a name="remarks"></a>Uwagi

Ostrzeżenie LNK4286 to bardziej ogólna wersja [narzędzi konsolidatora LNK4217 narzędzi konsolidatora](linker-tools-warning-lnk4217.md). Konsolidator generuje ostrzeżenie LNK4286, gdy może rozpoznać plik obiektu, do którego odwołuje się symbol, ale nie funkcję.

Aby rozwiązać LNK4286, Usuń `__declspec(dllimport)` modyfikator deklaracji z deklaracji do przodu *symboli* , do której odwołuje się element *filename_2. obj*.

Mimo że ostatni wygenerowany kod działa prawidłowo, kod wygenerowany do wywołania zaimportowanej funkcji jest mniej wydajny niż bezpośrednie wywoływanie funkcji. To ostrzeżenie nie pojawia się podczas kompilowania przy użyciu opcji [/CLR](../../build/reference/clr-common-language-runtime-compilation.md) .

Aby uzyskać więcej informacji na temat importowania i eksportowania deklaracji danych, zobacz [dllexport, dllimport](../../cpp/dllexport-dllimport.md).

## <a name="see-also"></a>Zobacz też

[Ostrzeżenie narzędzi konsolidatora LNK4049 narzędzi KONSOLIDATORA](linker-tools-warning-lnk4049.md) \
[Ostrzeżenie narzędzi konsolidatora LNK4217 narzędzi KONSOLIDATORA](linker-tools-warning-lnk4217.md) \
[dllexport, dllimport](../../cpp/dllexport-dllimport.md)
