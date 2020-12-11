---
description: 'Dowiedz się więcej na temat: jak skonfigurować projekty programu Visual Studio C++ na docelowe 64-bitowe, platformy x64'
title: 'Instrukcje: Konfigurowanie projektów programu Visual Studio C++ do docelowych 64-bitowych, platformy x64'
ms.date: 11/04/2016
helpviewer_keywords:
- platforms [C++], 64-bit
- 64-bit programming [C++], configuring projects
- project configurations [C++]
ms.assetid: 2b9ae001-df36-4750-83b2-982145d632ad
ms.openlocfilehash: 717f9db302f4a7bfef12d30830336b22f9fc5169
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97156375"
---
# <a name="how-to-configure-visual-studio-c-projects-to-target-64-bit-x64-platforms"></a>Instrukcje: Konfigurowanie projektów programu Visual Studio C++ do docelowych 64-bitowych, platformy x64

Możesz użyć konfiguracji projektu w środowisku IDE programu Visual Studio, aby skonfigurować aplikacje w języku C++ na 64-bitowe i x64 platform. Można również migrować ustawienia projektu Win32 do konfiguracji projektu 64-bitowego.

### <a name="to-set-up-c-applications-to-target-64-bit-platforms"></a>Aby skonfigurować aplikacje C++ do docelowych platform 64-bitowych

1. Otwórz projekt w języku C++, który chcesz skonfigurować.

1. Otwórz strony właściwości dla tego projektu. Aby uzyskać więcej informacji, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](working-with-project-properties.md).

   > [!NOTE]
   > W przypadku projektów platformy .NET upewnij się, że w oknie dialogowym **\<Projectname> strony właściwości** jest zaznaczony węzeł **Właściwości konfiguracji** lub jeden z jego węzłów podrzędnych. w przeciwnym razie przycisk **Configuration Manager** pozostanie niedostępny.

1. Wybierz przycisk **Configuration Manager** , aby otworzyć okno dialogowe **Configuration Manager** .

1. Z listy rozwijanej **Active Solution platform** wybierz **\<New...>** opcję, aby otworzyć okno dialogowe **Nowa platforma rozwiązania** .

1. Z listy rozwijanej **Typ lub wybierz nową platformę** wybierz 64-bitową platformę docelową.

   > [!NOTE]
   > W **nowej platformie rozwiązania** okno dialogowe, można użyć opcji **Kopiuj ustawienia z** , aby skopiować istniejące ustawienia projektu do nowej konfiguracji projektu 64-bitowego.

1. Wybierz przycisk **OK** . Platforma wybrana w poprzednim kroku jest wyświetlana w obszarze **Active Solution platform** w oknie dialogowym **Configuration Manager** .

1. Wybierz przycisk **Zamknij** w oknie dialogowym **Configuration Manager** , a następnie wybierz przycisk **OK** w oknie dialogowym **\<Projectname> strony właściwości** .

### <a name="to-copy-win32-project-settings-into-a-64-bit-project-configuration"></a>Aby skopiować ustawienia projektu Win32 do konfiguracji projektu 64-bitowego

- Gdy okno dialogowe **Nowa platforma rozwiązania** jest otwarte podczas konfigurowania projektu jako docelowego dla platformy 64-bitowej, z listy rozwijanej **Kopiuj ustawienia z** wybierz opcję **Win32**. Te ustawienia projektu są automatycznie aktualizowane na poziomie projektu:

  - Opcja konsolidatora [/Machine](reference/machine-specify-target-platform.md) jest ustawiona na **/Machine: x64**.

  - **Rejestr wyjściowy** jest wyłączony. Aby uzyskać więcej informacji, zobacz [strony właściwości konsolidatora](reference/linker-property-pages.md).

  - **Środowisko docelowe** jest ustawione na **/ENV x64**. Aby uzyskać więcej informacji, zobacz [strony właściwości MIDL](reference/midl-property-pages.md).

  - **Sprawdzanie poprawności parametrów** jest wyczyszczone i zresetowane do wartości domyślnej. Aby uzyskać więcej informacji, zobacz [strony właściwości MIDL](reference/midl-property-pages.md).

  - Jeśli **Format informacji o debugowaniu** został ustawiony na **/Zi** w konfiguracji projektu Win32, ustawiany jest **/Zi** w konfiguracji projektu 64-bitowego. Aby uzyskać więcej informacji, zobacz [/Z7,/Zi,/ZI (format informacji o debugowaniu)](reference/z7-zi-zi-debug-information-format.md).

  > [!NOTE]
  > Żadna z tych właściwości projektu nie jest zmieniana, jeśli są one zastępowane na poziomie pliku.

## <a name="see-also"></a>Zobacz też

[Konfigurowanie projektów C++ dla 64-bitowych, docelowych procesorów x64](configuring-programs-for-64-bit-visual-cpp.md)<br/>
[Debuguj 64-bitowe aplikacje](/visualstudio/debugger/debug-64-bit-applications)
