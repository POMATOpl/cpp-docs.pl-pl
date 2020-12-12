---
description: Dowiedz się więcej o błędzie środowiska uruchomieniowego C R6019
title: Błąd czasu wykonania języka C R6019
ms.date: 11/04/2016
f1_keywords:
- R6019
helpviewer_keywords:
- R6019
ms.assetid: 8129923e-7db2-40ee-9602-def9365f8d28
ms.openlocfilehash: 190b836d5c0823b3644e4ff49812b5de05f421e8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97237637"
---
# <a name="c-runtime-error-r6019"></a>Błąd czasu wykonania języka C R6019

nie można otworzyć urządzenia konsoli

> [!NOTE]
> Jeśli ten komunikat o błędzie wystąpi podczas uruchamiania aplikacji, aplikacja została zamknięta, ponieważ próbowała uzyskać dostęp do konsoli, ale nie ma wystarczających uprawnień. Istnieje kilka możliwych przyczyn tego błędu, ale zazwyczaj jest to spowodowane tym, że program musi być uruchomiony jako administrator lub występuje usterka w programie.
>
> Możesz wypróbować następujące kroki, aby naprawić ten błąd:
>
> - Uruchom program jako administrator.
> - Użyj strony **aplikacje i funkcje** lub **programy i funkcje** w **Panelu sterowania** , aby naprawić lub ponownie zainstalować program.
> - Sprawdź, **Windows Update** w **Panelu sterowania** aktualizacje oprogramowania.
> - Sprawdź dostępność zaktualizowanej wersji aplikacji. Jeśli problem będzie nadal występował, skontaktuj się z dostawcą aplikacji.

**Informacje dla programistów**

Ten błąd występuje, ponieważ aplikacja nosi funkcję konsoli, ale system operacyjny nie przyznał dostępu do konsoli. Poza trybem debugowania funkcje konsoli są zwykle niedozwolone w aplikacjach Microsoft Store. Jeśli aplikacja wymaga uprawnień administratora, upewnij się, że jest zainstalowana w celu domyślnego uruchomienia jako administrator.
