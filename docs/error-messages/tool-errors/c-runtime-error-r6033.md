---
description: Dowiedz się więcej o błędzie środowiska uruchomieniowego C R6033
title: Błąd czasu wykonania języka C R6033
ms.date: 11/04/2016
f1_keywords:
- R6033
helpviewer_keywords:
- R6033
ms.assetid: f9cffdc9-81bd-4a64-a698-02762cbd82c9
ms.openlocfilehash: 377f872957af4ab4a844e7d93345a612a16c0490
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97206607"
---
# <a name="c-runtime-error-r6033"></a>Błąd czasu wykonania języka C R6033

Próba użycia kodu MSIL z tego zestawu podczas inicjowania kodu natywnego. Wskazuje to na usterkę w aplikacji. Najprawdopodobniej wynik wywoływania funkcji MSIL (/CLR) z natywnego konstruktora lub z DllMain.

> [!NOTE]
> Jeśli ten komunikat o błędzie wystąpi podczas uruchamiania aplikacji, aplikacja została zamknięta, ponieważ ma problem wewnętrzny. Ten błąd może być spowodowany przez usterkę w aplikacji lub przez usterkę w dodatku lub rozszerzeniu, którego używa.
>
> Możesz wypróbować następujące kroki, aby naprawić ten błąd:
>
> - Użyj strony **aplikacje i funkcje** lub **programy i funkcje** w **Panelu sterowania** , aby naprawić lub ponownie zainstalować program.
> - Użyj strony **aplikacje i funkcje** lub **programy i funkcje** w **Panelu sterowania** , aby usunąć, naprawić lub ponownie zainstalować wszystkie rozszerzenia lub dodatki.
> - Sprawdź, **Windows Update** w **Panelu sterowania** aktualizacje oprogramowania.
> - Sprawdź dostępność zaktualizowanej wersji aplikacji. Jeśli problem będzie nadal występował, skontaktuj się z dostawcą aplikacji.

**Informacje dla programistów**

Ta Diagnostyka wskazuje, że instrukcje MSIL zostały wykonane podczas blokady modułu ładującego. Taka sytuacja może wystąpić, jeśli skompilowano natywne C++ przy użyciu flagi/CLR. W modułach, które zawierają kod zarządzany, należy używać tylko flagi/CLR. Aby uzyskać więcej informacji, zobacz [Inicjowanie zestawów mieszanych](../../dotnet/initialization-of-mixed-assemblies.md).
