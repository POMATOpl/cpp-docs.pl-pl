---
description: Dowiedz się więcej o błędzie środowiska uruchomieniowego C R6016
title: Błąd czasu wykonania języka C R6016
ms.date: 11/04/2016
f1_keywords:
- R6016
helpviewer_keywords:
- R6016
ms.assetid: 7bd3f274-d9c4-4bc4-8252-80bf168c4c3a
ms.openlocfilehash: 79339400436f21aefc0edea101b4642d443f5ce0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97237689"
---
# <a name="c-runtime-error-r6016"></a>Błąd czasu wykonania języka C R6016

za mało miejsca dla danych wątku

> [!NOTE]
> Jeśli ten komunikat o błędzie wystąpi podczas uruchamiania aplikacji, aplikacja została zamknięta, ponieważ ma problem z pamięcią wewnętrzną. Istnieje wiele możliwych przyczyn tego błędu, ale często jest to spowodowane bardzo małą ilością pamięci, usterką w aplikacji lub usterką w dodatku lub rozszerzeniu używanym przez aplikację.
>
> Możesz wypróbować następujące kroki, aby naprawić ten błąd:
>
> - Zamknij inne uruchomione aplikacje lub Uruchom ponownie komputer, aby zwolnić pamięć.
> - Użyj strony **aplikacje i funkcje** lub **programy i funkcje** w **Panelu sterowania** , aby naprawić lub ponownie zainstalować aplikację.
> - Użyj strony **aplikacje i funkcje** lub **programy i funkcje** w **Panelu sterowania** , aby usunąć, naprawić lub ponownie zainstalować dodatki lub rozszerzenia używane przez aplikację.
> - Sprawdź, **Windows Update** w **Panelu sterowania** aktualizacje oprogramowania.
> - Sprawdź dostępność zaktualizowanej wersji aplikacji. Jeśli problem będzie nadal występował, skontaktuj się z dostawcą aplikacji.

**Informacje dla programistów**

Ten błąd występuje, ponieważ program nie otrzymał wystarczającej ilości pamięci od systemu operacyjnego w celu ukończenia [_beginthread](../../c-runtime-library/reference/beginthread-beginthreadex.md) lub `_beginthreadex` wywołania lub lokalnego magazynu wątków nie został zainicjowany przez `_beginthread` lub `_beginthreadex` .

W momencie rozpoczynania nowego wątku biblioteka musi utworzyć wewnętrzną bazę danych dla tego wątku. Jeśli baza danych nie może zostać rozszerzona przy użyciu pamięci dostarczonej przez system operacyjny, wątek się nie rozpoczyna, a proces wywołujący się zatrzymuje. Może się to zdarzyć, gdy proces utworzył zbyt wiele wątków lub gdy pamięć lokalna wątku została wyczerpana.

Zalecamy, aby plik wykonywalny, który wywołuje bibliotekę środowiska uruchomieniowego języka C (CRT), był używany `_beginthreadex` do tworzenia wątków zamiast interfejsu API systemu Windows `CreateThread` . `_beginthreadex` Inicjuje wewnętrzny magazyn statyczny używany przez wiele funkcji CRT w lokalnym magazynie wątków. Jeśli używasz `CreateThread` do tworzenia wątku, CRT może zakończyć proces z R6016, gdy wywołanie jest wykonywane do funkcji CRT, która wymaga zainicjowania wewnętrznego magazynu statycznego.
