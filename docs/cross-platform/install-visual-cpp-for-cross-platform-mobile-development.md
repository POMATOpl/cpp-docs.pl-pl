---
title: Instalowanie środowiska opracowywania aplikacji mobilnych na wiele platform w języku C++
ms.date: 10/17/2019
ms.assetid: aaea6b8d-55eb-4427-8185-c050f855c257
ms.openlocfilehash: 6a573b0f7ba261b97af9de24e67f733acac0532f
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/12/2020
ms.locfileid: "90041955"
---
# <a name="install-cross-platform-mobile-development-with-c"></a>Instalowanie środowiska opracowywania aplikacji mobilnych na wiele platform w języku C++

Możesz użyć języka C++ w programie Visual Studio do tworzenia aplikacji klasycznych systemu Windows, aplikacji platforma uniwersalna systemu Windows (platformy UWP) i aplikacji Linux. Teraz możesz tworzyć aplikacje w języku C++ dla systemów Android i iOS. **Programowanie aplikacji mobilnych za pomocą języka C++** to instalowalny zestaw składników w programie Visual Studio. Obejmuje to międzyplatformowe szablony systemu iOS, Android i platformy UWP programu Visual Studio. Obciążenie instaluje narzędzia i zestawy SDK dla wielu platform, aby szybko rozpocząć pracę. Nie trzeba będzie lokalizować, pobierać i konfigurować własnych. Za pomocą tych narzędzi w programie Visual Studio można łatwo tworzyć, edytować, debugować i testować projekty Międzyplatformowe.

W tym artykule opisano sposób instalowania narzędzi i oprogramowania innych firm wymagane do tworzenia aplikacji międzyplatformowych w języku C++ przy użyciu programu Visual Studio. Aby zapoznać się z omówieniem, zobacz [Visual C++ międzyplatformowych aplikacji mobilnych](https://visualstudio.microsoft.com/vs/features/cplusplus-mdd/)

## <a name="requirements"></a>Wymagania

::: moniker range="vs-2017"

- Wymagania dotyczące instalacji znajdują się w temacie [wymagania systemowe rodziny produktów Visual Studio](/visualstudio/productinfo/vs2017-system-requirements-vs).

   > [!IMPORTANT]
   > W przypadku korzystania z systemu Windows 7 lub Windows Server 2008 R2 można opracowywać kod dla aplikacji klasycznych systemu Windows, aplikacji i bibliotek aktywności systemu Android, a także aplikacji i bibliotek kodu dla systemu iOS, ale nie sklepu Windows ani aplikacji platformy UWP.

::: moniker-end
::: moniker range=">=vs-2019"

- Wymagania dotyczące instalacji znajdują się w temacie [wymagania systemowe rodziny produktów Visual Studio](/visualstudio/releases/2019/system-requirements).

   > [!IMPORTANT]
   > W przypadku korzystania z systemu Windows 7 lub Windows Server 2008 R2 można opracowywać kod dla aplikacji klasycznych systemu Windows, aplikacji i bibliotek aktywności systemu Android, a także aplikacji i bibliotek kodu dla systemu iOS, ale nie Windows Phone ani aplikacji platformy UWP.

::: moniker-end

Aby tworzyć aplikacje dla określonych platform urządzeń, istnieją pewne dodatkowe wymagania:

- Emulatory x86 systemu Android, które wykorzystują Android SDK, działają najlepiej na komputerach, które mogą korzystać z przyspieszania sprzętowego, takiego jak Intel Hardware Accelerated Execution Manager (HAXM). Aby uzyskać więcej informacji, zobacz [przyspieszanie sprzętowe dla wydajności emulatora (Hyper-V & HAXM)](/xamarin/android/get-started/installation/android-emulator/hardware-acceleration?tabs=vswin&pivots=windows).

- Kompilowanie kodu dla systemu iOS wymaga identyfikatora Apple ID, konta programu dla deweloperów systemu iOS i komputera Mac, na którym można uruchomić program [Xcode](https://developer.apple.com/xcode/) w wersji 10,2 lub nowszej w systemie OS X Mavericks (wersja 10,9) lub nowszym. Aby uzyskać link do kroków instalacji, zobacz [Instalowanie narzędzi dla systemu iOS](#install-tools-for-ios).

- Emulatory Windows Phone wymagają komputera z uruchomioną funkcją Hyper-V. Funkcja Hyper-V w systemie Windows musi być włączona, aby można było instalować i uruchamiać emulatory. Aby uzyskać więcej informacji, zobacz [wymagania systemowe](/visualstudio/cross-platform/system-requirements-for-the-visual-studio-emulator-for-android)emulatora.

## <a name="get-the-tools"></a>Pobierz narzędzia

Programowanie aplikacji mobilnych za pomocą języka C++ jest dostępne w wersjach Visual Studio Community, Professional i Enterprise. Aby uzyskać program Visual Studio, przejdź do strony [plików do pobrania programu Visual Studio](https://visualstudio.microsoft.com/downloads/) . Narzędzia do tworzenia aplikacji mobilnych dla wielu platform są dostępne począwszy od programu Visual Studio 2015.

## <a name="install-the-tools"></a>Instalowanie narzędzi

Instalator programu Visual Studio obejmuje **opracowywanie aplikacji mobilnych przy użyciu obciążenia języka C++** . To obciążenie powoduje zainstalowanie narzędzi języka C++, szablonów i składników, które są wymagane do tworzenia aplikacji dla systemów Android i iOS w programie Visual Studio. Obejmuje to zestawy narzędzi w zatoce i Clang, które są niezbędne do kompilowania i debugowania systemu Android. Obciążenie instaluje Android SDK i składniki do komunikowania się z komputerem Mac do tworzenia aplikacji dla systemu iOS. Instaluje także narzędzia innych firm i zestawy SDK, które są wymagane do obsługi projektowania aplikacji dla systemów iOS i Android. Większość tych narzędzi innych firm to oprogramowanie typu open source wymagane do obsługi platformy Android.

- Zestaw Android Native Development Kit (NDK), Apache Ant i narzędzia deweloperskie dla systemu Android w języku C++ są wymagane do kompilowania kodu C++ przeznaczonego dla platformy Android.

  > [!NOTE]
  > Niektóre narzędzia w systemie Android NDK nie obsługują znaków Unicode w ścieżkach plików i nazwach plików. Jeśli projekt lub plik źródłowy zawiera znaki Unicode w ścieżce lub nazwie pliku, kompilacja zakończy się niepowodzeniem.

- Usługi Google Emulator systemu Android i Intel Hardware Accelerated Execution Manager (HAXM) są opcjonalne, ale zalecane. (Sterowniki Intel HAXM działają tylko na procesorach firmy Intel i są niezgodne z niektórymi maszynami wirtualnymi, w tym funkcją Hyper-V). Można opracowywać i debugować bezpośrednio na urządzeniu z systemem Android, ale często łatwiej jest użyć emulatora na pulpicie na potrzeby debugowania.

- Narzędzia programistyczne w języku c++ dla systemu iOS są wymagane do kompilowania kodu C++ przeznaczonego dla platformy iOS.

> [!NOTE]
> Jeśli używasz programu Visual Studio 2015, zobacz [Install Visual C++ dla opracowywania aplikacji mobilnych na wiele platform (Visual Studio 2015)](install-visual-cpp-for-cross-platform-mobile-development.md?view=vs-2015&preserve-view=true)

### <a name="install-the-mobile-development-with-c-workload"></a>Instalowanie tworzenia aplikacji mobilnych przy użyciu obciążenia języka C++

1. Uruchom **Instalator programu Visual Studio** z menu **Start** .

1. Jeśli masz już zainstalowany program Visual Studio, wybierz przycisk **Modyfikuj** dla zainstalowanej wersji programu Visual Studio, którą chcesz zmodyfikować. W przeciwnym razie wybierz pozycję **Zainstaluj** , aby zainstalować program Visual Studio.

1. Po wybraniu karty **obciążenia** przewiń w dół i wybierz pozycję **Programowanie aplikacji mobilnych za pomocą języka C++** w Instalator programu Visual Studio. Po wybraniu tego obciążenia są również wybierane inne wymagane składniki dla programowania w języku C++. Możesz również wybrać inne obciążenia i poszczególne składniki do zainstalowania w tym samym czasie. Aby utworzyć Międzyplatformowy kod, który również jest ukierunkowany na platformy UWP, wybierz **platforma uniwersalna systemu Windows obciążenie programowaniem** .

1. W okienku **szczegóły instalacji** rozwiń pozycję **Programowanie aplikacji mobilnych za pomocą języka C++**. W **opcjonalnej** sekcji można wybrać dodatkowe wersje NDK, Google emulator systemu Android, Intel Hardware Accelerated Execution Manager i narzędzie IncrediBuild Build Acceleration.

1. Domyślnie co najmniej jeden składnik instalatora Android SDK jest uwzględniony w obciążeniu. Dostępne są dodatkowe wersje Android SDK. Aby dodać jeden do instalacji, wybierz kartę **poszczególne składniki** , a następnie przewiń w dół do sekcji **zestawy SDK, biblioteki i struktury** , aby wybrać opcję.

1. Wybierz przycisk **Modyfikuj** lub **Zainstaluj** , aby zainstalować **Programowanie aplikacji mobilnych przy użyciu obciążenia języka C++** oraz innych wybranych obciążeń i składników opcjonalnych.

   Po zakończeniu instalacji zamknij Instalatora, a następnie uruchom ponownie komputer. Niektóre akcje Instalatora dla składników innych firm nie zaczną obowiązywać do momentu ponownego uruchomienia komputera.

   > [!IMPORTANT]
   > Musisz ponownie uruchomić system, aby upewnić się, że wszystko jest poprawnie zainstalowane.

1. Otwórz program Visual Studio.

## <a name="install-tools-for-ios"></a>Zainstaluj narzędzia dla systemu iOS

Możesz użyć programu Visual Studio do edytowania, debugowania i wdrażania kodu systemu iOS w symulatorze systemu iOS. Lub do urządzenia z systemem iOS. Ze względu na ograniczenia licencjonowania kod musi być skompilowany zdalnie na komputerze Mac. Aby kompilować i uruchamiać aplikacje dla systemu iOS przy użyciu programu Visual Studio, należy najpierw skonfigurować i skonfigurować agenta zdalnego na komputerze Mac. Szczegółowe instrukcje dotyczące instalacji, wymagania wstępne i opcje konfiguracji znajdują się w temacie [Instalowanie i Konfigurowanie narzędzi do kompilowania przy użyciu systemu iOS](../cross-platform/install-and-configure-tools-to-build-using-ios.md). Jeśli nie tworzysz dla systemu iOS, możesz pominąć ten krok.

## <a name="install-or-update-dependencies-manually"></a>Ręczne instalowanie lub aktualizowanie zależności

Nie trzeba instalować wszystkich zależności innych firm podczas instalowania **aplikacji mobilnych przy użyciu obciążenia języka C++** (lub w programie Visual Studio 2015 — opcja tworzenia aplikacji mobilnych Visual C++). Zainstaluj je później, wykonując kroki opisane w temacie [Instalowanie narzędzi](#install-the-tools). Instalator programu Visual Studio jest regularnie aktualizowana w celu zainstalowania najnowszych składników innych firm. Służy do instalowania zaktualizowanych zestawów SDK i NDKs. Można także zainstalować lub zaktualizować je niezależnie od programu Visual Studio.

Aby zaktualizować zestaw SDK, możesz ponownie uruchomić aplikację Menedżer zestawów SDK w katalogu Android SDK. I, aby zainstalować opcjonalne narzędzia i dodatkowe poziomy interfejsu API. Instalacja aktualizacji może się nie powieść, jeśli nie zostanie użyta funkcja **Uruchom jako administrator** do uruchomienia aplikacji Menedżera zestawów SDK. Jeśli masz problemy z tworzeniem aplikacji dla systemu Android, zapoznaj się z menedżerem zestawu SDK, aby uzyskać aktualizacje zainstalowanych zestawów SDK.

Aby używać niektórych emulatorów Android SDK, może być konieczne skonfigurowanie przyspieszania sprzętowego. Aby uzyskać więcej informacji, zobacz [przyspieszanie sprzętowe dla wydajności emulatora (Hyper-V & HAXM)](/xamarin/android/get-started/installation/android-emulator/hardware-acceleration?tabs=vswin).

W większości przypadków program Visual Studio może wykryć konfiguracje dla zainstalowanego oprogramowania innych firm. Zachowuje ścieżki instalacyjne w wewnętrznych zmiennych środowiskowych. Można zastąpić domyślne ścieżki tych narzędzi programistycznych dla wielu platform w środowisku IDE programu Visual Studio.

### <a name="to-set-the-paths-for-third-party-tools"></a>Aby ustawić ścieżki dla narzędzi innych firm

1. Na pasku menu programu Visual Studio wybierz pozycję **Narzędzia**  >  **Opcje**.

1. W oknie dialogowym **Opcje** wybierz pozycję **cross platform**  >  **C++**  >  **Android**.

   ![Opcje ścieżek narzędzi systemu Android](../cross-platform/media/cppmdd-options-android.png "Opcje ścieżek narzędzi systemu Android")

1. Aby zmienić ścieżkę używaną przez narzędzie, zaznacz pole wyboru obok ścieżki i Edytuj ścieżkę folderu w polu tekstowym. Możesz również użyć przycisku przeglądania (**...**), aby otworzyć okno dialogowe **Wybieranie lokalizacji** w celu wybrania folderu.

1. Wybierz **przycisk OK** , aby zapisać lokalizacje folderów narzędzi niestandardowych.

## <a name="see-also"></a>Zobacz także

[Instalowanie i Konfigurowanie narzędzi do kompilowania przy użyciu systemu iOS](install-and-configure-tools-to-build-using-ios.md)\
[Visual C++ aplikacji mobilnych na wiele platform](https://visualstudio.microsoft.com/vs/features/cplusplus-mdd/)
