---
title: Microsoft C++ porting and upgrading guide
description: Upgrade Microsoft C++ code to the latest version of Visual Studio.
ms.date: 11/18/2019
ms.assetid: f5fbcc3d-aa72-41a6-ad9a-a706af2166fb
ms.topic: overview
ms.openlocfilehash: 88b5b31428979d26bbbf810c4c04c99f411dbcbb
ms.sourcegitcommit: 217fac22604639ebd62d366a69e6071ad5b724ac
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/19/2019
ms.locfileid: "74189346"
---
# <a name="microsoft-c-porting-and-upgrading-guide"></a>Microsoft C++ porting and upgrading guide

This article provides a guide for upgrading Microsoft C++ code to the latest version of Visual Studio. For projects created in Visual Studio 2010 through 2015, just open the project in Visual Studio 2019. You can upgrade a Visual Studio 2008 or earlier project in two steps. Use Visual Studio 2010 to convert the project to MSBuild format first. Then open the project in Visual Studio 2019. For complete instructions, see [Upgrading C++ projects from earlier versions of Visual Studio](upgrading-projects-from-earlier-versions-of-visual-cpp.md).

The toolsets in Visual Studio 2015, Visual Studio 2017, and Visual Studio 2019 are binary-compatible. Now you can upgrade to a more recent version of the compiler without having to upgrade your library dependencies. For more information, see [C++ binary compatibility 2015-2019](binary-compat-2015-2017.md).

When upgrading projects that use open-source libraries or are meant to run on multiple platforms, we recommended migrating to a CMake-based project. For more information, see [CMake projects in Visual Studio](../build/cmake-projects-in-visual-studio.md)

## <a name="reasons-to-upgrade-c-code"></a>Reasons to upgrade C++ code

If a legacy application is running satisfactorily, in a secure environment, and isn't under active development, there might not be much incentive to upgrade it. However, consider an upgrade in these cases: Your application requires ongoing maintenance. Or, you're doing new feature development, or making performance or security improvements. An upgrade brings these benefits:

- The same code can run faster, because we've improved compiler optimizations.

- Modern C++ features and programming practices eliminate many common causes of bugs, and produce code that's far easier to maintain than older C-style idioms.

- Build times are faster, because of performance improvements in the compiler and linker.

- Better standards conformance. The [/permissive-](../build/reference/permissive-standards-conformance.md) compiler option helps you identify code that doesn't conform to the current C++ standard.

- Better run-time security, including more secure [C Runtime library]() features. And, compiler features such as [guard checking](../build/reference/guard-enable-guard-checks.md) and address sanitizers (new in Visual Studio 2019 version 16.4).

## <a name="multitargeting-vs-upgrading"></a>Multitargeting vs. upgrading

Perhaps upgrading your code base to a new toolset isn't an option for you. You can still use the latest Visual Studio to build and edit projects that use older toolsets and libraries. In Visual Studio 2019, you can take advantage of features such as:

- modern static analysis tools, including the C++ Core Guidelines checkers and Clang-Tidy, to help identify potential problems in your source code.

- automatic formatting according to your choice of modern styles can help make legacy code much more readable.

For more information, see [Use native multi-targeting in Visual Studio to build old projects](use-native-multi-targeting.md).

## <a name="in-this-section"></a>W tej sekcji

|Tytuł|Opis|
|-----------|-----------------|
|[Upgrading C++ projects from earlier versions of Visual Studio](upgrading-projects-from-earlier-versions-of-visual-cpp.md)|How to upgrade your code base to Visual Studio 2019 and v142 of the compiler.|
|[IDE tools for upgrading C++ code](ide-tools-for-upgrading-code.md)|Useful IDE features that help in the upgrade process.|
|[C++ binary compatibility 2015-2019](binary-compat-2015-2017.md)|Consume v140 and v141 libraries as-is from v142 projects.|
|[Używanie natywnej wielowersyjności kodu w programie Visual Studio do kompilacji starych projektów](use-native-multi-targeting.md)|Use Visual Studio 2019 with older compilers and libraries.|
|[Visual C++ — historia zmian w latach 2003–2015](visual-cpp-change-history-2003-2015.md)|A list of all the changes in the Microsoft C++ libraries and build tools from Visual Studio 2003 through 2015 that might require changes in your code.|
|[Visual C++ — co nowego od roku 2003 do 2015](visual-cpp-what-s-new-2003-through-2015.md)|All the "what's new" information for Microsoft C++ from Visual Studio 2003 through Visual Studio 2015.|
|[Przenoszenie i uaktualnianie: Przykłady i analizy przypadków](porting-and-upgrading-examples-and-case-studies.md)|For this section, we ported and upgrades several samples and applications and discussed the experiences and results. These articles give you a sense of what's involved in the porting and upgrading process. Throughout the process, we discuss tips and tricks for upgrading and show how specific errors were fixed.|
|[Porting to the Universal Windows Platform](porting-to-the-universal-windows-platform-cpp.md)|Contains information about porting code to Windows 10|
|[Wprowadzenie do programu Visual C++ dla użytkowników systemu UNIX](introduction-to-visual-cpp-for-unix-users.md)|Provides information for UNIX users who are new to Visual C++ and want to become productive with it.|
|[Running Linux programs on Windows](porting-from-unix-to-win32.md)|Discusses options for migrating UNIX applications to Windows.|

## <a name="see-also"></a>Zobacz także

[Język C++ w programie Visual Studio](../overview/visual-cpp-in-visual-studio.md)<br/>
[What's New for The C++ compiler in Visual Studio](../overview/what-s-new-for-visual-cpp-in-visual-studio.md)<br/>
[Ulepszenia zgodności języka C++ w programie Visual Studio](../overview/cpp-conformance-improvements.md)<br/>
