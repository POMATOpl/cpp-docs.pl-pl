---
description: 'Dowiedz się więcej na temat: dodatek MFC MBCS DLL'
title: Dodatek MFC MBCS DLL Add-on
ms.date: 12/02/2019
helpviewer_keywords:
- MBCS
- MFC
ms.openlocfilehash: 8961fe65937d53c2aa056b7061548710e0c80286
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97122775"
---
# <a name="mfc-mbcs-dll-add-on"></a>Dodatek MFC MBCS DLL Add-on

Obsługa biblioteki MFC i jej bibliotek zestawów znaków wielobajtowych (MBCS) wymaga dodatkowego kroku podczas instalacji programu Visual Studio w Visual Studio 2013 i nowszych.

**Visual Studio 2013**: Domyślnie biblioteki MFC zainstalowane w programie Visual Studio 2013 obsługują tylko programowanie w formacie Unicode. Aby można było skompilować projekt MFC w Visual Studio 2013, który ma właściwość **zestawu znaków** ustawioną na **Używanie zestawu znaków wielobajtowych** lub **nie jest ustawiony**, potrzebne są biblioteki DLL MBCS. Pobierz bibliotekę DLL w [bibliotece MFC wielobajtowej dla Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40770).

**Visual Studio 2015**: w składnikach Instalatora Visual C++ są zawarte zarówno biblioteki DLL w formacie Unicode, jak i MBCS, ale obsługa MFC nie jest instalowana domyślnie. Visual C++ i MFC są opcjonalnymi konfiguracjami instalacji w Instalatorze programu Visual Studio. Aby upewnić się, że biblioteka MFC jest zainstalowana, wybierz pozycję **niestandardowe** w instalatorze i w obszarze **Języki programowania** upewnij się, że wybrano **Visual C++** i **Microsoft Foundation Classes dla języka C++** . Jeśli zainstalowano już program Visual Studio, podczas próby utworzenia projektu MFC zostanie wyświetlony monit o zainstalowanie Visual C++ i/lub MFC.

**Visual Studio 2017 i nowsze**: biblioteki MFC w formacie Unicode i MBCS są instalowane wraz z **programowaniem aplikacji klasycznych w języku C++** w przypadku wybrania **obsługi MFC i ATL** z okienka **składniki opcjonalne** w programie Instalator programu Visual Studio. Jeśli instalacja nie obejmuje tych składników, przejdź do **pliku | Nowe projekty** okno dialogowe, a następnie kliknij link **Otwórz Instalator programu Visual Studio** . Aby uzyskać więcej informacji, zobacz [Instalowanie programu Visual Studio](/visualstudio/install/install-visual-studio).

## <a name="see-also"></a>Zobacz też

[Wersje biblioteki MFC](mfc-library-versions.md)
