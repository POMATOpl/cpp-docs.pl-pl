---
description: Dowiedz się więcej o błędzie środowiska uruchomieniowego C R6028
title: Błąd czasu wykonania języka C R6028
ms.date: 11/04/2016
f1_keywords:
- R6028
helpviewer_keywords:
- R6028
ms.assetid: 81e99079-4388-4244-a4f7-4641c508871c
ms.openlocfilehash: f4b634814331a7301fccef77be31034afc77084a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97301779"
---
# <a name="c-runtime-error-r6028"></a>Błąd czasu wykonania języka C R6028

nie można zainicjować sterty

> [!NOTE]
> Jeśli ten komunikat o błędzie wystąpi podczas uruchamiania aplikacji, aplikacja została zamknięta, ponieważ ma problem z pamięcią wewnętrzną. Istnieje wiele możliwych przyczyn tego błędu, ale często jest to spowodowane bardzo małą ilością pamięci, usterką w programie lub uszkodzonymi sterownikami sprzętowymi.
>
> Możesz wypróbować następujące kroki, aby naprawić ten błąd:
>
> - Zamknij inne uruchomione aplikacje lub Uruchom ponownie komputer, aby zwolnić pamięć.
> - Użyj strony **aplikacje i funkcje** lub **programy i funkcje** w **Panelu sterowania** , aby naprawić lub ponownie zainstalować program.
> - Jeśli aplikacja działała przed ostatnią instalacją innej aplikacji lub sterownika, użyj strony **aplikacje i funkcje** lub **programy i funkcje** w **Panelu sterowania** , aby usunąć nową aplikację lub sterownik, a następnie spróbuj ponownie wykonać swoją aplikację.
> - Sprawdź witrynę sieci Web dostawcy sprzętu lub **Windows Update** w **Panelu sterowania** , aby uzyskać aktualizacje oprogramowania i sterowników.
> - Sprawdź dostępność zaktualizowanej wersji aplikacji. Jeśli problem będzie nadal występował, skontaktuj się z dostawcą aplikacji.

**Informacje dla programistów**

Ten błąd występuje, gdy system operacyjny nie może utworzyć puli pamięci dla aplikacji. W przypadku środowiska uruchomieniowego języka C (CRT) nazywanego funkcją Win32 `HeapCreate` , która zwróciła błąd wskazujący wartość null.

Jeśli ten błąd występuje podczas uruchamiania aplikacji, system może nie być w stanie spełnić żądań sterty, ponieważ ładowane są uszkodzone sterowniki. Sprawdź witrynę Windows Update lub witrynę dostawcy sprzętu, aby uzyskać zaktualizowane sterowniki.
