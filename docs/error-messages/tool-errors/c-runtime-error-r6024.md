---
description: Dowiedz się więcej o błędzie środowiska uruchomieniowego C R6024
title: Błąd czasu wykonania języka C R6024
ms.date: 11/04/2016
f1_keywords:
- R6024
helpviewer_keywords:
- R6024
ms.assetid: 0fb11c0f-9b81-4cab-81bd-4785742946a5
ms.openlocfilehash: 165592e87eb38ab68c2435cc0a8ca53eb3bc16ba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97237598"
---
# <a name="c-runtime-error-r6024"></a>Błąd czasu wykonania języka C R6024

za mało miejsca na _onexit tabeli/atexit

> [!NOTE]
> Jeśli ten komunikat o błędzie wystąpi podczas uruchamiania aplikacji, aplikacja została zamknięta, ponieważ ma problem z pamięcią wewnętrzną. Ten błąd jest zwykle spowodowany przez bardzo małą ilość pamięci lub rzadko przez usterkę w programie lub uszkodzenie bibliotek Visual C++, z których korzysta.
>
> Możesz wypróbować następujące kroki, aby naprawić ten błąd:
>
> - Zamknij inne uruchomione aplikacje lub Uruchom ponownie komputer, aby zwolnić pamięć.
> - Użyj strony **aplikacje i funkcje** lub **programy i funkcje** w **Panelu sterowania** , aby naprawić lub ponownie zainstalować program.
> - Użyj strony **aplikacje i funkcje** lub **programy i funkcje** w **Panelu sterowania** , aby naprawić lub ponownie zainstalować wszystkie kopie pakietu redystrybucyjnego Microsoft Visual C++.
> - Sprawdź, **Windows Update** w **Panelu sterowania** aktualizacje oprogramowania.
> - Sprawdź dostępność zaktualizowanej wersji aplikacji. Jeśli problem będzie nadal występował, skontaktuj się z dostawcą aplikacji.

**Informacje dla programistów**

Ten błąd występuje, ponieważ dla funkcji or nie jest dostępna żadna pamięć `_onexit` `atexit` . Ten błąd jest spowodowany przez warunek braku pamięci. Możesz rozważyć wstępne przydzielanie buforów podczas uruchamiania aplikacji, aby pomóc w zapisywaniu danych użytkownika i wykonywaniu czystego działania aplikacji w warunkach braku pamięci.
