---
description: Dowiedz się więcej o:/BASE (adres podstawowy)
title: /BASE (Adres podstawowy)
ms.date: 09/05/2018
f1_keywords:
- /base
- VC.Project.VCLinkerTool.BaseAddress
helpviewer_keywords:
- base addresses [C++]
- programs [C++], preventing relocation
- semicolon [C++], specifier
- -BASE linker option
- key address size
- environment variables [C++], LIB
- programs [C++], base address
- LIB environment variable
- BASE linker option
- DLLs [C++], linking
- /BASE linker option
- '@ symbol for base address'
- executable files [C++], base address
- at sign symbol for base address
ms.assetid: 00b9f6fe-0bd2-4772-a69c-7365eb199069
ms.openlocfilehash: 269911c7d9fce47be1b9755ddebf38170ea4e81c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182778"
---
# <a name="base-base-address"></a>/BASE (Adres podstawowy)

Określa adres podstawowy programu.

## <a name="syntax"></a>Składnia

> **/Base:**{*Address*[**,**<em>size</em>] | **\@** <em>Nazwa pliku</em>**,**<em>klucz</em>}

## <a name="remarks"></a>Uwagi

> [!NOTE]
> Ze względów bezpieczeństwa firma Microsoft zaleca korzystanie z opcji [/DYNAMICBASE](dynamicbase-use-address-space-layout-randomization.md) zamiast określania adresów bazowych dla plików wykonywalnych. Spowoduje to wygenerowanie obrazu wykonywalnego, który można losowo zmienić w bazie czasu ładowania przy użyciu funkcji losowego układu przestrzeni adresowej (ASLR) systemu Windows. Opcja/DYNAMICBASE jest domyślnie włączona.

Opcja/BASE ustawia adres podstawowy dla programu, zastępując domyślną lokalizację pliku exe lub DLL. Domyślny adres podstawowy pliku. exe to 0x400000 dla obrazów 32-bitowych lub 0x140000000 dla obrazów 64-bitowych. Dla biblioteki DLL domyślny adres podstawowy to 0x10000000 dla obrazów 32-bitowych lub 0x180000000 dla obrazów 64-bitowych. W systemach operacyjnych, które nie obsługują losowego generowania układu przestrzeni adresowej (ASLR) lub jeśli nie ustawiono opcji/DYNAMICBASE: NO, system operacyjny najpierw próbuje załadować program w określonym lub domyślnym adresie podstawowym. Jeśli w tym miejscu nie jest dostępna wystarczająca ilość miejsca, system zlokalizuje program. Aby zapobiec relokacji, użyj opcji [/FIXED](fixed-fixed-base-address.md) .

Konsolidator wystawia błąd, jeśli *adres* nie jest wielokrotnością 64 KB. Opcjonalnie można określić rozmiar programu; Konsolidator emituje ostrzeżenie, jeśli program nie mieści się w określonym rozmiarze.

W wierszu polecenia inny sposób określania adresu podstawowego jest przy użyciu podstawowego pliku odpowiedzi na adres. Podstawowy plik odpowiedzi adresowej to plik tekstowy, który zawiera adresy podstawowe i opcjonalne rozmiary wszystkich bibliotek DLL, które będą używane przez program, i unikatowy klucz tekstu dla każdego adresu podstawowego. Aby określić adres podstawowy przy użyciu pliku odpowiedzi, należy użyć znaku ( **\@** ), po którym następuje nazwa pliku odpowiedzi, a następnie przecinek , a następnie wartość *klucza* dla adresu podstawowego do użycia w pliku. Konsolidator szuka *nazwy pliku* w określonej ścieżce lub nie określono ścieżki w katalogach określonych w zmiennej środowiskowej LIB. Każdy wiersz w *pliku filename* reprezentuje jedną bibliotekę DLL i ma następującą składnię:

>  *adres* klucza [*size*] **;** *komentarz*

*Klucz* jest ciągiem znaków alfanumerycznych i nie jest rozróżniana wielkość liter. Zwykle jest to nazwa biblioteki DLL, ale nie musi ona być. Po *kluczu* następuje *adres* podstawowy w notacji języka C, szesnastkowa lub dziesiętna oraz opcjonalny maksymalny *rozmiar*. Wszystkie trzy argumenty są rozdzielone spacjami lub tabulatorami. Konsolidator emituje ostrzeżenie, jeśli określony *rozmiar* jest mniejszy niż wirtualna przestrzeń adresowa wymagana przez program. *Komentarz* jest określany za pomocą średnika (**;**) i może być w tym samym lub osobnym wierszu. Konsolidator ignoruje cały tekst od średnika do końca wiersza. Ten przykład przedstawia część tego pliku:

```
main   0x00010000    0x08000000    ; for PROJECT.exe
one    0x28000000    0x00100000    ; for DLLONE.DLL
two    0x28100000    0x00300000    ; for DLLTWO.DLL
```

Jeśli plik, który zawiera te linie, jest nazywany DLLS.txt, następujące przykładowe polecenie stosuje te informacje:

```
link dlltwo.obj /dll /base:@dlls.txt,two
```

Innym sposobem ustawienia adresu podstawowego jest użycie argumentu *podstawowego* w instrukcji [name](name-c-cpp.md) lub [Library](library.md) . Opcje/BASE i [/dll](dll-build-a-dll.md) razem są równoważne instrukcji **Library** .

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz stronę właściwości **Konfiguracja**  >  **konsolidator**  >  **Zaawansowane** właściwości.

1. Zmodyfikuj właściwość **adres podstawowy** .

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.BaseAddress%2A>.

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
