---
title: Przykładowy projekt w języku C++ na potrzeby analizy kodu
description: Jak utworzyć przykładowe rozwiązanie do użycia w instruktażu analizy kodu dla programu Microsoft C++ w programie Visual Studio.
ms.date: 04/14/2020
ms.topic: sample
helpviewer_keywords:
- demo sample [Visual Studio ALM]
- code analysis, samples
ms.assetid: 09e1b9f7-5916-4ed6-a001-5c2d7e710682
ms.openlocfilehash: dd4fe67c05200ccc2865bc7c48b1f5047d77565e
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92924622"
---
# <a name="sample-c-project-for-code-analysis"></a>Przykładowy projekt w języku C++ na potrzeby analizy kodu

Poniższe procedury pokazują, jak utworzyć przykład dla [przewodnika: Analizowanie kodu C/C++ pod kątem wad](../code-quality/walkthrough-analyzing-c-cpp-code-for-defects.md). Procedury tworzą:

- Rozwiązanie programu Visual Studio o nazwie *CppDemo* .

- Projekt biblioteki statycznej o nazwie *CodeDefects* .

- Projekt biblioteki statycznej o nazwie *Adnotacje* .

Procedury te zawierają również kod dla plików nagłówkowych i *. cpp* dla bibliotek statycznych.

## <a name="create-the-cppdemo-solution-and-the-codedefects-project"></a>Tworzenie rozwiązania CppDemo i projektu CodeDefects

::: moniker range=">=msvc-160"

1. Otwórz program Visual Studio i wybierz pozycję **Utwórz nowy projekt**

1. W oknie dialogowym **Tworzenie nowego projektu** Zmień filtr języka na **C++** .

1. Wybierz pozycję **Kreator pulpitu systemu Windows** , a następnie kliknij przycisk **dalej** .

1. Na stronie **Konfiguruj nowy projekt** w polu tekstowym **Nazwa projektu** wprowadź *CodeDefects* .

1. W polu tekstowym **Nazwa rozwiązania** wprowadź *CppDemo* .

1. Wybierz pozycję **Utwórz** .

1. W oknie dialogowym **projekt pulpitu systemu Windows** Zmień **Typ aplikacji** na **Biblioteka statyczna (. lib)** .

1. W obszarze **Opcje dodatkowe** wybierz pozycję **pusty projekt** .

1. Wybierz **przycisk OK** , aby utworzyć rozwiązanie i projekt.

::: moniker-end

::: moniker range="msvc-150"

1. Otwórz program Visual Studio. Na pasku menu wybierz pozycję **plik**  >  **Nowy**  >  **projekt** .

1. W oknie dialogowym **Nowy projekt** wybierz pozycję **Visual C++** > **Windows Desktop** .

1. Wybierz pozycję **Kreator pulpitu systemu Windows** .

1. W polu tekstowym **Nazwa** wprowadź *CodeDefects* .

1. W polu tekstowym **Nazwa rozwiązania** wprowadź *CppDemo* .

1. Wybierz przycisk **OK** .

1. W oknie dialogowym **projekt pulpitu systemu Windows** Zmień **Typ aplikacji** na **Biblioteka statyczna (. lib)** .

1. W obszarze **Opcje dodatkowe** wybierz pozycję **pusty projekt** .

1. Wybierz **przycisk OK** , aby utworzyć rozwiązanie i projekt.

::: moniker-end

::: moniker range="msvc-140"

1. Otwórz program Visual Studio. Na pasku menu wybierz pozycję **plik**  >  **Nowy**  >  **projekt** .

1. W oknie dialogowym **Nowy projekt** wybierz pozycję **Szablony** > **Visual C++** > **Win32** .

1. Wybierz pozycję **aplikacja konsoli Win32** .

1. W polu tekstowym **Nazwa** wprowadź *CodeDefects* .

1. W polu tekstowym **Nazwa rozwiązania** wprowadź *CppDemo* .

1. Wybierz przycisk **OK** .

1. W oknie dialogowym **Kreator aplikacji Win32** wybierz przycisk **dalej** .

1. Zmień **Typ aplikacji** na **bibliotekę statyczną** .

1. W obszarze **Opcje dodatkowe** Usuń zaznaczenie **prekompilowanego nagłówka** .

1. Wybierz przycisk **Zakończ** , aby utworzyć rozwiązanie i projekt.

::: moniker-end

## <a name="add-the-header-and-source-file-to-the-codedefects-project"></a>Dodaj nagłówek i plik źródłowy do projektu CodeDefects

1. W Eksplorator rozwiązań rozwiń węzeł **CodeDefects** .

1. Kliknij prawym przyciskiem myszy, aby otworzyć menu kontekstowe dla **plików nagłówkowych** . Wybierz pozycję **Dodaj**  >  **nowy element** .

1. W oknie dialogowym **Dodaj nowy element** wybierz pozycję **Visual C++**  >  **kod** , a następnie wybierz pozycję **plik nagłówka (. h)** .

1. W polu **Nazwa** wprowadź wartość *błąd. h* , a następnie wybierz przycisk **Dodaj** .

1. W oknie Edycja dla *błędu. h* wybierz i Usuń zawartość.

1. Skopiuj poniższy kod i wklej go do pliku *usterek. h* w edytorze.

    ```cpp
    #pragma once

    #include <windows.h>

    // Function prototypes
    bool CheckDomain(wchar_t const *);
    HRESULT ReadUserAccount();

    // These constants define the common sizes of the
    // user account information throughout the program
    const int USER_ACCOUNT_LEN = 256;
    const int ACCOUNT_DOMAIN_LEN = 128;
    ```

1. W Eksplorator rozwiązań kliknij prawym przyciskiem myszy, aby otworzyć menu kontekstowe dla **plików źródłowych** . Wybierz pozycję **Dodaj**  >  **nowy element** .

1. W oknie dialogowym **Dodaj nowy element** wybierz opcję **plik C++ (. cpp)** .

1. W polu **Nazwa wprowadź nazwę** *usterka. cpp* , a następnie wybierz przycisk **Dodaj** .

1. Skopiuj poniższy kod i wklej go do pliku *usterek. cpp* w edytorze.

    ```cpp
    #include "Bug.h"

    // the user account
    wchar_t g_userAccount[USER_ACCOUNT_LEN] = { L"domain\\user" };
    int len = 0;

    bool CheckDomain(wchar_t const* domain)
    {
        return (wcsnlen_s(domain, USER_ACCOUNT_LEN) > 0);
    }

    HRESULT ReadUserAccount()
    {
        return S_OK;
    }

    bool ProcessDomain()
    {
        wchar_t* domain = new wchar_t[ACCOUNT_DOMAIN_LEN];
        // ReadUserAccount gets a 'domain\user' input from
        //the user into the global 'g_userAccount'
        if (ReadUserAccount())
        {
            // Copies part of the string prior to the '\'
            // character onto the 'domain' buffer
            for (len = 0; (len < ACCOUNT_DOMAIN_LEN) && (g_userAccount[len] != L'\0'); len++)
            {
                if (g_userAccount[len] == L'\\')
                {
                    // Stops copying on the domain and user separator ('\')
                    break;
                }
                domain[len] = g_userAccount[len];
            }
            if ((len = ACCOUNT_DOMAIN_LEN) || (g_userAccount[len] != L'\\'))
            {
                // '\' was not found. Invalid domain\user string.
                delete[] domain;
                return false;
            }
            else
            {
                domain[len] = L'\0';
            }
            // Process domain string
            bool result = CheckDomain(domain);

            delete[] domain;
            return result;
        }
        return false;
    }

    int path_dependent(int n)
    {
        int i;
        int j;
        if (n == 0)
            i = 1;
        else
            j = 1;
        return i + j;
    }
    ```

1. Na pasku menu wybierz kolejno opcje **plik**  >  **Zapisz wszystko** .

## <a name="add-the-annotations-project-and-configure-it-as-a-static-library"></a>Dodaj projekt adnotacji i skonfiguruj go jako bibliotekę statyczną

::: moniker range=">=msvc-160"

1. W Eksplorator rozwiązań kliknij prawym przyciskiem myszy pozycję **CppDemo** , aby otworzyć menu kontekstowe. Wybierz pozycję **Dodaj**  >  **Nowy projekt** .

1. W oknie dialogowym **Dodawanie nowego projektu** wybierz pozycję **Kreator pulpitu systemu Windows** , a następnie kliknij przycisk **dalej** .

1. Na stronie **Konfiguruj nowy projekt** w polu tekstowym **Nazwa projektu** wprowadź *Adnotacje* , a następnie wybierz pozycję **Utwórz** .

1. W oknie dialogowym **projekt pulpitu systemu Windows** Zmień **Typ aplikacji** na **Biblioteka statyczna (. lib)** .

1. W obszarze **Opcje dodatkowe** wybierz pozycję **pusty projekt** .

1. Wybierz **przycisk OK** , aby utworzyć projekt.

::: moniker-end

::: moniker range="msvc-150"

1. W Eksplorator rozwiązań kliknij prawym przyciskiem myszy pozycję **CppDemo** , aby otworzyć menu kontekstowe. Wybierz pozycję **Dodaj**  >  **Nowy projekt** .

1. W oknie dialogowym **Dodaj nowy projekt** wybierz pozycję **Visual C++** > **Windows Desktop** .

1. Wybierz pozycję **Kreator pulpitu systemu Windows** .

1. W polu tekstowym **Nazwa** wprowadź *Adnotacje* , a następnie wybierz przycisk **OK** .

1. W oknie dialogowym **projekt pulpitu systemu Windows** Zmień **Typ aplikacji** na **Biblioteka statyczna (. lib)** .

1. W obszarze **Opcje dodatkowe** wybierz pozycję **pusty projekt** .

1. Wybierz **przycisk OK** , aby utworzyć projekt.

::: moniker-end

::: moniker range="msvc-140"

1. W Eksplorator rozwiązań kliknij prawym przyciskiem myszy pozycję **CppDemo** , aby otworzyć menu kontekstowe. Wybierz pozycję **Dodaj**  >  **Nowy projekt** .

1. W oknie dialogowym **Dodaj nowy projekt** wybierz pozycję **Visual C++** > **Win32** .

1. Wybierz pozycję **aplikacja konsoli Win32** .

1. W polu tekstowym **Nazwa** wprowadź *Adnotacje* .

1. Wybierz przycisk **OK** .

1. W oknie dialogowym **Kreator aplikacji Win32** wybierz przycisk **dalej** .

1. Zmień **Typ aplikacji** na **bibliotekę statyczną** .

1. W obszarze **Opcje dodatkowe** Usuń zaznaczenie **prekompilowanego nagłówka** .

1. Wybierz pozycję **Zakończ** , aby utworzyć projekt.

::: moniker-end

## <a name="add-the-header-file-and-source-file-to-the-annotations-project"></a>Dodaj plik nagłówka i plik źródłowy do projektu adnotacji

1. W Eksplorator rozwiązań rozwiń pozycję **Adnotacje** .

1. Kliknij prawym przyciskiem myszy, aby otworzyć menu kontekstowe dla **plików nagłówkowych** w obszarze **Adnotacje** . Wybierz pozycję **Dodaj**  >  **nowy element** .

1. W oknie dialogowym **Dodaj nowy element** wybierz pozycję **Visual C++**  >  **kod** , a następnie wybierz pozycję **plik nagłówka (. h)** .

1. W polu tekstowym **Nazwa** wprowadź *Adnotacje. h* , a następnie wybierz przycisk **Dodaj** .

1. W oknie Edycja do *adnotacji. h* wybierz i Usuń zawartość.

1. Skopiuj poniższy kod i wklej go do pliku *Annotations. h* w edytorze.

    ```cpp
    #pragma once
    #include <sal.h>

    struct LinkedList
    {
        struct LinkedList* next;
        int data;
    };

    typedef struct LinkedList LinkedList;

    _Ret_maybenull_ LinkedList* AllocateNode();
    ```

1. W Eksplorator rozwiązań kliknij prawym przyciskiem myszy, aby otworzyć menu kontekstowe dla **plików źródłowych** w obszarze **Adnotacje** . Wybierz pozycję **Dodaj**  >  **nowy element** .

1. W oknie dialogowym **Dodaj nowy element** wybierz opcję **plik C++ (. cpp)** .

1. W polu tekstowym **Nazwa** wprowadź *Adnotacje. cpp* , a następnie wybierz przycisk **Dodaj** .

1. Skopiuj poniższy kod i wklej go do pliku *Annotation. cpp* w edytorze.

    ```cpp
    #include "annotations.h"
    #include <malloc.h>

    _Ret_maybenull_ LinkedList* AllocateNode()
    {
        LinkedList* result = static_cast<LinkedList*>(malloc(sizeof(LinkedList)));
        return result;
    }

    LinkedList* AddTail(LinkedList* node, int value)
    {
        // finds the last node
        while (node->next != nullptr)
        {
            node = node->next;
        }

        // appends the new node
        LinkedList* newNode = AllocateNode();
        newNode->data = value;
        newNode->next = 0;
        node->next = newNode;

        return newNode;
    }
    ```

1. Na pasku menu wybierz kolejno opcje **plik**  >  **Zapisz wszystko** .

Rozwiązanie jest teraz ukończone i powinno zostać skompilowane bez błędów.

::: moniker range="msvc-150"

> [!NOTE]
> W programie Visual Studio 2017 w aparacie IntelliSense może zostać wyświetlone ostrzeżenie fałszywe `E1097 unknown attribute "no_init_all"` . Możesz bezpiecznie zignorować to ostrzeżenie.

::: moniker-end
