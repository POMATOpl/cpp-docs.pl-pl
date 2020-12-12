---
description: Dowiedz się więcej o błędzie środowiska uruchomieniowego C R6031
title: Błąd czasu wykonania języka C R6031
ms.date: 11/04/2016
f1_keywords:
- R6031
helpviewer_keywords:
- R6031
ms.assetid: 805d4cd1-cb2f-43fe-87e6-e7bd5b7329c5
ms.openlocfilehash: cd3a9e62e4209df5aa232ac9df6b69ce8a63d10a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97206620"
---
# <a name="c-runtime-error-r6031"></a>Błąd czasu wykonania języka C R6031

Podjęto próbę zainicjowania CRT więcej niż raz. Wskazuje to na usterkę w aplikacji.

> [!NOTE]
> Jeśli ten komunikat o błędzie wystąpi podczas uruchamiania aplikacji, aplikacja została zamknięta, ponieważ ma problem wewnętrzny. Może to być spowodowane usterką w aplikacji lub przez usterkę w dodatku lub rozszerzeniu, którego używa aplikacja.
>
> Możesz wypróbować następujące kroki, aby naprawić ten błąd:
>
> - Użyj strony **aplikacje i funkcje** lub **programy i funkcje** w **Panelu sterowania** , aby naprawić lub ponownie zainstalować program.
> - Użyj strony **aplikacje i funkcje** lub **programy i funkcje** w **Panelu sterowania** , aby usunąć, naprawić lub zainstalować ponownie wszystkie programy dodatków lub rozszerzenia używane przez aplikację.
> - Sprawdź, **Windows Update** w **Panelu sterowania** aktualizacje oprogramowania.
> - Sprawdź dostępność zaktualizowanej wersji aplikacji. Jeśli problem będzie nadal występował, skontaktuj się z dostawcą aplikacji.

**Informacje dla programistów**

Ta Diagnostyka wskazuje, że instrukcje MSIL zostały wykonane podczas blokady modułu ładującego. Aby uzyskać więcej informacji, zobacz [Inicjowanie zestawów mieszanych](../../dotnet/initialization-of-mixed-assemblies.md).
