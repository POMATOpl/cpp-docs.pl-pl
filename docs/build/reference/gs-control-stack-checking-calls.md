---
description: Dowiedz się więcej o:/GS (Kontroluj wywołania sprawdzania stosu)
title: /Gs (Kontroluj wywołania sprawdzania stosu)
ms.date: 10/25/2018
f1_keywords:
- /GS
helpviewer_keywords:
- disabling stack probes
- GS compiler option [C++]
- /GS compiler option [C++]
- stack, stack probes
- stack probes
- -GS compiler option [C++]
- stack checking calls
ms.assetid: 40daed7c-f942-4085-b872-01e12b37729e
ms.openlocfilehash: 128a5ad4dbcba15dfc5b76313b8576ce1448ec68
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200168"
---
# <a name="gs-control-stack-checking-calls"></a>/Gs (Kontroluj wywołania sprawdzania stosu)

Kontroluje próg dla sond stosu.

## <a name="syntax"></a>Składnia

> **/GS**[*rozmiar*]

## <a name="arguments"></a>Argumenty

*zmienia*<br/>
Obowiązkowe Liczba bajtów, które mogą zajmować zmienne lokalne przed zainicjowaniem sondy stosu. Nie jest dozwolone żadne miejsce między **/GS** i *rozmiarem*.

## <a name="remarks"></a>Uwagi

*Sonda stosu* jest sekwencją kodu, który kompilator wstawia na początku wywołania funkcji. Po zainicjowaniu sondy stosu dociera niegroźnie do pamięci przez ilość miejsca wymaganą do przechowywania zmiennych lokalnych funkcji. Powoduje to, że system operacyjny będzie w sposób przezroczysty stroną w dodatkowej pamięci stosu, jeśli jest to wymagane, zanim pozostała część funkcji zostanie uruchomiona.

Domyślnie kompilator generuje kod inicjujący sondę stosu, gdy funkcja wymaga więcej niż jednej strony przestrzeni stosu. Jest to odpowiednik opcji kompilatora **/Gs4096** dla platform x86, x64, ARM i arm64. Ta wartość umożliwia aplikacji i menedżerowi pamięci systemu Windows zwiększenie ilości pamięci przekazanej do stosu programu dynamicznie w czasie wykonywania.

> [!NOTE]
> Wartość domyślna **/Gs4096** umożliwia sekwencyjne programowanie aplikacji dla systemu Windows w czasie wykonywania. Zaleca się, aby nie zmieniać wartości domyślnej, chyba że wiadomo, dlaczego trzeba ją zmienić.

Niektóre programy — na przykład sterowniki urządzeń wirtualnych — nie wymagają tego domyślnego mechanizmu wzrostu stosu. W takich przypadkach sondy stosu nie są konieczne i można zatrzymać generowanie ich przez kompilator przez ustawienie *rozmiaru* do wartości, która jest większa niż każda funkcja będzie wymagała lokalnego magazynu zmiennych.

**/GS0** inicjuje sondy stosu dla każdego wywołania funkcji, które wymaga magazynu dla zmiennych lokalnych. Może to mieć negatywny wpływ na wydajność.

W przypadku obiektów docelowych x64, jeśli opcja **/GS** jest określona bez argumentu *size* , jest taka sama jak **/GS0**. Jeśli argument *size* ma wartość od 1 do 9, D9014 ostrzegawczy jest emitowany, a efekt jest taki sam jak określenie **/GS0**.

Dla elementów docelowych x86, ARM i ARM64, opcja **/GS** bez argumentu *size* jest taka sama jak **/Gs4096**. Jeśli argument *size* ma wartość od 1 do 9, D9014 ostrzegawczy jest emitowany, a efekt jest taki sam jak określenie **/Gs4096**.

Dla wszystkich obiektów docelowych argument *rozmiaru* między 10 a 2147485647 ustawia próg dla określonej wartości. *Rozmiar* 2147485648 lub większy powoduje błąd krytyczny C1049.

Sondy stosu można włączać lub wyłączać za pomocą dyrektywy [check_stack](../../preprocessor/check-stack.md) . **/GS** i `check_stack` pragma nie ma wpływu na standardowe procedury biblioteki C; mają wpływ tylko na kompilację funkcji.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz   >  stronę właściwości konfiguracja wiersza polecenia **C/C++**  >   .

1. Wprowadź opcję kompilatora **/GS** i opcjonalny rozmiar w **opcjach dodatkowych**. Wybierz **przycisk OK** lub **Zastosuj** , aby zapisać zmiany.

### <a name="to-set-this-compiler-option-programmatically"></a>Aby programowo ustawić tę opcję kompilatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Zobacz też

[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)
