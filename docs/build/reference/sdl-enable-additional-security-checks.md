---
title: /sdl (Włącz dodatkowe kontrole zabezpieczeń)
description: Opcja/sdl kompilatora języka Microsoft C/C++ włącza zalecane testy i ostrzeżenia dotyczące cyklu projektowania zabezpieczeń (SDL).
ms.date: 10/02/2020
f1_keywords:
- VC.Project.VCCLCompilerTool.SDLCheck
ms.assetid: 3dcf86a0-3169-4240-9f29-e04a9f535826
ms.openlocfilehash: 8d679bb3fc48e52bcc42a85d507618c38fd3dcdc
ms.sourcegitcommit: 30792632548d1c71894f9fecbe2f554294b86020
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/06/2020
ms.locfileid: "91765197"
---
# <a name="sdl-enable-additional-security-checks"></a>/sdl (Włącz dodatkowe kontrole zabezpieczeń)

Włącza zalecane testy cyklu projektowania zabezpieczeń (SDL). Sprawdzają one zmiany w błędach związanych z zabezpieczeniami i ustawiają dodatkowe funkcje bezpiecznego generowania kodu.

## <a name="syntax"></a>Składnia

> **`/sdl`**[**`-`**]

## <a name="remarks"></a>Uwagi

**/SDL** włącza nadzbiór kontroli zabezpieczeń linii bazowej dostarczonych przez [`/GS`](gs-buffer-security-check.md) i zastąpień **`/GS-`** . Domyślnie program **`/sdl`** jest wyłączony. **`/sdl-`** wyłącza dodatkowe sprawdzanie zabezpieczeń.

### <a name="compile-time-checks"></a>Sprawdzanie czasu kompilacji

**`/sdl`** włącza te ostrzeżenia jako błędy:

| Ostrzeżenie włączone przez/SDL | Równoważny przełącznik wiersza polecenia | Opis |
|--|--|--|
| [C4146](../../error-messages/compiler-warnings/compiler-warning-level-2-c4146.md) | /we4146 | Jednoargumentowy operator minus został zastosowany do typu bez znaku, co spowoduje powstanie niepodpisanego wyniku. |
| [C4308](../../error-messages/compiler-warnings/compiler-warning-level-2-c4308.md) | /we4308 | Ujemna stała całkowita przekonwertowana na typ bez znaku, co może oznaczać, że jest to niemożliwy wynik. |
| [C4532](../../error-messages/compiler-warnings/compiler-warning-level-1-c4532.md) | /we4532 | Użycie `continue` `break` `goto` słowa kluczowego or w `__finally` / `finally` bloku ma niezdefiniowane zachowanie podczas nieprawidłowego kończenia. |
| [C4533](../../error-messages/compiler-warnings/compiler-warning-level-1-c4533.md) | /we4533 | Kod inicjujący zmienną nie zostanie wykonany. |
| [C4700](../../error-messages/compiler-warnings/compiler-warning-level-1-and-level-4-c4700.md) | /we4700 | Użycie niezainicjowanej zmiennej lokalnej. |
| [C4703](../../error-messages/compiler-warnings/compiler-warning-level-4-c4703.md) | /we4703 | Użycie potencjalnie niezainicjowanej zmiennej wskaźnika lokalnego. |
| [C4789](../../error-messages/compiler-warnings/compiler-warning-level-1-c4789.md) | /we4789 | Przepełnienie buforu w przypadku korzystania z określonych funkcji języka C (CRT). |
| [C4995](../../error-messages/compiler-warnings/compiler-warning-level-3-c4995.md) | /we4995 | Użycie funkcji oznaczonej za pomocą dyrektywy pragma [`deprecated`](../../preprocessor/deprecated-c-cpp.md) . |
| [C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) | /we4996 | Użycie funkcji oznaczonej jako [`deprecated`](../../cpp/deprecated-cpp.md) . |

### <a name="runtime-checks"></a>Sprawdzenia środowiska uruchomieniowego

Gdy **`/sdl`** jest włączona, kompilator generuje kod, który wykonuje te testy w czasie wykonywania:

- Włącza tryb ścisły **`/GS`** wykrywania przepełnienia buforu w czasie wykonywania, który jest równoznaczny z kompilowaniem za pomocą `#pragma strict_gs_check(push, on)` .

- Wykonuje ograniczoną oczyszczanie wskaźnika. W wyrażeniach, które nie obejmują dereferencji i typów, które nie mają destruktora zdefiniowanego przez użytkownika, odwołania do wskaźnika są ustawiane jako nieprawidłowy adres po wywołaniu **`delete`** . Ta oczyszczanie pomaga zapobiec ponownemu używaniu nieodświeżonych odwołań do wskaźników.

- Inicjuje wskaźniki elementu członkowskiego klasy. Automatycznie inicjuje składowe klasy typu wskaźnika do **`nullptr`** tworzenia wystąpienia obiektu (przed uruchomieniem konstruktora). Pomaga zapobiegać użyciu niezainicjowanych wskaźników, które nie są jawnie inicjowane przez Konstruktor. Inicjalizacja wskaźnika elementu członkowskiego wygenerowanego przez kompilator jest wywoływana tak długo, jak:

  - Obiekt nie jest przydzielony przy użyciu niestandardowego (zdefiniowanego przez użytkownika) `operator new`

  - Obiekt nie jest przydzielony jako część tablicy (na przykład `new A[x]` )

  - Klasa nie jest zarządzana ani zaimportowana

  - Klasa ma zdefiniowany przez użytkownika Konstruktor domyślny.

  Aby można było zainicjować za pomocą funkcji inicjowania klasy generowanej przez kompilator, element członkowski musi być wskaźnikiem, a nie właściwością ani stałą.

Aby uzyskać więcej informacji, zobacz [ostrzeżenia,/SDL i ulepszanie wykrywania zmiennej niezainicjowanej](https://www.microsoft.com/security/blog/2012/06/06/warnings-sdl-and-improving-uninitialized-variable-detection/).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz **Configuration Properties**  >  stronę właściwości ogólne**C/C++** właściwości konfiguracji  >  **General** .

1. Ustaw właściwość **SDL checks** przy użyciu kontrolki rozwijanej właściwości. Wybierz **przycisk OK** lub **Zastosuj** , aby zapisać zmiany.

## <a name="see-also"></a>Zobacz też

[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia wiersza polecenia kompilatora MSVC](compiler-command-line-syntax.md)
