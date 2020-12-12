---
description: 'Dowiedz się więcej na temat: Przewodnik: Testowanie projektu (C++)'
title: 'Wskazówki: testowanie projektu (C++)'
ms.date: 04/25/2019
helpviewer_keywords:
- project testing [C++]
- testing projects
- projects [C++], testing
ms.assetid: 88cdd377-c5c8-4201-889d-32f5653ebead
ms.openlocfilehash: 0469f6c161689d2638cfb206c91c2530b72cd00b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334767"
---
# <a name="walkthrough-testing-a-project-c"></a>Wskazówki: testowanie projektu (C++)

Gdy uruchamiasz program w trybie debugowania, możesz użyć punktów przerwania, aby wstrzymać program do sprawdzenia stanu zmiennych i obiektów.

W tym instruktażu Oglądasz wartość zmiennej w trakcie działania programu i ustalamy, dlaczego wartość nie jest oczekiwana.

## <a name="prerequisites"></a>Wymagania wstępne

- W tym instruktażu założono, że rozumiesz podstawy języka C++.

- Przyjęto również założenie, że zostały wykonane wcześniejsze powiązane instruktaże, które są wymienione na liście [przy użyciu środowiska IDE programu Visual Studio na potrzeby programowania aplikacji klasycznych](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)w języku C++.

### <a name="to-run-a-program-in-debug-mode"></a>Aby uruchomić program w trybie debugowania

1. Otwórz grę Games. cpp do edycji.

1. Zaznacz ten wiersz kodu:

   `Cardgame solitaire(1);`

1. Aby ustawić punkt przerwania w tym wierszu, na pasku menu wybierz **Debuguj**  >  **Przełącz punkt przerwania** lub wybierz klawisz **F9** . Czerwony okrąg pojawia się na lewo od wiersza; wskazuje, że punkt przerwania jest ustawiony. Aby usunąć punkt przerwania, możesz ponownie wybrać polecenie menu lub klawisz **F9** .

   Jeśli używasz myszy, możesz również ustawić lub usunąć punkt przerwania, klikając na lewym marginesie.

1. Na pasku menu wybierz **Debuguj**  >  **Rozpocznij debugowanie** lub wybierz klawisz **F5** .

   Gdy program osiągnie wiersz z punktem przerwania, wykonywanie jest tymczasowo zatrzymane, ponieważ program jest w trybie przerwania. Żółta strzałka z lewej strony wiersza kodu wskazuje, że jest to kolejny wiersz, który ma zostać wykonany.

1. Aby przeanalizować wartość `Cardgame::totalParticipants` zmiennej, przesuń wskaźnik myszy nad `Cardgame` kontrolkę ekspansja po lewej stronie okna etykietki narzędzi. `totalParticipants`Wyświetlana jest nazwa zmiennej i jej wartość **12** .

   Otwórz menu skrótów dla `Cardgame::totalParticipants` zmiennej, a następnie wybierz polecenie **Dodaj czujkę** , aby wyświetlić tę zmienną w oknie **czujka 1** . Możesz również zaznaczyć zmienną i przeciągnąć ją do okna **czujka 1** .

1. Aby przejść do następnego wiersza kodu, na pasku menu wybierz polecenie **Debuguj**  >  **krok przekroczenia** lub wybierz klawisz **F10** .

   Wartość `Cardgame::totalParticipants` w oknie **czujka 1** jest teraz wyświetlana jako **13**.

1. Otwórz menu skrótów dla `return 0;` instrukcji, a następnie wybierz polecenie **Uruchom do kursora**. Żółta strzałka z lewej strony kodu wskazuje następną instrukcję do wykonania.

1. `Cardgame::totalParticipants`Liczba powinna się zmniejszyć po `Cardgame` zakończeniu. W tym momencie `Cardgame::totalParticipants` powinna być równa 0, ponieważ wszystkie `Cardgame` wystąpienia zostały usunięte, ale okno **czujki 1** wskazuje, że `Cardgame::totalparticipants` jest równe **18**. Różnica wskazuje, że wystąpił błąd w kodzie, który można wykryć i naprawić, wykonując kolejne wskazówki, [Przewodnik: debugowanie projektu (C++)](../ide/walkthrough-debugging-a-project-cpp.md).

1. Aby zatrzymać program, na pasku menu wybierz **debugowanie**  >  **Zatrzymaj debugowanie** lub wybierz  + skrót klawiaturowy SHIFT **F5** .

## <a name="next-steps"></a>Następne kroki

**Poprzednie:** [Przewodnik: kompilowanie projektu (C++)](../ide/walkthrough-building-a-project-cpp.md)<br/>
**Dalej:** [Przewodnik: debugowanie projektu (C++)](../ide/walkthrough-debugging-a-project-cpp.md)

## <a name="see-also"></a>Zobacz też

[Dokumentacja języka C++](../cpp/cpp-language-reference.md)<br/>
[Projekty i systemy kompilacji](../build/projects-and-build-systems-cpp.md)<br/>
