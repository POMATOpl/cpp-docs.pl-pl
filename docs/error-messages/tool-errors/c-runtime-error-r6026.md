---
description: Dowiedz się więcej o błędzie środowiska uruchomieniowego C R6026
title: Błąd czasu wykonania języka C R6026
ms.date: 11/04/2016
f1_keywords:
- R6026
helpviewer_keywords:
- R6026
ms.assetid: 7ea751f8-fc20-46ab-99ef-84c95ca0b6b4
ms.openlocfilehash: f592cfff4dab72cbaac3d6470fdb2423302a08c2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97237533"
---
# <a name="c-runtime-error-r6026"></a>Błąd czasu wykonania języka C R6026

za mało miejsca na zainicjowanie stdio

> [!NOTE]
> Jeśli ten komunikat o błędzie wystąpi podczas uruchamiania aplikacji, aplikacja została zamknięta, ponieważ ma problem z pamięcią wewnętrzną. Istnieje kilka możliwych przyczyn tego błędu, ale zazwyczaj jest to spowodowane bardzo małą ilością pamięci. Może być również przyczyną błędu w aplikacji przez uszkodzenie bibliotek Visual C++, których używa, lub przez sterownik.
>
> Możesz wypróbować następujące kroki, aby naprawić ten błąd:
>
> - Zamknij inne uruchomione aplikacje lub Uruchom ponownie komputer, aby zwolnić pamięć.
> - Użyj strony **aplikacje i funkcje** lub **programy i funkcje** w **Panelu sterowania** , aby naprawić lub ponownie zainstalować program.
> - Jeśli aplikacja działała przed ostatnią instalacją innej aplikacji lub sterownika, użyj strony **aplikacje i funkcje** lub **programy i funkcje** w **Panelu sterowania** , aby usunąć nową aplikację lub sterownik, a następnie spróbuj ponownie wykonać swoją aplikację.
> - Użyj strony **aplikacje i funkcje** lub **programy i funkcje** w **Panelu sterowania** , aby naprawić lub ponownie zainstalować wszystkie kopie pakietu redystrybucyjnego Microsoft Visual C++.
> - Sprawdź, **Windows Update** w **Panelu sterowania** aktualizacje oprogramowania.
> - Sprawdź dostępność zaktualizowanej wersji aplikacji. Jeśli problem będzie nadal występował, skontaktuj się z dostawcą aplikacji.

**Informacje dla programistów**

Ten błąd występuje w przypadku braku wystarczającej ilości wolnej pamięci umożliwiającej zainicjowanie obsługi standardowej operacji we/wy w środowisku uruchomieniowym języka C. Ten błąd występuje zwykle podczas uruchamiania aplikacji. Sprawdź, czy aplikacja oraz sterowniki i biblioteki DLL, które ładuje, nie uszkadzają sterty podczas uruchamiania.
