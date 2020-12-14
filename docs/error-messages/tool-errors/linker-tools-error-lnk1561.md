---
description: 'Dowiedz się więcej na temat: Błąd narzędzi konsolidatora LNK1561'
title: Błąd narzędzi konsolidatora LNK1561
ms.date: 11/04/2016
f1_keywords:
- LNK1561
helpviewer_keywords:
- LNK1561
ms.assetid: cb0b709b-7c9c-4496-8a4e-9e1e4aefe447
ms.openlocfilehash: b8c99c6e4b016b1eee443cf8f166665f4f9ad894
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97310651"
---
# <a name="linker-tools-error-lnk1561"></a>Błąd narzędzi konsolidatora LNK1561

punkt wejścia musi być zdefiniowany

Konsolidator nie znalazł *punktu wejścia*, funkcja początkowa wywoływana w pliku wykonywalnym. Domyślnie konsolidator szuka `main` `wmain` funkcji lub dla aplikacji konsolowej, `WinMain` funkcji lub dla `wWinMain` aplikacji systemu Windows lub `DllMain` dla biblioteki DLL wymagającej inicjalizacji. Możesz określić inną funkcję przy użyciu opcji konsolidatora [/entry](../../build/reference/entry-entry-point-symbol.md) .

Ten błąd może mieć kilka przyczyn:

- Być może nie dołączono pliku, który definiuje punkt wejścia na liście plików do połączenia. Sprawdź, czy plik zawierający funkcję punktu wejścia jest połączony z Twoją aplikacją.
- Punkt wejścia mógł zostać zdefiniowany przy użyciu nieprawidłowej sygnatury funkcji; na przykład może być błędnie wpisana lub użyto nieprawidłowej wielkości liter dla nazwy funkcji lub określono nieprawidłowy typ zwracany lub typy parametrów.
- Nie określono opcji [/dll](../../build/reference/dll-build-a-dll.md) podczas KOMPILOWANIA biblioteki DLL.
- W przypadku użycia opcji konsolidatora [/entry](../../build/reference/entry-entry-point-symbol.md) może być nieprawidłowo określona nazwa funkcji punktu wejścia.
- Jeśli używasz narzędzia [lib](../../build/reference/lib-reference.md) do KOMPILOWANIA biblioteki DLL, być może został określony plik. def. Jeśli tak, usuń plik. def z kompilacji.

Podczas kompilowania aplikacji konsolidator szuka funkcji punktu wejścia, aby wywołać metodę uruchamiania kodu. Jest to funkcja, która jest wywoływana po załadowaniu aplikacji i zainicjowaniu środowiska uruchomieniowego. Musisz podać funkcję punktu wejścia dla aplikacji lub nie można uruchomić aplikacji. Punkt wejścia jest opcjonalny dla biblioteki DLL. Domyślnie konsolidator szuka funkcji punktu wejścia, która ma jedną z kilku określonych nazw i podpisów, takich jak `int main(int, char**)` . Jako punkt wejścia można określić inną nazwę funkcji, używając opcji konsolidatora/ENTRY.

## <a name="example"></a>Przykład

Poniższy przykład generuje LNK1561:

```cpp
// LNK1561.cpp
// LNK1561 expected
int i;
// add a main function to resolve this error
```
