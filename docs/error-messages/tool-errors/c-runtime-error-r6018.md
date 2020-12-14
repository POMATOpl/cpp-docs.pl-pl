---
description: Dowiedz się więcej o błędzie środowiska uruchomieniowego C R6018
title: Błąd czasu wykonania języka C R6018
ms.date: 11/04/2016
f1_keywords:
- R6018
helpviewer_keywords:
- R6018
ms.assetid: f6dd40d1-a119-4d8b-b39e-97350ea23349
ms.openlocfilehash: 778b57c7071ab6ce042c9e1c434541c1dbcfad13
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97237663"
---
# <a name="c-runtime-error-r6018"></a>Błąd czasu wykonania języka C R6018

nieoczekiwany błąd sterty

> [!NOTE]
> Jeśli ten komunikat o błędzie wystąpi podczas uruchamiania aplikacji, aplikacja została zamknięta, ponieważ ma problem wewnętrzny. Istnieje kilka możliwych przyczyn tego błędu, ale często jest to spowodowane usterką w kodzie aplikacji.
>
> Możesz wypróbować następujące kroki, aby naprawić ten błąd:
>
> - Użyj strony **aplikacje i funkcje** lub **programy i funkcje** w **Panelu sterowania** , aby naprawić lub ponownie zainstalować program.
> - Sprawdź, **Windows Update** w **Panelu sterowania** aktualizacje oprogramowania.
> - Sprawdź dostępność zaktualizowanej wersji aplikacji. Jeśli problem będzie nadal występował, skontaktuj się z dostawcą aplikacji.

**Informacje dla programistów**

Program napotkał nieoczekiwany błąd podczas wykonywania operacji zarządzania pamięcią.

Ten błąd występuje zazwyczaj, gdy program przypadkowo zmienia dane sterty czasu wykonywania. Jednak może być również przyczyną błędu wewnętrznego w środowisku uruchomieniowym lub kodzie systemu operacyjnego.

Aby rozwiązać ten problem, sprawdź, czy w kodzie nie występują usterki dotyczące uszkodzenia sterty. Aby uzyskać więcej informacji i przykładów, zobacz [szczegóły sterty debugowania CRT](/visualstudio/debugger/crt-debug-heap-details). Następnie sprawdź, czy używasz najnowszych pakietów redystrybucyjnych dla wdrożenia aplikacji. Aby uzyskać więcej informacji, zobacz [wdrażanie w Visual C++](../../windows/deployment-in-visual-cpp.md).
