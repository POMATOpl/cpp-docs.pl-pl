---
description: Dowiedz się więcej na temat:/ORDER (funkcje Put w kolejności)
title: /ORDER (Ustaw funkcje w kolejności)
ms.date: 09/05/2018
f1_keywords:
- VC.Project.VCLinkerTool.FunctionOrder
- /order
helpviewer_keywords:
- ORDER linker option
- -ORDER linker option
- LINK tool [C++], program optimizing
- /ORDER linker option
- LINK tool [C++], swap tuning
- paging, optimizing
ms.assetid: ecf5eb3e-e404-4e86-9a91-4e5ec157261a
ms.openlocfilehash: 36888cbb24c869d06eaaa5830b95ae76fc42b860
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226353"
---
# <a name="order-put-functions-in-order"></a>/ORDER (Ustaw funkcje w kolejności)

Określ kolejność łączy dla oddzielnie spakowanych funkcji (COMDAT).

## <a name="syntax"></a>Składnia

> **/Order: \@** <em>Nazwa pliku</em>

### <a name="parameters"></a>Parametry

*Nazwa pliku*<br/>
Plik tekstowy, który określa kolejność linków dla funkcji COMDAT.

## <a name="remarks"></a>Uwagi

Opcja kompilatora **/Order** pozwala zoptymalizować zachowanie stronicowania programu, grupując funkcję wraz z funkcjami wywoływanymi przez nią. Można również grupować często nazywane funkcje. Te techniki, znane jako *dostrajanie swap* lub *Optymalizacja stronicowania*, zwiększają prawdopodobieństwo, że wywołana funkcja jest w pamięci, gdy jest to konieczne i nie musi być stronicowana z dysku.

Podczas kompilowania kodu źródłowego do pliku obiektu, można powiedzieć kompilatorowi, aby umieszczał każdą funkcję do własnej sekcji o nazwie *COMDAT*, przy użyciu opcji kompilatora [/Gy (Włącz łączenie na poziomie funkcji)](gy-enable-function-level-linking.md) . Opcja konsolidatora **/Order** nakazuje konsolidatorowi umieszczenie COMDAT w obrazie wykonywalnym w określonej kolejności.

Aby określić kolejność COMDAT, Utwórz *plik odpowiedzi*, plik tekstowy, który wyświetla listę każdej COMDAT według nazwy, jeden na wiersz, w kolejności, w jakiej mają one zostać umieszczone przez konsolidator. Przekaż nazwę tego pliku jako parametr *filename* opcji **/Order** . Dla funkcji języka C++ Nazwa COMDAT jest dekoracyjną formą nazwy funkcji. Użyj niedekoracyjnej nazwy dla funkcji C, `main` i dla funkcji języka C++ zadeklarowanych jako `extern "C"` . Nazwy funkcji i nazwy dekoracyjne uwzględniają wielkość liter. Aby uzyskać więcej informacji na temat dekoracyjnych nazw, zobacz [nazwy dekoracyjne](decorated-names.md).

Aby znaleźć dekoracyjne nazwy COMDAT, użyj opcji [/Symbols](symbols.md) narzędzia [polecenia DUMPBIN](dumpbin-reference.md) w pliku obiektu. Konsolidator automatycznie dołącza podkreślenie ( **\_** ) do nazw funkcji w pliku odpowiedzi, chyba że nazwa zaczyna się od znaku zapytania (**?**) lub znaku ( **\@** ). Na przykład, jeśli plik źródłowy, przykład. cpp, zawiera funkcje `int cpp_func(int)` , `extern "C" int c_func(int)` a `int main(void)` polecenie `DUMPBIN /SYMBOLS example.obj` wyświetla następujące dekoracyjne nazwy:

```Output
...
088 00000000 SECT1A notype ()    External     | ?cpp_func@@YAHH@Z (int __cdecl cpp_func(int))
089 00000000 SECT22 notype ()    External     | _c_func
08A 00000000 SECT24 notype ()    External     | _main
...
```

W takim przypadku określ nazwy jako `?cpp_func@@YAHH@Z` , `c_func` , i `main` w pliku odpowiedzi.

Jeśli w opcjach konsolidatora zostanie wyświetlona więcej niż jedna opcja **/Order** , to Ostatnia z nich zacznie obowiązywać.

Opcja **/Order** wyłącza łączenie przyrostowe. Po określeniu tej opcji można zobaczyć [LNK4075 narzędzi konsolidatora](../../error-messages/tool-errors/linker-tools-warning-lnk4075.md) ostrzeżenia konsolidatora, jeśli jest włączone łączenie przyrostowe lub jeśli określono opcję kompilatora [/ZI (przyrostowe PDB)](z7-zi-zi-debug-information-format.md) . Aby wyciszyć to ostrzeżenie, można użyć opcji [/Incremental: No](incremental-link-incrementally.md) konsolidatora, aby wyłączyć konsolidację przyrostową, i użyć opcji kompilatora [/ZI (Generuj PDB)](z7-zi-zi-debug-information-format.md) do wygenerowania pliku PDB bez konsolidacji przyrostowej.

> [!NOTE]
> LINK nie może zamówić funkcji statycznych, ponieważ nazwy funkcji statycznych nie są nazwami symboli publicznych. Gdy **/Order** jest określony, zostanie wygenerowane ostrzeżenie konsolidatora [LNK4037](../../error-messages/tool-errors/linker-tools-warning-lnk4037.md) dla każdego symbolu w pliku odpowiedzi porządkowania, który jest statyczny lub nie został znaleziony.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz   >    >  stronę właściwości **optymalizacji** konsolidatora właściwości konfiguracji.

1. Zmodyfikuj właściwość **kolejność funkcji** , aby zawierała nazwę pliku odpowiedzi.

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.FunctionOrder%2A>.

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
