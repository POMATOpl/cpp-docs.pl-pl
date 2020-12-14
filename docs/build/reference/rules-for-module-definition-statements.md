---
description: 'Dowiedz się więcej o: regułach dla instrukcji Module-Definition'
title: Zasady dla instrukcji definicji modułu
ms.date: 11/04/2016
f1_keywords:
- .def
helpviewer_keywords:
- module definition files, statement syntax
- module definition files
ms.assetid: f65cd3a7-65d7-4d06-939f-a8b1ecd50f2d
ms.openlocfilehash: bca1f279a9a93690edeaabc2264d1cfe869b3e80
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225001"
---
# <a name="rules-for-module-definition-statements"></a>Zasady dla instrukcji definicji modułu

Poniższe reguły składni mają zastosowanie do wszystkich instrukcji w pliku. def. Inne reguły, które mają zastosowanie do określonych instrukcji, są opisane z każdą instrukcją.

- W instrukcjach, słowach kluczowych atrybutów i identyfikatorach określonych przez użytkownika jest uwzględniana wielkość liter.

- Długie nazwy plików zawierające spacje lub średniki (;) musi być ujęty w cudzysłów (").

- Użyj co najmniej jednej spacji, tabulatorów lub znaków nowego wiersza do oddzielenia słowa kluczowego instrukcji od jego argumentów oraz do oddzielenia instrukcji od siebie. Dwukropek (:) lub znak równości (=) oznaczający, że argument jest otoczony zerem lub więcej spacjami, tabulatorami lub znakami nowego wiersza.

- Instrukcja **name** lub **Library** , jeśli jest używana, musi poprzedzać wszystkie inne instrukcje.

- Instrukcje **sekcja** i **eksporty** mogą pojawić się więcej niż raz w pliku. def. Każda instrukcja może przyjmować wiele specyfikacji, które muszą być oddzielone co najmniej jedną spacją, tabulatorami lub znakami nowego wiersza. Słowo kluczowe instrukcji musi występować raz przed pierwszą specyfikacją i może zostać powtórzone przed każdą dodatkową specyfikacją.

- Wiele instrukcji ma odpowiednik opcji wiersza polecenia. Więcej szczegółów można znaleźć w opisie odpowiedniej opcji LINKu.

- Komentarze w pliku DEF są wyznaczane za pomocą średnika (;) na początku każdego wiersza komentarza. Komentarz nie może udostępniać wiersza instrukcji, ale może występować między specyfikacjami w instrukcji wielowierszowej. (**Sekcje** i **eksporty** są instrukcje wielowierszowe).

- Argumenty liczbowe są określone w podstawowym 10 lub szesnastkowym.

- Jeśli argument ciągu pasuje do [słowa zastrzeżonego](reserved-words.md), musi być ujęty w znaki podwójnego cudzysłowu (").

## <a name="see-also"></a>Zobacz też

[Definicja modułu (. Def) — pliki](module-definition-dot-def-files.md)
