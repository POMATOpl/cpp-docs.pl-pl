---
title: 'Wskazówki: wdrażanie Twojego programu (C++)'
ms.date: 05/14/2019
helpviewer_keywords:
- deploying applications [C++], walkthroughs
- setup projects [C++]
- program deployments [C++]
- projects [C++], setup
- projects [C++], deploying programs
- application deployment [C++], walkthroughs
ms.assetid: 79e6cc4e-dced-419d-aaf7-d62d1367603f
ms.openlocfilehash: 6c5d98687d6b5a49fb7b4b90aecf345a739c34a3
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92924676"
---
# <a name="walkthrough-deploying-your-program-c"></a>Wskazówki: wdrażanie Twojego programu (C++)

Teraz, gdy aplikacja została utworzona przez wykonanie wcześniejszych powiązanych instruktaży, ostatnim krokiem jest utworzenie Instalatora, aby inni użytkownicy mogli zainstalować program na swoich komputerach. W przypadku Instalatora zostanie dodany nowy projekt do istniejącego rozwiązania. Dane wyjściowe tego nowego projektu to plik setup.exe, który zainstaluje aplikację na innym komputerze.

W tym przewodniku pokazano, jak za pomocą Instalator Windows wdrożyć aplikację. Do wdrożenia aplikacji można także użyć technologii ClickOnce. Aby uzyskać więcej informacji, zobacz [wdrażanie ClickOnce dla aplikacji Visual C++](../windows/clickonce-deployment-for-visual-cpp-applications.md). Aby uzyskać więcej informacji na temat ogólnego wdrażania, zobacz [wdrażanie aplikacji, usług i składników](/visualstudio/deployment/deploying-applications-services-and-components).

## <a name="prerequisites"></a>Wymagania wstępne

- W tym przewodniku założono, że rozumiesz podstawy języka C++.

- Przyjęto również założenie, że zostały wykonane wcześniejsze powiązane instruktaże, które są wymienione na liście [przy użyciu środowiska IDE programu Visual Studio na potrzeby programowania aplikacji klasycznych](using-the-visual-studio-ide-for-cpp-desktop-development.md)w języku C++.

- Nie można ukończyć przewodnika w wersjach Express programu Visual Studio.

## <a name="install-the-visual-studio-setup-and-deployment-project-template"></a>Zainstaluj szablon projektu instalacji i wdrażania programu Visual Studio

Kroki opisane w tej sekcji różnią się w zależności od zainstalowanej wersji programu Visual Studio. Aby wyświetlić dokumentację preferowanej wersji programu Visual Studio, użyj kontrolki selektora **wersji** . Znajduje się w górnej części spisu treści na tej stronie.

<!-- markdownlint-disable MD034 -->

::: moniker range="msvc-160"

### <a name="to-install-the-setup-and-deployment-project-template-for-visual-studio-2019"></a>Aby zainstalować szablon projektu instalacji i wdrażania dla programu Visual Studio 2019

1. Jeśli jeszcze tego nie zrobiono, Pobierz rozszerzenie projekty Instalatora Microsoft Visual Studio. Rozszerzenie jest bezpłatne dla deweloperów programu Visual Studio i dodaje funkcjonalność szablonów projektu instalacji i wdrażania do programu Visual Studio. Gdy masz połączenie z Internetem, w programie Visual Studio wybierz pozycję **rozszerzenia**  >  **Zarządzanie rozszerzeniami** . W oknie dialogowym **rozszerzenia i aktualizacje** wybierz kartę **Online** i wpisz *Microsoft Visual Studio projekty Instalatora* w polu wyszukiwania. Naciśnij klawisz **Enter** , wybierz pozycję **\<version> projekty Instalatora Microsoft Visual Studio** , a następnie kliknij pozycję **Pobierz** . Wybierz, aby uruchomić i zainstalować rozszerzenie, a następnie ponownie uruchom program Visual Studio.

1. Na pasku menu programu Visual Studio wybierz kolejno pozycje **plik** > **ostatnie projekty i rozwiązania** , a następnie wybierz polecenie ponownie otwórz projekt.

1. Na pasku menu wybierz pozycję **plik**  >  **Nowy**  >  **projekt** , aby otworzyć okno dialogowe **Tworzenie nowego projektu** . W polu wyszukiwania wpisz ciąg "Setup", a następnie na liście wyników wybierz pozycję **Setup Project** .

1. Wprowadź nazwę projektu konfiguracji w polu **Nazwa** . Z listy rozwijanej **rozwiązanie** wybierz pozycję **Dodaj do rozwiązania** . Wybierz przycisk **OK** , aby utworzyć projekt Instalatora. Zostanie otwarta karta **Asystent plików (ProjectName)** w oknie edytora.

1. Kliknij prawym przyciskiem myszy węzeł **folder aplikacji** i wybierz polecenie **Dodaj** > **dane wyjściowe projektu** , aby otworzyć okno dialogowe **Dodawanie grupy wyjściowej projektu** .

1. W oknie dialogowym wybierz pozycję **podstawowe dane wyjściowe** , a następnie kliknij przycisk **OK** . Zostanie wyświetlony nowy element o nazwie **podstawowe wyjście z gry (aktywne)** .

1. Wybierz element **podstawowy elementu z gry (aktywne)** , kliknij prawym przyciskiem myszy i wybierz polecenie **Utwórz skrót do podstawowych danych wyjściowych z gry (aktywne)** . Zostanie wyświetlony nowy element o nazwie **skrót do podstawowych danych wyjściowych z gry (aktywne)** .

1. Zmień nazwę elementu skrótu na *Game* , a następnie przeciągnij i upuść element w węźle **menu programy użytkownika** po lewej stronie okna.

1. W **Eksplorator rozwiązań** wybierz projekt **Instalatora gry** i wybierz polecenie **Wyświetl** > **okno właściwości** lub naciśnij klawisz **F4** , aby otworzyć okno **Właściwości** .

1. Określ dodatkowe szczegóły, które mają być wyświetlane w instalatorze.  Na przykład użyj firmy *contoso* dla **producenta** , *Instalatora gry* dla **nazwy produktu** i *https \: //www.contoso.com* dla **SupportUrl** .

1. Na pasku menu wybierz kolejno opcje **Kompiluj**  >  **Configuration Manager** . W tabeli **projektu** w kolumnie **kompilacja** zaznacz pole wyboru **Instalator gry** . Kliknij przycisk **Zamknij** .

1. Na pasku menu wybierz **kompilację** Kompiluj > **rozwiązanie** , aby skompilować projekt gry i projekt Instalatora gry.

1. W folderze rozwiązanie Znajdź program setup.exe, który został skompilowany przy użyciu projektu Instalatora gry, a następnie uruchom go, aby zainstalować aplikację Game na komputerze. Można skopiować ten plik (i GameInstaller.msi), aby zainstalować aplikację i wymagane pliki biblioteki na innym komputerze.

::: moniker-end

::: moniker range="<=msvc-150"

### <a name="to-install-the-setup-and-deployment-project-template-for-visual-studio-2017-and-earlier"></a>Aby zainstalować szablon projektu instalacji i wdrażania dla programu Visual Studio 2017 i jego wcześniejszych wersji

1. Gdy masz połączenie z Internetem, w programie Visual Studio wybierz pozycję **Narzędzia** > **rozszerzenia i aktualizacje** .

1. W obszarze **rozszerzenia i aktualizacje** wybierz kartę **online** , a następnie w polu wyszukiwania wpisz *Microsoft Visual Studio Projects (projekty Instalatora* ). Naciśnij klawisz **Enter** , wybierz pozycję **\<version> projekty Instalatora Microsoft Visual Studio** , a następnie kliknij pozycję **Pobierz** .

1. Wybierz, aby zainstalować rozszerzenie, a następnie ponownie uruchom program Visual Studio.

1. Na pasku menu wybierz kolejno pozycje **plik** > **ostatnie projekty i rozwiązania** , a następnie wybierz rozwiązanie do **gier** , aby je otworzyć ponownie.

### <a name="to-create-a-setup-project-and-install-your-program"></a>Aby utworzyć projekt konfiguracji i zainstalować program

1. Zmień konfigurację aktywnego rozwiązania na Release. Na pasku menu wybierz kolejno opcje **Kompiluj**  >  **Configuration Manager** . W oknie dialogowym **Configuration Manager** na liście rozwijanej **aktywna Konfiguracja rozwiązania** wybierz pozycję **wersja** . Wybierz przycisk **Zamknij** , aby zapisać konfigurację.

1. Na pasku menu wybierz pozycję **plik** > **Nowy** > **projekt** , aby otworzyć okno dialogowe **Nowy projekt** .

1. W lewym okienku okna dialogowego rozwiń węzeł **zainstalowane**  >  **Inne typy projektów** , a następnie wybierz pozycję **Instalator programu Visual Studio** . W środkowym okienku wybierz kolejno pozycje **Konfiguracja projekt** .

1. Wprowadź nazwę projektu konfiguracji w polu **Nazwa** . W tym przykładzie należy wprowadzić *Instalatora gry* . Z listy rozwijanej **rozwiązanie** wybierz pozycję **Dodaj do rozwiązania** . Wybierz przycisk **OK** , aby utworzyć projekt Instalatora. Zostanie otwarta karta **Asystent plików (Instalator gry)** w oknie edytora.

1. Kliknij prawym przyciskiem myszy węzeł **folder aplikacji** i wybierz polecenie **Dodaj** > **dane wyjściowe projektu** , aby otworzyć okno dialogowe **Dodawanie grupy wyjściowej projektu** .

1. W oknie dialogowym wybierz pozycję **podstawowe dane wyjściowe** , a następnie kliknij przycisk **OK** . Zostanie wyświetlony nowy element o nazwie **podstawowe wyjście z gry (aktywne)** .

1. Wybierz element **podstawowy elementu z gry (aktywne)** , kliknij prawym przyciskiem myszy i wybierz polecenie **Utwórz skrót do podstawowych danych wyjściowych z gry (aktywne)** . Zostanie wyświetlony nowy element o nazwie **skrót do podstawowych danych wyjściowych z gry (aktywne)** .

1. Zmień nazwę elementu skrótu na *Game* , a następnie przeciągnij i upuść element w węźle **menu programy użytkownika** po lewej stronie okna.

1. W **Eksplorator rozwiązań** wybierz projekt **Instalatora gry** i wybierz polecenie **Wyświetl** > **okno właściwości** lub naciśnij klawisz **F4** , aby otworzyć okno **Właściwości** .

1. Określ dodatkowe szczegóły, które mają być wyświetlane w instalatorze.  Na przykład użyj firmy *contoso* dla **producenta** , *Instalatora gry* dla **nazwy produktu** i *https \: //www.contoso.com* dla **SupportUrl** .

1. Na pasku menu wybierz kolejno opcje **Kompiluj**  >  **Configuration Manager** . W tabeli **projektu** w kolumnie **kompilacja** zaznacz pole wyboru **Instalator gry** . Kliknij przycisk **Zamknij** .

1. Na pasku menu wybierz **kompilację** Kompiluj > **rozwiązanie** , aby skompilować projekt gry i projekt Instalatora gry.

1. W folderze rozwiązanie Znajdź program setup.exe, który został skompilowany przy użyciu projektu Instalatora gry, a następnie uruchom go, aby zainstalować aplikację Game na komputerze. Można skopiować ten plik (i GameInstaller.msi), aby zainstalować aplikację i wymagane pliki biblioteki na innym komputerze.

::: moniker-end

## <a name="next-steps"></a>Następne kroki

**Poprzednie:** [Przewodnik: debugowanie projektu (C++)](walkthrough-debugging-a-project-cpp.md)

## <a name="see-also"></a>Zobacz także

[Dokumentacja języka C++](../cpp/cpp-language-reference.md)<br/>
[Projekty i systemy kompilacji](../build/projects-and-build-systems-cpp.md)<br/>
[Wdrażanie aplikacji klasycznych](../windows/deploying-native-desktop-applications-visual-cpp.md)<br/>
