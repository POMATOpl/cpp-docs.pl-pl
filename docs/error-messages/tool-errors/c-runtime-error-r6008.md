---
description: Dowiedz się więcej o błędzie środowiska uruchomieniowego C R6008
title: Błąd czasu wykonania języka C R6008
ms.date: 11/04/2016
f1_keywords:
- R6008
helpviewer_keywords:
- R6008
ms.assetid: f0f304fc-709a-4843-bc7e-bad1ae0d1649
ms.openlocfilehash: d74bd647a4a4d844bb0b9bf0fe2f2d53994dc9ab
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97237782"
---
# <a name="c-runtime-error-r6008"></a>Błąd czasu wykonania języka C R6008

za mało miejsca na argumenty

> [!NOTE]
> Jeśli ten komunikat o błędzie wystąpi podczas uruchamiania aplikacji, aplikacja została zamknięta, ponieważ ma problem z pamięcią wewnętrzną. Istnieje kilka możliwych przyczyn tego błędu, ale często jest to spowodowane bardzo małą ilością pamięci, zbyt dużą ilością pamięci przez zmienne środowiskowe lub usterką w programie.
>
> Możesz wypróbować następujące kroki, aby naprawić ten błąd:
>
> - Zamknij inne uruchomione aplikacje lub Uruchom ponownie komputer, aby zwolnić pamięć.
> - Zmniejsz liczbę i rozmiar argumentów wiersza polecenia do aplikacji.
> - Użyj strony **aplikacje i funkcje** lub **programy i funkcje** w **Panelu sterowania** , aby naprawić lub ponownie zainstalować program.
> - Sprawdź, **Windows Update** w **Panelu sterowania** aktualizacje oprogramowania.
> - Sprawdź dostępność zaktualizowanej wersji aplikacji. Jeśli problem będzie nadal występował, skontaktuj się z dostawcą aplikacji.

**Informacje dla programistów**

Za mało pamięci, aby załadować program, ale za mało pamięci, aby utworzyć tablicę **argv** . Może to być spowodowane bardzo małą ilością pamięci lub niezazwyczaj dużymi wierszami poleceń lub użyciem zmiennej środowiskowej. Rozważ jedno z następujących rozwiązań:

- Zwiększ ilość pamięci dostępnej dla programu.

- Zmniejsz liczbę i rozmiar argumentów wiersza polecenia.

- Zmniejsz rozmiar środowiska, usuwając zbędne zmienne.
