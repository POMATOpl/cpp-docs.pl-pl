---
description: 'Dowiedz się więcej na temat: Przewodnik: kompilowanie projektu (C++)'
title: 'Wskazówki: tworzenie projektu (C++)'
ms.date: 04/25/2019
helpviewer_keywords:
- building projects [C++]
- projects [C++], building
- project building [C++]
ms.assetid: d459bc03-88ef-48d0-9f9a-82d17f0b6a4d
ms.openlocfilehash: f606a0ead796916fa41f7669852e67d58ae3b17c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222544"
---
# <a name="walkthrough-building-a-project-c"></a>Wskazówki: tworzenie projektu (C++)

W tym instruktażu zawarto świadomie wprowadzić błąd składniowy języka C++ w kodzie, aby dowiedzieć się, jak wygląda błąd kompilacji i jak rozwiązać ten problem. Podczas kompilowania projektu, komunikat o błędzie wskazuje, jaki problem jest i gdzie wystąpił.

## <a name="prerequisites"></a>Wymagania wstępne

- W tym instruktażu założono, że rozumiesz podstawy języka C++.

- Przyjęto również założenie, że zostały wykonane wcześniejsze powiązane instruktaże, które są wymienione na liście [przy użyciu środowiska IDE programu Visual Studio na potrzeby programowania aplikacji klasycznych](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)w języku C++.

### <a name="to-fix-compilation-errors"></a>Aby naprawić błędy kompilacji

1. W grze. cpp Usuń średnik w ostatnim wierszu, tak aby był on podobny do instrukcji:

   `return 0`

1. Na pasku menu wybierz polecenie **Kompiluj**  >  **kompilację rozwiązania**.

1. Komunikat w oknie **Lista błędów** wskazuje, że wystąpił błąd podczas kompilowania projektu. Opis wygląda następująco:

   `error C2143: syntax error: missing ';' before '}'`

   Aby wyświetlić informacje pomocy dotyczące tego błędu, zaznacz je w oknie **Lista błędów** a następnie wybierz klawisz **F1** .

1. Dodaj średnik z powrotem do końca wiersza, który zawiera błąd składniowy:

   `return 0;`

1. Na pasku menu wybierz polecenie **Kompiluj**  >  **kompilację rozwiązania**.

   Komunikat w oknie **danych wyjściowych** wskazuje, że projekt został skompilowany pomyślnie.

    ```Output
    1>------ Build started: Project: Game, Configuration: Debug Win32 ------
    1>Game.cpp
    1>Game.vcxproj -> C:\Users\<username>\source\repos\Game\Debug\Game.exe
    ========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
    ```

## <a name="next-steps"></a>Następne kroki

**Poprzednie:** [Przewodnik: Praca z projektami i rozwiązaniami (C++)](../ide/walkthrough-working-with-projects-and-solutions-cpp.md)<br/>
**Dalej:** [Przewodnik: Testowanie projektu (C++)](../ide/walkthrough-testing-a-project-cpp.md)

## <a name="see-also"></a>Zobacz też

[Dokumentacja języka C++](../cpp/cpp-language-reference.md)<br/>
[Projekty i systemy kompilacji](../build/projects-and-build-systems-cpp.md)<br/>
