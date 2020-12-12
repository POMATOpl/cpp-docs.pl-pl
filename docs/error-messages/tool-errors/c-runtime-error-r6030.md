---
description: Dowiedz się więcej o błędzie środowiska uruchomieniowego C R6030
title: Błąd czasu wykonania języka C R6030
ms.date: 11/04/2016
f1_keywords:
- R6030
helpviewer_keywords:
- R6030
ms.assetid: 0238a6c3-a033-4046-8adc-f8f99d961153
ms.openlocfilehash: e3c945df043f8702d75db56c28b50b8b00f4df8f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297216"
---
# <a name="c-runtime-error-r6030"></a>Błąd czasu wykonania języka C R6030

Nie zainicjowano CRT

> [!NOTE]
> Jeśli ten komunikat o błędzie wystąpi podczas uruchamiania aplikacji, aplikacja została zamknięta, ponieważ ma problem wewnętrzny. Ten problem jest najczęściej spowodowany przez niektóre programy zabezpieczające oprogramowania lub rzadko przez usterkę w programie.
>
> Możesz wypróbować następujące kroki, aby naprawić ten błąd:
>
> - Oprogramowanie zabezpieczające może zawierać konkretne instrukcje dotyczące ograniczenia tego problemu. Sprawdź witrynę sieci Web dostawcy oprogramowania zabezpieczającego, aby uzyskać szczegółowe informacje. Alternatywnie Sprawdź dostępność zaktualizowanych wersji oprogramowania zabezpieczającego lub wypróbuj inne oprogramowanie zabezpieczające.
> - Użyj strony **aplikacje i funkcje** lub **programy i funkcje** w **Panelu sterowania** , aby naprawić lub ponownie zainstalować program.
> - Sprawdź, **Windows Update** w **Panelu sterowania** aktualizacje oprogramowania.
> - Sprawdź dostępność zaktualizowanej wersji aplikacji. Jeśli problem będzie nadal występował, skontaktuj się z dostawcą aplikacji.

**Informacje dla programistów**

Ten błąd występuje, jeśli używasz środowiska uruchomieniowego języka C (CRT), ale kod uruchomienia CRT nie został wykonany. Ten błąd jest możliwy, jeśli przełącznik konsolidatora [/entry](../../build/reference/entry-entry-point-symbol.md) jest używany do przesłonięcia domyślnego adresu początkowego, zazwyczaj **mainCRTStartup**, **WmainCRTStartup** dla konsoli exe, **WinMainCRTStartup** lub **wWinMainCRTStartup** dla programu Windows exe lub **_DllMainCRTStartup** dla biblioteki DLL. Jeśli jedna z powyższych funkcji nie zostanie wywołana podczas uruchamiania, środowisko uruchomieniowe języka C nie zostanie zainicjowane. Te funkcje uruchomieniowe są zwykle wywoływane domyślnie podczas łączenia z biblioteką środowiska uruchomieniowego języka C i używania **zwykłych punktów** wejścia, **wmain**, **WinMain** lub **DllMain** .

Ten błąd jest również możliwy, gdy inny program używa technik iniekcji kodu w celu zalewkowania niektórych wywołań biblioteki DLL. W przypadku niektórych niepożądanych programów zabezpieczających ta technika jest używana. W wersjach Visual C++ starszych niż program Visual Studio 2015 możliwe jest użycie statycznie połączonej biblioteki CRT w celu rozwiązania problemu, ale nie jest to zalecane w przypadku aktualizacji zabezpieczeń i aplikacji. Poprawienie tego problemu może wymagać wykonania akcji przez użytkownika końcowego.
