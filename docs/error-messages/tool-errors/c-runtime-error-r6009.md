---
description: Dowiedz się więcej o błędzie środowiska uruchomieniowego C R6009
title: Błąd czasu wykonania języka C R6009
ms.date: 11/04/2016
f1_keywords:
- R6009
helpviewer_keywords:
- R6009
ms.assetid: edfb1f8b-3807-48f4-a994-318923b747ae
ms.openlocfilehash: 797e1f98247705afcacc59c0372e241748154a0a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97237715"
---
# <a name="c-runtime-error-r6009"></a>Błąd czasu wykonania języka C R6009

za mało miejsca na środowisko

> [!NOTE]
> Jeśli ten komunikat o błędzie wystąpi podczas uruchamiania aplikacji, aplikacja została zamknięta, ponieważ ma problem z pamięcią wewnętrzną. Istnieje kilka możliwych przyczyn tego błędu, ale często jest to spowodowane bardzo małą ilością pamięci, zbyt dużą ilością pamięci przez zmienne środowiskowe lub usterką w programie.
>
> Możesz wypróbować następujące kroki, aby naprawić ten błąd:
>
> - Zamknij inne uruchomione aplikacje lub Uruchom ponownie komputer, aby zwolnić pamięć.
> - Użyj strony **aplikacje i funkcje** lub **programy i funkcje** w **Panelu sterowania** , aby naprawić lub ponownie zainstalować program.
> - Sprawdź, **Windows Update** w **Panelu sterowania** aktualizacje oprogramowania.
> - Sprawdź dostępność zaktualizowanej wersji aplikacji. Jeśli problem będzie nadal występował, skontaktuj się z dostawcą aplikacji.

**Informacje dla programistów**

Za mało pamięci, aby załadować program, ale za mało pamięci, aby utworzyć tablicę **envp** .  Przyczyną może być bardzo mała ilość pamięci lub niezazwyczaj duże użycie zmiennej środowiskowej. Rozważ jedno z następujących rozwiązań:

- Zwiększ ilość pamięci dostępnej dla programu.

- Zmniejsz liczbę i rozmiar argumentów wiersza polecenia.

- Zmniejsz rozmiar środowiska, usuwając zbędne zmienne.
