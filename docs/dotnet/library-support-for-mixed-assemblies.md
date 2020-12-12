---
description: 'Dowiedz się więcej o: obsługa bibliotek dla zestawów mieszanych'
title: Obsługa bibliotek dla zestawów mieszanych
ms.date: 09/18/2018
helpviewer_keywords:
- msvcm90[d].dll
- mixed assemblies [C++], library support
- msvcmrt[d].lib
- libraries [C++], mixed assemblies
ms.assetid: 1229595c-9e9d-414d-b018-b4e4c727576d
ms.openlocfilehash: d20069c2caa1cf46ebdb54907de586630d4ee71c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113717"
---
# <a name="library-support-for-mixed-assemblies"></a>Obsługa bibliotek dla zestawów mieszanych

Visual C++ obsługuje użycie standardowej biblioteki języka C++, biblioteki środowiska uruchomieniowego języka C (CRT), ATL i MFC dla aplikacji skompilowanych za pomocą opcji [/CLR (Kompilacja środowiska uruchomieniowego CLR)](../build/reference/clr-common-language-runtime-compilation.md). Dzięki temu istniejące aplikacje, które używają tych bibliotek, mogą również używać funkcji .NET Framework.

> [!IMPORTANT]
> **/CLR: Pure** i **/CLR:** opcje kompilatora bezpiecznego są przestarzałe w programie Visual Studio 2015 i nieobsługiwane w programie Visual Studio 2017.

Ta obsługa obejmuje następujące biblioteki DLL i importowania:

- Msvcmrt [d]. lib w przypadku kompilowania z **/CLR**. Linki zestawów mieszanych z tą biblioteką importu.

Ta obsługa obejmuje kilka pokrewnych korzyści:

- Standardowa Biblioteka CRT i C++ jest dostępna do kodu mieszanego. Udostępniona biblioteka standardowa CRT i C++ nie jest możliwa do zweryfikowania; ostatecznie Twoje wywołania są nadal kierowane do tej samej standardowej biblioteki CRT i C++, jak używane z kodu natywnego.

- Popraw ujednoliconą obsługę wyjątków w obrazach mieszanych.

- Statyczne Inicjowanie zmiennych C++ w mieszanych obrazach.

- Obsługa zmiennych dla poszczególnych domen i procesów w kodzie zarządzanym.

- Rozwiązuje problemy z blokadą modułu ładującego stosowane do mieszanych bibliotek DLL skompilowanych w programie Visual Studio 2003 i wcześniejszych.

Ponadto w tej obsłudze przedstawiono następujące ograniczenia:

- Tylko model CRT DLL jest obsługiwany dla kodu skompilowanego z **/CLR**. Nie istnieją statyczne biblioteki CRT obsługujące kompilacje **/CLR** .

## <a name="see-also"></a>Zobacz też

- [Zestawy mieszane (natywne i zarządzane)](../dotnet/mixed-native-and-managed-assemblies.md)
