---
description: Dowiedz się więcej o:/QIfist (Pomijaj _ftol)
title: /QIfist (Pomijanie _ftol)
ms.date: 11/04/2016
f1_keywords:
- /qifist
helpviewer_keywords:
- QIfist compiler option [C++]
- -QIfist compiler option [C++]
- /QIfist compiler option [C++]
ms.assetid: 1afd32a5-f658-4b66-85f4-e0ce4cb955bd
ms.openlocfilehash: 79e9242d66b532f558307d05b222b2fd8cfd43ab
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225651"
---
# <a name="qifist-suppress-_ftol"></a>/QIfist (Pomijanie _ftol)

Przestarzałe. Pomija wywołanie funkcji pomocnika, `_ftol` gdy wymagana jest konwersja z typu zmiennoprzecinkowego na typ całkowity.

## <a name="syntax"></a>Składnia

```
/QIfist
```

## <a name="remarks"></a>Uwagi

> [!NOTE]
> **/QIfist** jest dostępna tylko w kompilatorze przeznaczonym dla architektury x86; Ta opcja kompilatora nie jest dostępna w kompilatorach przeznaczonych dla architektury x64 orARM.

Oprócz konwersji z typu zmiennoprzecinkowego na typ całkowity, `_ftol` Funkcja zapewnia, że tryb zaokrąglania jednostki zmiennoprzecinkowej (FPU) ma wartość zero (obcinanie), ustawiając bity 10 i 11 formantu. Gwarantuje to, że konwersja z typu zmiennoprzecinkowego na typ całkowity występuje zgodnie z opisem w standardzie ANSI C (część ułamkowa liczby jest odrzucana). W przypadku korzystania z **/QIfist** ta gwarancja nie jest już stosowana. Tryb zaokrąglania będzie jednym z czterech, zgodnie z opisem w podręczniku odniesienia firmy Intel:

- Zaokrąglij do najbliższej (parzystej liczby)

- Zaokrąglij w kierunku nieskończoności ujemnej

- Zaokrąglij do nieskończoności dodatniej

- Zaokrąglij w kierunku zera

Można użyć funkcji [_control87, _controlfp \_ _control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md) C Run-Time, aby zmodyfikować zachowanie zaokrągleń FPU. Domyślny tryb zaokrąglania FPU jest "zaokrąglony do najbliższej". Korzystanie z **/QIfist** może zwiększyć wydajność aplikacji, ale nie bez ryzyka. Należy dokładnie przetestować fragmenty kodu, które są wrażliwe na tryby zaokrąglania przed użyciem kodu skompilowanego za pomocą **/QIfist** w środowiskach produkcyjnych.

[/arch (x86)](arch-x86.md) i **/QIfist** nie mogą być używane w tym samym jednostka kompilacji.

> [!NOTE]
> **/QIfist** domyślnie nie działa, ponieważ bity zaokrąglania wpływają na zmiennoprzecinkowe zaokrąglenie zmiennoprzecinkowe (które występuje po każdym obliczeniu), więc po ustawieniu flag dla stylu C (w kierunku zera) obliczenia zmiennoprzecinkowe mogą być różne. Nie należy używać **/QIfist** , jeśli kod zależy od oczekiwanego zachowania obcinanie części ułamkowej liczby zmiennoprzecinkowej. Jeśli nie masz pewności, nie używaj **/QIfist**.

Opcja **/QIfist** jest przestarzała począwszy od programu Visual Studio 2005. Kompilator wprowadził znaczące ulepszenia szybkości przetwarzania zmiennoprzecinkowego na int. Aby zapoznać się z listą przestarzałych opcji kompilatora, zobacz Opcje kompilatora **przestarzałe i usunięte** w [opcjach kompilatora wymienionych według kategorii](compiler-options-listed-by-category.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Kliknij folder **C/C++** .

1. Kliknij stronę właściwości **wiersza polecenia** .

1. Wpisz opcję kompilatora w polu **dodatkowe opcje** .

### <a name="to-set-this-compiler-option-programmatically"></a>Aby programowo ustawić tę opcję kompilatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Zobacz też

[/Q opcje (operacje na niskim poziomie)](q-options-low-level-operations.md)<br/>
[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)
