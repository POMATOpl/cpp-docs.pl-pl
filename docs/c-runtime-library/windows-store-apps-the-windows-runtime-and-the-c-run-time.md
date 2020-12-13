---
description: 'Dowiedz się więcej na temat: platformy UWP Apps, środowisko wykonawcze systemu Windows i C Run-Time'
title: PLATFORMY UWP aplikacje, środowisko wykonawcze systemu Windows i C Run-Time
ms.date: 02/02/2019
ms.assetid: 356d6d8d-76ee-4181-9ad0-6f24b2fede38
ms.openlocfilehash: cfbbdbde19b882fb51b8fd8782b20e4205bdb00b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97136750"
---
# <a name="uwp-apps-the-windows-runtime-and-the-c-run-time"></a>PLATFORMY UWP aplikacje, środowisko wykonawcze systemu Windows i C Run-Time

Aplikacje platforma uniwersalna systemu Windows (platformy UWP) są programami uruchomionymi w środowisko wykonawcze systemu Windows, które są wykonywane w systemie Windows 8. Środowisko wykonawcze systemu Windows to godna zaufania środowisko kontrolujące funkcje, zmienne i zasoby, które są dostępne dla aplikacji platformy UWP. Jednak przez zaprojektowanie ograniczeń środowisko wykonawcze systemu Windows uniemożliwia korzystanie z większości funkcji języka C Run-Time Library (CRT) w aplikacjach platformy UWP.

Środowisko wykonawcze systemu Windows nie obsługuje następujących funkcji CRT:

- Większość funkcji CRT, które są związane z nieobsługiwanymi funkcjami.

   Na przykład aplikacja platformy UWP nie może utworzyć procesu przy użyciu rodzin **exec** i **tarł** procedur.

   Gdy funkcja CRT nie jest obsługiwana w aplikacji platformy UWP, ten fakt jest zanotowany w jego artykule referencyjnym.

- Większość funkcji znaków wielobajtowych i ciągów.

   Jednak tekst Unicode i ANSI są obsługiwane.

- Zmienne środowiskowe.

- Koncepcja bieżącego katalogu roboczego.

- PLATFORMY UWP aplikacje i biblioteki DLL, które są statycznie połączone z CRT i zbudowane przy użyciu opcji [/MT](../build/reference/md-mt-ld-use-run-time-library.md) lub `/MTd` kompilatora.

   Oznacza to, że aplikacja, która używa wielowątkowej, statycznej wersji CRT.

- Aplikacja, która jest skompilowana przy użyciu opcji kompilatora [/MDD](../build/reference/md-mt-ld-use-run-time-library.md) .

   Oznacza to, że jest to wersja typu Debug, wielowątkowej i DLL dla programu CRT. Taka aplikacja nie jest obsługiwana na środowisko wykonawcze systemu Windows.

Aby zapoznać się z pełną listą funkcji CRT, które nie są dostępne w aplikacji platformy UWP i sugestie dotyczące funkcji alternatywnych, zobacz [funkcje CRT nieobsługiwane w aplikacjach platforma uniwersalna systemu Windows](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="see-also"></a>Zobacz też

[Zgodność](../c-runtime-library/compatibility.md)<br/>
[środowisko wykonawcze systemu Windows Nieobsługiwane funkcje CRT](../c-runtime-library/windows-runtime-unsupported-crt-functions.md)<br/>
[Procedury środowiska uruchomieniowego języka Universal C według kategorii](../c-runtime-library/run-time-routines-by-category.md)<br/>
[Tworzenie aplikacji konsolowej platforma uniwersalna systemu Windows](/windows/uwp/launch-resume/console-uwp)
