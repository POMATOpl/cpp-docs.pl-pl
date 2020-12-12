---
description: Dowiedz się więcej na temat:/GL (Optymalizacja całego programu)
title: /GL (Optymalizacja całego programu)
ms.date: 11/04/2016
f1_keywords:
- /gl
helpviewer_keywords:
- /GL compiler option [C++]
- whole program optimizations and C++ compiler
- -GL compiler option [C++]
- GL compiler option [C++]
ms.assetid: 09d51e2d-9728-4bd0-b5dc-3b8284aca1d1
ms.openlocfilehash: ad42eaeeacf897686831c9b415aa62026b5644f1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200198"
---
# <a name="gl-whole-program-optimization"></a>/GL (Optymalizacja całego programu)

Włącza optymalizację całego programu.

## <a name="syntax"></a>Składnia

```
/GL[-]
```

## <a name="remarks"></a>Uwagi

Optymalizacja całego programu umożliwia kompilatorowi wykonywanie optymalizacji z informacjami na wszystkich modułach w programie. Bez optymalizacji całego programu, optymalizacje są wykonywane dla każdego modułu (jednostka kompilacji).

Optymalizacja całego programu jest domyślnie wyłączona i należy ją jawnie włączyć. Można jednak jawnie wyłączyć go za pomocą **/GL-**.

Wraz z informacjami na temat wszystkich modułów kompilator może:

- Optymalizuj użycie rejestrów w granicach funkcji.

- Wykonaj lepsze zadanie śledzenia modyfikacji danych globalnych, co pozwala na zmniejszenie liczby obciążeń i magazynów.

- Wykonaj lepsze zadanie śledzenia możliwego zestawu elementów modyfikowanych przez odwołanie wskaźnika, zmniejszając liczbę obciążeń i magazynów.

- Wbudowana funkcja w module, nawet gdy funkcja jest zdefiniowana w innym module.

pliki. obj tworzone za pomocą **/GL** nie będą dostępne dla takich narzędzi konsolidatora, jak [polecenia EDITBIN](editbin-reference.md) i [polecenia DUMPBIN](dumpbin-reference.md).

Jeśli kompilujesz program z **/GL** i [/c](c-compile-without-linking.md), należy użyć opcji konsolidatora/LTCG, aby utworzyć plik wyjściowy.

Nie można używać [/Zi](z7-zi-zi-debug-information-format.md) z **/GL**

W kolejnych wersjach Visual C++ nie można odczytać formatu plików utworzonych za pomocą **/GL** w bieżącej wersji. Nie należy dostarczać pliku lib składającego się z plików. obj, które zostały utworzone za pomocą **/GL** , chyba że chcemy przesłać kopie pliku lib dla wszystkich wersji Visual C++, których użytkownicy będą mogli używać, teraz i w przyszłości.

pliki. obj tworzone za pomocą **/GL** i prekompilowanych plików nagłówkowych nie powinny być używane do kompilowania pliku. lib, chyba że plik. lib zostanie połączony na tym samym komputerze, na którym wyprodukowała plik **/GL** . obj. Informacje z prekompilowanego pliku nagłówkowego pliku. obj będą wymagały czasu połączenia.

Aby uzyskać więcej informacji na temat optymalizacji dostępnych wraz z ograniczeniami w zakresie optymalizacji całego programu, zobacz [/LTCG](ltcg-link-time-code-generation.md).  **/GL** także udostępnia optymalizację z przewodnikiem. zobacz/LTCG.  Podczas kompilowania dla optymalizacji profilowanej i jeśli chcesz, aby funkcja była uporządkowana z optymalizacji profilowanej, należy skompilować z [/Gy](gy-enable-function-level-linking.md) lub opcją kompilatora, która oznacza/Gy.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Zobacz [/LTCG (generowanie kodu w czasie konsolidacji)](ltcg-link-time-code-generation.md) , aby uzyskać informacje na temat sposobu określania **/GL** w środowisku deweloperskim.

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

1. Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WholeProgramOptimization%2A>.

## <a name="see-also"></a>Zobacz też

[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)
