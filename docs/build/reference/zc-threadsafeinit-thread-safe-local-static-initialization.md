---
description: 'Dowiedz się więcej na temat:/Zc: threadSafeInit (bezpieczne statyczne inicjowanie w wątkach)'
title: '/Zc: threadSafeInit (bezpieczne statyczne inicjowanie lokalnego wątku)'
ms.date: 03/14/2018
f1_keywords:
- threadSafeInit
- /Zc:threadSafeInit
helpviewer_keywords:
- -Zc compiler options (C++)
- threadSafeInit
- Thread-safe Local Static Initialization
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: a0fc4b34-2cf0-45a7-a642-b8afc4ca19f2
ms.openlocfilehash: ac14e7979d2adab0b21229f426e00a489c14f38f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97271216"
---
# <a name="zcthreadsafeinit-thread-safe-local-static-initialization"></a>/Zc: threadSafeInit (bezpieczne statyczne inicjowanie lokalnego wątku)

Opcja kompilatora **/Zc: threadSafeInit** instruuje kompilator, aby zainicjował statyczne zmienne lokalne (zakres funkcji) w sposób bezpieczny dla wątków, eliminując konieczność ręcznej synchronizacji. Tylko Inicjalizacja jest bezpieczna wątkowo. Używanie i modyfikowanie statycznych zmiennych lokalnych w wielu wątkach musi nadal być synchronizowane ręcznie. Ta opcja jest dostępna od programu Visual Studio 2015. Domyślnie program Visual Studio włącza tę opcję.

## <a name="syntax"></a>Składnia

> **/Zc: threadSafeInit**[ **-** ]

## <a name="remarks"></a>Uwagi

W standardzie C++ 11, zmienne zakresu bloku ze statycznym lub okresem przechowywania wątków muszą być inicjowane od zera przed innymi inicjalizacjami. Inicjalizacja występuje, gdy kontrolka jest najpierw przekazywana przez deklarację zmiennej. Jeśli wyjątek jest zgłaszany podczas inicjowania, zmienna jest uważana za niezainicjowaną, a inicjacja zostanie ponowiona przy następnym przejęciu kontroli przez deklarację. Jeśli kontrolka przejdzie jednocześnie do deklaracji z inicjacją, bloki wykonywania współbieżne podczas inicjowania są kończone. Zachowanie jest niezdefiniowane, jeśli kontrola przejdzie ponownie do deklaracji cyklicznie podczas inicjowania. Domyślnie program Visual Studio rozpoczynający się w programie Visual Studio 2015 implementuje to standardowe zachowanie. Takie zachowanie może być jawnie określone przez ustawienie opcji kompilatora **/Zc: threadSafeInit** .

Opcja kompilatora **/Zc: threadSafeInit** jest domyślnie włączona. Opcja [/permissive-](permissive-standards-conformance.md) nie ma wpływu na **/Zc: threadSafeInit**.

Bezpieczne inicjowanie wątków statycznych zmiennych lokalnych opiera się na kodzie zaimplementowanym w bibliotece uniwersalnej uruchomieniowej C (UCRT). Aby uniknąć powstawania zależności od UCRT lub zachowania niebezpiecznego zainicjowania wątku w wersjach programu Visual Studio starszych niż Visual Studio 2015, użyj opcji **/Zc: threadSafeInit-** . Jeśli wiesz, że bezpieczeństwo wątków nie jest wymagane, Użyj tej opcji w celu wygenerowania nieco mniejszego, szybszego kodu wokół statycznych deklaracji lokalnych.

Bezpieczne dla wątków statyczne zmienne lokalne używają lokalnego magazynu wątków (TLS) w celu zapewnienia wydajnego wykonania, gdy statyczny został już zainicjowany. Implementacja tej funkcji zależy od funkcji obsługi systemu operacyjnego Windows w systemie Windows Vista i nowszych systemach operacyjnych. W systemach Windows XP, Windows Server 2003 i starszych systemach operacyjnych nie jest to obsługiwane, więc nie uzyskują one korzyści z wydajności. W tych systemach operacyjnych obowiązuje również dolny limit liczby sekcji protokołu TLS, które mogą zostać załadowane. Przekroczenie limitu sekcji TLS może spowodować awarię. Jeśli jest to problem w kodzie, szczególnie w kodzie, który musi działać w starszych systemach operacyjnych, użyj **/Zc: threadSafeInit-** , aby wyłączyć kod inicjalizacji bezpieczny wątkowo.

Aby uzyskać więcej informacji na temat problemów ze zgodnością w Visual C++, zobacz [niestandardowe zachowanie](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Z menu rozwijanego **konfiguracje** wybierz pozycję **wszystkie konfiguracje**.

1. Wybierz   >  stronę właściwości konfiguracja wiersza polecenia **C/C++**  >   .

1. Zmodyfikuj właściwość **Opcje dodatkowe** , aby uwzględnić **/Zc: threadSafeInit** lub **/Zc: threadSafeInit-** , a następnie wybierz **przycisk OK**.

## <a name="see-also"></a>Zobacz też

[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)<br/>
[/Zc (Zgodność)](zc-conformance.md)<br/>
