---
description: 'Dowiedz się więcej na temat: Tworzenie aplikacji natywnych działań systemu Android'
title: Tworzenie aplikacji systemu Android działania natywnego
ms.date: 10/17/2019
ms.assetid: 884014b1-5208-45ec-b0da-ad0070d2c24d
ms.openlocfilehash: d8ccccde40c89553d12fd98645cda2877e581273
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319329"
---
# <a name="create-an-android-native-activity-app"></a>Tworzenie aplikacji systemu Android działania natywnego

W przypadku instalowania wieloplatformowego **opracowywania aplikacji mobilnych przy użyciu obciążenia języka C++** program Visual Studio może służyć do tworzenia w pełni funkcjonalnego środowiska z natywnymi działaniami systemu Android. Zestaw Android Native Development Kit (NDK) stanowi zestaw narzędzi umożliwiający wdrożenie większości aplikacji systemu Android przy użyciu czystego kodu C/C++. Kod JNI języka Java działa jako Glue, aby umożliwić współdziałanie kodu C/C++ z systemem Android. System Android NDK wprowadził możliwość tworzenia natywnych aplikacji aktywności z użyciem interfejsu API systemu Android Level 9. Natywny kod aktywności jest popularny do tworzenia gier i intensywnie korzystających z grafiki aplikacji wykorzystujących aparat Unreal lub OpenGL. Ten temat przeprowadzi Cię przez proces tworzenia prostej natywnej aplikacji, która korzysta z technologii OpenGL. Dodatkowe tematy przeprowadzą Cię przez cykl życia deweloperów w zakresie edytowania, kompilowania, debugowania i wdrażania natywnego kodu aktywności.

## <a name="requirements"></a>Wymagania

Aby można było utworzyć aplikację dla działania w trybie macierzystym systemu Android, należy upewnić się, że zostały spełnione wszystkie wymagania systemowe oraz że zainstalowano **Programowanie aplikacji mobilnych za pomocą języka C++** w programie Visual Studio. Aby uzyskać więcej informacji, zobacz [Instalowanie międzyplatformowego opracowywania aplikacji mobilnych za pomocą języka C++](../cross-platform/install-visual-cpp-for-cross-platform-mobile-development.md). Upewnij się, że wymagane narzędzia i zestawy SDK innych firm są zawarte w instalacji oraz że zainstalowano emulator systemu Android.

## <a name="create-a-new-native-activity-project"></a>Tworzenie nowego projektu działania natywnego

W tym samouczku utworzysz nowy projekt aktywności systemu Android Native, a następnie kompilujesz i uruchomisz aplikację domyślną w emulatorze systemu Android.

::: moniker range="msvc-150"

1. W programie Visual Studio wybierz pozycję **plik** > **Nowy** > **projekt**.

1. W oknie dialogowym **Nowy projekt** w obszarze **Szablony** wybierz pozycję **Visual C++** > **wiele platform**, a następnie wybierz szablon **aplikacja native-activity (Android)** .

1. Nadaj aplikacji nazwę, na przykład *MyAndroidApp*, a następnie wybierz przycisk **OK**.

   ![Tworzenie projektu działania natywnego](../cross-platform/media/cppmdd-newproject.png "Tworzenie projektu działania natywnego")

   Program Visual Studio tworzy nowe rozwiązanie i otwiera Eksplorator rozwiązań.

   ![Natywny projekt aktywności w Eksplorator rozwiązań](../cross-platform/media/cppmdd-rc-na-solutionexp.png "Natywny projekt aktywności w Eksplorator rozwiązań")

::: moniker-end

::: moniker range=">=msvc-160"

1. W programie Visual Studio wybierz pozycję **plik** > **Nowy** > **projekt**.

1. W oknie dialogowym **Utwórz nowy projekt** wybierz szablon **aplikacja natywna działania (Android)** , a następnie wybierz przycisk **dalej**.

1. W oknie dialogowym **Konfigurowanie nowego projektu** wprowadź nazwę, taką jak *MyAndroidApp* w polu **Nazwa projektu**, a następnie wybierz pozycję **Utwórz**.

   Program Visual Studio tworzy nowe rozwiązanie i otwiera Eksplorator rozwiązań.

::: moniker-end

Nowe rozwiązanie aplikacji Android Native Activity obejmuje dwa projekty:

- `MyAndroidApp.NativeActivity` zawiera kod odwołań i przyklejania dla aplikacji do uruchamiania jako działanie natywne w systemie Android. Implementacja punktów wejścia z kodu Glue znajduje się w *Main. cpp*. Wstępnie skompilowane nagłówki znajdują się w pliku *PCH. h*. Ten projekt aplikacji natywnej aktywności jest kompilowany do biblioteki udostępnionej *. plik,* który jest wybierany przez projekt pakietu.

- `MyAndroidApp.Packaging` tworzy plik *. apk* do wdrożenia na urządzeniu z systemem Android lub w emulatorze. Zawiera ona zasoby i *AndroidManifest.xml* plik, w którym są ustawiane właściwości manifestu. Zawiera również plik *build.xml* , który kontroluje proces kompilacji ANT. Domyślnie jest ustawiony jako projekt startowy, aby można go było wdrożyć i uruchomić bezpośrednio z programu Visual Studio.

## <a name="build-and-run-the-default-android-native-activity-app"></a>Kompilowanie i uruchamianie domyślnej aplikacji dla systemu Android Native Activity

Skompiluj i uruchom aplikację wygenerowaną przez szablon w celu zweryfikowania instalacji i konfiguracji. Na potrzeby tego testu wstępnego Uruchom aplikację na jednym z profili urządzeń zainstalowanych przez emulator systemu Android. Jeśli wolisz przetestować aplikację w innym miejscu docelowym, możesz załadować emulator docelowy lub podłączyć urządzenie do komputera.

## <a name="to-build-and-run-the-default-native-activity-app"></a>Aby skompilować i uruchomić domyślną aplikację natywnego działania

1. Jeśli nie została jeszcze wybrana, wybierz pozycję **x86** z listy rozwijanej **platformy rozwiązań** .

     ![Lista rozwijana platformy rozwiązań x86 — wybór](../cross-platform/media/cppmdd-rc-na-solution-x86.png "Lista rozwijana platformy rozwiązań x86 — wybór")

     Jeśli lista **platform rozwiązań** nie jest wyświetlana, wybierz pozycję **platformy rozwiązań** z listy **Dodaj/Usuń przyciski** , a następnie wybierz swoją platformę.

1. Na pasku menu wybierz polecenie **Kompiluj**  >  **kompilację rozwiązania**.

     W oknie danych wyjściowych zostaną wyświetlone dane wyjściowe procesu kompilacji dla dwóch projektów w rozwiązaniu.

1. Wybierz jeden z profilów emulatora systemu Android jako cel wdrożenia.

     Jeśli zainstalowano Inne emulatory lub podłączone urządzenie z systemem Android, można je wybrać z listy rozwijanej cel wdrożenia.

1. Naciśnij klawisz **F5** , aby rozpocząć debugowanie, lub **przesuń** + **F5** , aby rozpocząć bez debugowania.

   Oto jak wygląda aplikacja domyślna w emulatorze systemu Android.

   ![Emulator z uruchomioną aplikacją](../cross-platform/media/cppmdd-emulator-running-app.png "Emulator z uruchomioną aplikacją")

   Program Visual Studio uruchamia emulator, który zajmuje kilka sekund, aby załadować i wdrożyć kod. Po rozpoczęciu pracy aplikacji można ustawić punkty przerwania i użyć debugera do przechodzenia przez kod, badania wartości lokalnych i obserwacji.

1. Naciśnij klawisz **SHIFT** + **F5** , aby zatrzymać debugowanie.

   Emulator to oddzielny proces, który jest nadal uruchamiany. Można edytować, kompilować i wdrażać kod wielokrotnie w tym samym emulatorze.
