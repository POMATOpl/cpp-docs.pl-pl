---
description: 'Dowiedz się więcej na temat: Przewodnik: wdrażanie aplikacji Visual C++ przy użyciu projektu Instalatora'
title: Wdrażanie aplikacji Visual C++ przy użyciu projektu Instalatora
ms.date: 04/25/2019
helpviewer_keywords:
- deployment for Visual C++
ms.assetid: 66735cda-8fe3-4211-a19a-2cf717a12a3f
ms.openlocfilehash: 3815ce7a489440d6ae7db6bc73a1c17d02d46ae3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97135996"
---
# <a name="walkthrough-deploying-a-visual-c-application-by-using-a-setup-project"></a>Wskazówki: wdrażanie aplikacji Visual C++ przy użyciu instalacji projektu

Opisuje sposób użycia projektu konfiguracji do wdrożenia aplikacji Visual C++.

## <a name="prerequisites"></a>Wymagania wstępne

Następujące składniki są wymagane do przeprowadzenia tego instruktażu:

- Komputer z zainstalowanym programem Visual Studio.

- Dodatkowy komputer, który nie ma bibliotek Visual C++.

## <a name="create-the-setup-project"></a>Tworzenie projektu Instalatora

Instrukcje dotyczące tworzenia projektu konfiguracji różnią się w zależności od zainstalowanej wersji programu Visual Studio. Aby wyświetlić dokumentację preferowanej wersji programu Visual Studio, użyj kontrolki selektora **wersji** . Znajduje się w górnej części spisu treści na tej stronie.

::: moniker range="=msvc-160"

### <a name="to-create-the-project-in-visual-studio-2019"></a>Aby utworzyć projekt w programie Visual Studio 2019

1. Na pasku menu wybierz pozycję **plik** > **Nowy** > **projekt** , aby otworzyć okno dialogowe **Tworzenie nowego projektu** .

   ![Projekt aplikacji MFC](media/vs2019-mfc-app-new-project.png "Nowa aplikacja MFC")

1. W górnej części okna dialogowego wpisz `MFC` w polu wyszukiwania, a następnie wybierz pozycję **aplikacja MFC** z listy wyników. Jeśli nie widzisz go, musisz uruchomić program Instalator programu Visual Studio z menu Start systemu Windows, a następnie kliknąć kafelek **obciążenie Programowanie aplikacji klasycznych w języku C++** . W obszarze **poszczególne składniki** upewnij się, że składnik MFC jest zaznaczone.

1. Na następnej stronie Wprowadź nazwę projektu i określ lokalizację projektu w razie potrzeby.

1. Wybierz przycisk **Utwórz** , aby utworzyć projekt klienta. Gdy zostanie wyświetlony **Kreator aplikacji MFC** , Zaakceptuj wszystkie ustawienia domyślne.

1. Zmień konfigurację aktywnego rozwiązania na **Release**. Z menu **kompilacja** wybierz pozycję **Menedżer konfiguracji**. W oknie dialogowym **Configuration Manager** wybierz pozycję **wydawanie** w polu listy rozwijanej **aktywna Konfiguracja rozwiązania** . Kliknij przycisk **Zamknij**.

1. Naciśnij **klawisze CTRL** + **SHIFT** + **B** , aby skompilować aplikację. Lub w menu **kompilacja** kliknij pozycję **Kompiluj rozwiązanie**. Kompilowanie aplikacji umożliwia projektowi Instalatora używanie danych wyjściowych tego projektu aplikacji MFC.

1. Jeśli jeszcze tego nie zrobiono, Pobierz rozszerzenie projekty Instalatora Microsoft Visual Studio. Rozszerzenie jest bezpłatne dla deweloperów programu Visual Studio i dodaje funkcjonalność szablonów projektu instalacji i wdrażania do programu Visual Studio. Gdy masz połączenie z Internetem, w programie Visual Studio wybierz pozycję **rozszerzenia**  >  **Zarządzanie rozszerzeniami**. W oknie dialogowym **rozszerzenia i aktualizacje** wybierz kartę **Online** i wpisz *Microsoft Visual Studio projekty Instalatora* w polu wyszukiwania. Naciśnij klawisz **Enter**, wybierz pozycję **\<version> projekty Instalatora Microsoft Visual Studio**, a następnie kliknij pozycję **Pobierz**. Wybierz, aby uruchomić i zainstalować rozszerzenie, a następnie ponownie uruchom program Visual Studio.

   ![Projekt Instalatora programu Visual Studio](media/vs2019-extension-dialog-installer-project.png "Nadaj nazwę projektowi klienta")

1. Na pasku menu programu Visual Studio wybierz kolejno pozycje **plik** > **ostatnie projekty i rozwiązania**, a następnie wybierz polecenie ponownie otwórz projekt.

1. Na pasku menu wybierz pozycję **plik**  >  **Nowy**  >  **projekt** , aby otworzyć okno dialogowe **Tworzenie nowego projektu** . W polu wyszukiwania wpisz ciąg "Setup", a następnie na liście wyników wybierz pozycję **Setup Project**.

1. Wprowadź nazwę projektu konfiguracji w polu **Nazwa** . Z listy rozwijanej **rozwiązanie** wybierz pozycję **Dodaj do rozwiązania**. Wybierz przycisk **OK** , aby utworzyć projekt Instalatora. Zostanie otwarta karta **Asystent plików (ProjectName)** w oknie edytora.

::: moniker-end

::: moniker range="=msvc-150"

### <a name="to-create-the-project-in-visual-studio-2017"></a>Aby utworzyć projekt w programie Visual Studio 2017

1. Tworzenie nowego projektu. W menu **plik** wskaż polecenie **Nowy**, a następnie kliknij pozycję **projekt**.

1. Użyj **Kreatora aplikacji MFC** , aby utworzyć nowe rozwiązanie programu Visual Studio. Aby znaleźć kreatora, w oknie dialogowym **Nowy projekt** rozwiń węzeł **Visual C++** , wybierz pozycję **MFC**, wybierz pozycję **aplikacja MFC**, wprowadź nazwę projektu, a następnie kliknij przycisk **OK**. Kliknij przycisk **Finish** (Zakończ).

   > [!NOTE]
   > Jeśli brakuje typu **aplikacji MFC** , wybierz pozycję **Otwórz Instalator programu Visual Studio** w lewym okienku okna dialogowego **Nowy projekt** . Zainstaluj opcję znajdującą się w obszarze **Programowanie aplikacji klasycznych w języku C++** w sekcji **opcjonalne** składniki o nazwie **Visual C++ MFC dla architektury x86 i x64**.

1. Zmień konfigurację aktywnego rozwiązania na **Release**. Z menu **kompilacja** wybierz pozycję **Menedżer konfiguracji**. W oknie dialogowym **Configuration Manager** wybierz pozycję **wydawanie** w polu listy rozwijanej **aktywna Konfiguracja rozwiązania** . Kliknij przycisk **Zamknij**.

1. Naciśnij **klawisze CTRL** + **SHIFT** + **B** , aby skompilować aplikację. Lub w menu **kompilacja** kliknij pozycję **Kompiluj rozwiązanie**. Kompilowanie aplikacji umożliwia projektowi Instalatora używanie danych wyjściowych tego projektu aplikacji MFC.

1. Jeśli jeszcze tego nie zrobiono, Pobierz rozszerzenie projekty Instalatora Microsoft Visual Studio. Rozszerzenie jest bezpłatne dla deweloperów programu Visual Studio i dodaje funkcjonalność szablonów projektu instalacji i wdrażania do programu Visual Studio. Gdy masz połączenie z Internetem, w programie Visual Studio wybierz pozycję **Narzędzia**  >  **rozszerzenia i aktualizacje**. W oknie dialogowym **rozszerzenia i aktualizacje** wybierz kartę **Online** i wpisz *Microsoft Visual Studio projekty Instalatora* w polu wyszukiwania. Naciśnij klawisz **Enter**, wybierz pozycję **\<version> projekty Instalatora Microsoft Visual Studio**, a następnie kliknij pozycję **Pobierz**. Wybierz, aby uruchomić i zainstalować rozszerzenie, a następnie ponownie uruchom program Visual Studio.

1. Na pasku menu wybierz kolejno pozycje **plik** > **ostatnie projekty i rozwiązania**, a następnie wybierz polecenie ponownie otwórz projekt.

1. Na pasku menu wybierz pozycję **plik**  >  **Nowy**  >  **projekt** , aby otworzyć okno dialogowe **Nowy projekt** . Następnie w lewym okienku okna dialogowego rozwiń węzeł **zainstalowane**  >  **Inne typy projektów** , a następnie wybierz pozycję **Instalator programu Visual Studio**. W środkowym okienku wybierz kolejno pozycje **Konfiguracja projekt**.

1. Wprowadź nazwę projektu konfiguracji w polu **Nazwa** . Z listy rozwijanej **rozwiązanie** wybierz pozycję **Dodaj do rozwiązania**. Wybierz przycisk **OK** , aby utworzyć projekt Instalatora. Zostanie otwarta karta **Asystent plików (ProjectName)** w oknie edytora.

::: moniker-end

::: moniker range="=msvc-140"

### <a name="to-create-the-project-in-visual-studio-2015"></a>Aby utworzyć projekt w programie Visual Studio 2015

1. Tworzenie nowego projektu. W menu **plik** wskaż polecenie **Nowy**, a następnie kliknij pozycję **projekt**.

1. Użyj **Kreatora aplikacji MFC** , aby utworzyć nowe rozwiązanie programu Visual Studio. Aby znaleźć kreatora, w oknie dialogowym **Nowy projekt** rozwiń węzeł **Visual C++** , wybierz pozycję **MFC**, wybierz pozycję **aplikacja MFC**, wprowadź nazwę projektu, a następnie kliknij przycisk **OK**. Kliknij przycisk **Finish** (Zakończ).

   > [!NOTE]
   > Jeśli brakuje typu **aplikacji MFC** , kliknij przycisk Start systemu Windows i wpisz polecenie **Dodaj Usuń programy**. Otwórz program z listy wyników, a następnie Znajdź instalację Microsoft Visual Studio 2015 na liście zainstalowanych programów. Kliknij go dwukrotnie, a następnie wybierz **Modyfikuj** i wybierz składnik **Microsoft Foundation Classes** w obszarze **Visual C++**.

1. Zmień konfigurację aktywnego rozwiązania na **Release**. Z menu **kompilacja** wybierz **Configuration Manager**. W oknie dialogowym **Configuration Manager** wybierz pozycję **wydawanie** w polu listy rozwijanej **aktywna Konfiguracja rozwiązania** . Kliknij przycisk **Zamknij**.

1. Naciśnij **klawisze CTRL** + **SHIFT** + **B** , aby skompilować aplikację. Lub w menu **kompilacja** kliknij pozycję **Kompiluj rozwiązanie**. Kompilowanie aplikacji umożliwia projektowi Instalatora używanie danych wyjściowych tego projektu aplikacji MFC.

1. Jeśli jeszcze tego nie zrobiono, Pobierz rozszerzenie projekty Instalatora Microsoft Visual Studio. Rozszerzenie jest bezpłatne dla deweloperów programu Visual Studio i dodaje funkcjonalność szablonów projektu instalacji i wdrażania do programu Visual Studio. Gdy masz połączenie z Internetem, w programie Visual Studio wybierz pozycję **Narzędzia**  >  **rozszerzenia i aktualizacje**. W oknie dialogowym **rozszerzenia i aktualizacje** wybierz kartę **Online** i wpisz *Microsoft Visual Studio projekty Instalatora* w polu wyszukiwania. Naciśnij klawisz **Enter**, wybierz pozycję **\<version> projekty Instalatora Microsoft Visual Studio**, a następnie kliknij pozycję **Pobierz**. Wybierz, aby uruchomić i zainstalować rozszerzenie, a następnie ponownie uruchom program Visual Studio.

1. Na pasku menu wybierz kolejno pozycje **plik** > **ostatnie projekty i rozwiązania**, a następnie wybierz polecenie ponownie otwórz projekt.

1. Na pasku menu wybierz pozycję **plik**  >  **Nowy**  >  **projekt** , aby otworzyć okno dialogowe **Nowy projekt** . Następnie w lewym okienku okna dialogowego rozwiń węzeł **zainstalowane**  >  **Inne typy projektów** , a następnie wybierz pozycję **Instalator programu Visual Studio**. W środkowym okienku wybierz kolejno pozycje **Konfiguracja projekt**.

1. Wprowadź nazwę projektu konfiguracji w polu **Nazwa** . Z listy rozwijanej **rozwiązanie** wybierz pozycję **Dodaj do rozwiązania**. Wybierz przycisk **OK** , aby utworzyć projekt Instalatora. Zostanie otwarta karta **Asystent plików (ProjectName)** w oknie edytora.

::: moniker-end

## <a name="add-items-to-the-project"></a>Dodaj elementy do projektu

1. Kliknij prawym przyciskiem myszy węzeł **folder aplikacji** i wybierz polecenie **Dodaj**  >  **dane wyjściowe projektu** , aby otworzyć okno dialogowe **Dodawanie grupy wyjściowej projektu** . W oknie dialogowym wybierz pozycję **podstawowe dane wyjściowe** , a następnie kliknij przycisk **OK**. Zostanie wyświetlony nowy element o nazwie **podstawowe wyjście z ProjectName (aktywny)** .

1. Kliknij prawym przyciskiem myszy węzeł **folder aplikacji** , a następnie wybierz polecenie **Dodaj**  >  **zestaw** , aby otworzyć okno dialogowe **Wybieranie składnika** . Wybierz i Dodaj wszystkie wymagane biblioteki DLL wymagane przez program, zgodnie z opisem w artykule [Określanie bibliotek DLL do redystrybucji](determining-which-dlls-to-redistribute.md).

1. Wybierz **podstawowe dane wyjściowe elementu z ProjectName (aktywne)**, kliknij prawym przyciskiem myszy i wybierz polecenie **Utwórz skrót do podstawowego wyjścia z ProjectName (aktywny)**. Zostanie wyświetlony nowy element o nazwie **skrót do podstawowego wyjścia z ProjectName (aktywny)** . Można zmienić nazwę elementu skrótu, a następnie przeciągnąć i upuścić element w węźle **menu programy użytkownika** po lewej stronie okna.

1. Na pasku menu wybierz kolejno opcje **Kompiluj**  >  **Configuration Manager**. W tabeli **projektu** w kolumnie **kompilacja** zaznacz pole wyboru dla projektu wdrożenia. Kliknij przycisk **Zamknij**.

1. Na pasku menu wybierz kompilacja Kompiluj   >  **rozwiązanie** , aby skompilować projekt MFC i projekt wdrożenia.

1. W folderze rozwiązanie Znajdź program setup.exe, który został skompilowany na podstawie projektu wdrożenia. Możesz skopiować ten plik (i plik msi), aby zainstalować aplikację i wymagane pliki biblioteki na innym komputerze. Uruchom program instalacyjny na drugim komputerze, który nie ma bibliotek Visual C++.

## <a name="see-also"></a>Zobacz też

[Przykłady wdrożeń](deployment-examples.md)<br/>
