---
description: Dowiedz się więcej o błędzie środowiska uruchomieniowego C R6017
title: Błąd czasu wykonania języka C R6017
ms.date: 11/04/2016
f1_keywords:
- R6017
helpviewer_keywords:
- R6017
ms.assetid: df3ec5f5-6771-4648-ba06-0e26c6a1cc6a
ms.openlocfilehash: 38c4b65ec3d577176485882d6f581bacd2ad007c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97237650"
---
# <a name="c-runtime-error-r6017"></a>Błąd czasu wykonania języka C R6017

nieoczekiwany błąd blokady wielowątkowej

> [!NOTE]
> Jeśli ten komunikat o błędzie wystąpi podczas uruchamiania aplikacji, aplikacja została zamknięta, ponieważ ma problem wewnętrzny. Istnieje kilka możliwych przyczyn tego błędu, ale często jest to spowodowane usterką w kodzie aplikacji.
>
> Możesz wypróbować następujące kroki, aby naprawić ten błąd:
>
> - Użyj strony **aplikacje i funkcje** lub **programy i funkcje** w **Panelu sterowania** , aby naprawić lub ponownie zainstalować program.
> - Sprawdź, **Windows Update** w **Panelu sterowania** aktualizacje oprogramowania.
> - Sprawdź dostępność zaktualizowanej wersji aplikacji. Jeśli problem będzie nadal występował, skontaktuj się z dostawcą aplikacji.

**Informacje dla programistów**

Proces otrzymał nieoczekiwany błąd podczas próby uzyskania dostępu do blokady wielowątkowej środowiska uruchomieniowego C dla zasobu systemowego. Ten błąd występuje zazwyczaj, gdy proces przypadkowo zmienia dane sterty środowiska uruchomieniowego. Jednak może być również przyczyną błędu wewnętrznego w bibliotece środowiska uruchomieniowego lub kodu systemu operacyjnego.

Aby rozwiązać ten problem, sprawdź, czy w kodzie nie występują usterki dotyczące uszkodzenia sterty. Aby uzyskać więcej informacji i przykładów, zobacz [szczegóły sterty debugowania CRT](/visualstudio/debugger/crt-debug-heap-details). Następnie sprawdź, czy używasz najnowszych pakietów redystrybucyjnych dla wdrożenia aplikacji. Aby uzyskać więcej informacji, zobacz [wdrażanie w Visual C++](../../windows/deployment-in-visual-cpp.md).
