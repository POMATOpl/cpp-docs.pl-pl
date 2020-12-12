---
description: 'Dowiedz się więcej na temat: jak kontrola konta użytkownika (UAC) wpływa na aplikację'
title: Jak kontrola konta użytkownika (UAC) wpływa na aplikację?
ms.date: 11/19/2018
helpviewer_keywords:
- UAC [C++]
- security [C++], User Account Control
- user accounts [C++]
- User Account Control [C++]
ms.assetid: 0d001870-253e-4989-b689-f78035953799
ms.openlocfilehash: 64196e0cac0a5b4edcf0b24fd95df2e5291ec45a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320069"
---
# <a name="how-user-account-control-uac-affects-your-application"></a>Jak kontrola konta użytkownika (UAC) wpływa na aplikację?

Kontrola konta użytkownika (UAC) to funkcja systemu Windows Vista, w której konta użytkowników mają ograniczone uprawnienia. Szczegółowe informacje na temat funkcji Kontrola konta użytkownika można znaleźć w następujących lokacjach:

- [Najlepsze rozwiązania i wskazówki dla deweloperów dotyczące aplikacji w środowisku najmniej uprzywilejowanym](/windows/win32/uxguide/winenv-uac)

## <a name="building-projects-after-enabling-uac"></a>Kompilowanie projektów po włączeniu funkcji Kontrola konta użytkownika

W przypadku tworzenia projektu programu Visual Studio C++ w systemie Windows Vista z wyłączonymi kontrolami konta użytkownika i włączeniu funkcji Kontrola konta użytkownika należy wyczyścić i ponownie skompilować projekt, aby działał poprawnie.

## <a name="applications-that-require-administrative-privileges"></a>Aplikacje wymagające uprawnień administracyjnych

Domyślnie konsolidator Visual C++ osadza fragment kontroli konta użytkownika w manifeście aplikacji z poziomem wykonania `asInvoker` . Jeśli aplikacja wymaga uprawnień administracyjnych do prawidłowego działania (na przykład jeśli modyfikuje węzeł HKLM rejestru lub zapisuje je w chronionych obszarach dysku, takich jak katalog systemu Windows), należy zmodyfikować aplikację.

Pierwsza opcja polega na zmodyfikowaniu fragmentu UAC manifestu w celu zmiany poziomu wykonywania na *wymaga administratora*. Następnie aplikacja będzie monitować użytkownika o poświadczenia administracyjne przed jego uruchomieniem. Aby uzyskać informacje o tym, jak to zrobić, zobacz [/MANIFESTUAC (osadza informacje UAC w manifeście)](../build/reference/manifestuac-embeds-uac-information-in-manifest.md).

Druga opcja polega na tym, że nie można osadzić fragmentu UAC w manifeście przez określenie `/MANIFESTUAC:NO` opcji konsolidatora. W takim przypadku aplikacja zostanie uruchomiona Zwirtualizowana. Wszelkie zmiany wprowadzone w rejestrze lub w systemie plików nie będą zachowywane po zakończeniu Twojej aplikacji.

Poniższy schemat blokowy opisuje sposób działania aplikacji w zależności od tego, czy funkcja Kontrola konta użytkownika jest włączona, oraz czy aplikacja ma manifest UAC:

![Zachowanie modułu ładującego systemu Windows](media/uacflowchart.png "Zachowanie modułu ładującego systemu Windows")

## <a name="see-also"></a>Zobacz też

[Najlepsze rozwiązania w zakresie zabezpieczeń](security-best-practices-for-cpp.md)
