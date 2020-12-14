---
description: Dowiedz się więcej o błędzie środowiska uruchomieniowego C R6032
title: Błąd czasu wykonania języka C R6032
ms.date: 11/04/2016
f1_keywords:
- R6032
helpviewer_keywords:
- R6032
ms.assetid: 52092a63-cc51-444a-bfc3-fad965a3558e
ms.openlocfilehash: b0fbc7730867fb6e9045adf4e5e2b8667f741784
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97275896"
---
# <a name="c-runtime-error-r6032"></a>Błąd czasu wykonania języka C R6032

Za mało miejsca na informacje o ustawieniach regionalnych

> [!NOTE]
> Jeśli ten komunikat o błędzie wystąpi podczas uruchamiania aplikacji, aplikacja została zamknięta, ponieważ ma problem z pamięcią wewnętrzną. Istnieje kilka możliwych przyczyn tego błędu, ale często jest to spowodowane bardzo małą ilością pamięci lub usterką w programie.
>
> Możesz wypróbować następujące kroki, aby naprawić ten błąd:
>
> - Zamknij inne uruchomione aplikacje lub Uruchom ponownie komputer, aby zwolnić pamięć.
> - Użyj strony **aplikacje i funkcje** lub **programy i funkcje** w **Panelu sterowania** , aby naprawić lub ponownie zainstalować program.
> - Sprawdź, **Windows Update** w **Panelu sterowania** aktualizacje oprogramowania.
> - Sprawdź dostępność zaktualizowanej wersji aplikacji. Jeśli problem będzie nadal występował, skontaktuj się z dostawcą aplikacji.

**Informacje dla programistów**

Środowisko uruchomieniowe utrzymuje informacje o ustawieniach regionalnych poszczególnych wątków, aby można było przetwarzać wywołania do funkcji zależnych od ustawień regionalnych. Jeśli alokacja pamięci dla tych informacji nie powiedzie się, środowisko uruchomieniowe nie może działać, ponieważ zależą od niej zbyt wiele podstawowych funkcji.
