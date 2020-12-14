---
description: 'Dowiedz się więcej na temat: polecenia standardowe'
title: Polecenia standardowe
ms.date: 11/04/2016
helpviewer_keywords:
- File menu
- identifiers [MFC], command IDs
- command IDs, standard commands
- OLE commands
- commands [MFC], standard
- standard command IDs
- Window menu commands
- standard commands
- View menu commands
- Edit menu standard commands
- Help [MFC], menus
- programmer-defined IDs [MFC]
ms.assetid: 88cf3ab4-79b3-4ac6-9365-8ac561036fbf
ms.openlocfilehash: 09c0afecf5b34565c3ab14e276c7c43a20189a0a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216746"
---
# <a name="standard-commands"></a>Polecenia standardowe

Struktura definiuje wiele komunikatów poleceń standardowych. Identyfikatory tych poleceń zazwyczaj przyjmują postać:

*Element* **ID_** *_*

gdzie *Source* jest zwykle nazwą menu i *element* jest elementem menu. Na przykład identyfikator polecenia dla nowego polecenia w menu plik jest ID_FILE_NEW. Identyfikatory poleceń standardowych są pokazywane pogrubioną czcionką w dokumentacji. Identyfikatory zdefiniowane przez programistę są wyświetlane w czcionce, która różni się od otaczającego tekstu.

Poniżej wymieniono niektóre z najważniejszych poleceń, które są obsługiwane:

*Polecenia menu plik*<br/>
Nowe, otwarte, zamknięte, Zapisz, Zapisz jako, Konfiguracja strony, konfiguracja drukowania, drukowanie, Podgląd wydruku, wyjście i ostatnio używane pliki.

*Polecenia menu Edytuj*<br/>
Wyczyść, Wyczyść wszystko, Kopiuj, Wytnij, Znajdź, wklej, powtarzaj, Zamień, zaznacz wszystko, Cofnij i wykonaj ponownie.

*Polecenia menu Widok*<br/>
Pasek narzędzi i pasek stanu.

*Polecenia menu okna*<br/>
Nowy, Rozmieść, Kaskada, Podziel w poziomie, Podziel w pionie i Podziel.

*Polecenia menu Pomoc*<br/>
Indeks, korzystanie z pomocy i informacje o programie.

*Polecenia OLE (menu Edycja)*<br/>
Wstaw nowy obiekt, Edytuj linki, wklejaj łącze, wklejaj obiekty specjalne i *TypeName* (polecenia czasownikowe).

Struktura zapewnia różne poziomy obsługi tych poleceń. Niektóre polecenia są obsługiwane tylko jako zdefiniowane identyfikatory poleceń, a inne są obsługiwane przez szczegółowe implementacje. Na przykład struktura implementuje polecenie Otwórz w menu plik, tworząc nowy obiekt dokumentu, wyświetlając otwarte okno dialogowe i otwierając i odczytując plik. Z kolei należy samodzielnie zaimplementować polecenia w menu Edytuj, ponieważ polecenia takie jak ID_EDIT_COPY zależą od charakteru kopiowanych danych.

Aby uzyskać więcej informacji na temat obsługiwanych poleceń i dostępnego poziomu implementacji, zobacz [Uwagi techniczne 22](../mfc/tn022-standard-commands-implementation.md). Standardowe polecenia są zdefiniowane w pliku plik AFXRES. H.

## <a name="see-also"></a>Zobacz też

[Obiekty interfejsu użytkownika i identyfikatory poleceń](../mfc/user-interface-objects-and-command-ids.md)
