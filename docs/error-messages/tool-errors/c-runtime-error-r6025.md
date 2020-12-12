---
description: Dowiedz się więcej o błędzie środowiska uruchomieniowego C R6025
title: Błąd czasu wykonania języka C R6025
ms.date: 11/04/2016
f1_keywords:
- R6025
helpviewer_keywords:
- R6025
ms.assetid: afa06d98-9c36-445b-b3e7-b6409bc8e779
ms.openlocfilehash: 7bf3213d81e144f14f6eeb25f108f497267ec4d2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97237572"
---
# <a name="c-runtime-error-r6025"></a>Błąd czasu wykonania języka C R6025

czyste wywołanie funkcji wirtualnej

> [!NOTE]
> Jeśli ten komunikat o błędzie wystąpi podczas uruchamiania aplikacji, aplikacja została zamknięta, ponieważ ma problem wewnętrzny. Najbardziej typową przyczyną tego błędu jest usterka w aplikacji lub uszkodzenie instalacji.
>
> Możesz wypróbować następujące kroki, aby naprawić ten błąd:
>
> - Użyj strony **aplikacje i funkcje** lub **programy i funkcje** w **Panelu sterowania** , aby naprawić lub ponownie zainstalować program.
> - Sprawdź, **Windows Update** w **Panelu sterowania** aktualizacje oprogramowania.
> - Sprawdź dostępność zaktualizowanej wersji aplikacji. Jeśli problem będzie nadal występował, skontaktuj się z dostawcą aplikacji.

**Informacje dla programistów**

Nie utworzono wystąpienia obiektu do obsługi czystego wywołania funkcji wirtualnej.

Ten błąd jest spowodowany wywoływaniem funkcji wirtualnej w abstrakcyjnej klasie podstawowej za pomocą wskaźnika, który jest tworzony przez rzutowanie do typu klasy pochodnej, ale w rzeczywistości jest wskaźnikiem do klasy bazowej. Może się to zdarzyć podczas rzutowania z **`void`** <strong>\*</strong> na wskaźnik do klasy, gdy **`void`** <strong>\*</strong> został utworzony podczas konstruowania klasy bazowej.
