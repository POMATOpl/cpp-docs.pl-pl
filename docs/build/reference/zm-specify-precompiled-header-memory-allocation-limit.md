---
title: -Zm (Określ Limit alokacji pamięci Prekompilowanego nagłówka) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /zm
dev_langs:
- C++
helpviewer_keywords:
- PCH files, memory allocation limit
- Zm compiler option [C++]
- /Zm compiler option [C++]
- precompiled header files, memory allocation limit
- Specify Precompiled Header Memory Allocation Limit compiler option
- cl.exe compiler, memory allocation limit
- .pch files, memory allocation limit
- memory allocation, Memory Allocation Limit compiler option
- -Zm compiler option [C++]
ms.assetid: 94c77d5e-6672-46a7-92e0-3f69e277727d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9dfd1b0525991f81736af571d2c450e0c12edfc4
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/17/2018
ms.locfileid: "45702736"
---
# <a name="zm-specify-precompiled-header-memory-allocation-limit"></a>/Zm (Określ limit alokacji pamięci prekompilowanego nagłówka)

Określa ilość pamięci przydzielanej przez kompilator do konstruowania wstępnie skompilowanych nagłówków.

## <a name="syntax"></a>Składnia

```
/Zmfactor
```

## <a name="arguments"></a>Argumenty

*współczynnik*<br/>
Czynnik skalowania określa ilość pamięci, której kompilator używa do konstruowania wstępnie skompilowanych nagłówków.

*Współczynnik* argument jest wartością procentową domyślnego rozmiaru bufora roboczego zdefiniowanego przez kompilator. Wartość domyślna *współczynnik* wynosi 100 (procent), ale można określić więcej lub mniej.

## <a name="remarks"></a>Uwagi

We wcześniejszych wersjach Visual C++ kompilator używał kilku stert dyskretnych, a każda miała skończony limit. Obecnie kompilator dynamicznie powiększa sterty w miarę potrzeb, aż do całkowitego limitu rozmiaru sterty, i wymaga bufora o stałym rozmiarze wyłącznie w celu konstruowania wstępnie skompilowanych nagłówków. W związku z tym **/Zm** — opcja kompilatora jest niepotrzebna.

Jeśli kompilatorowi zabraknie miejsca na stertę i emituje [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md) komunikat o błędzie, gdy używasz **/Zm** — opcja kompilatora, prawdopodobnie zarezerwowano zbyt dużo pamięci. Rozważ usunięcie **/Zm** opcji. Jeśli kompilator generuje [C1076](../../error-messages/compiler-errors-1/fatal-error-c1076.md) komunikat o błędzie, towarzyszący [C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md) komunikat Określa *współczynnik* argumentu, aby zastosować, rekompilując przy użyciu **/Zm** — opcja kompilatora.

W poniższej tabeli przedstawiono sposób, w jaki *współczynnik* argument wpływa na limit alokacji pamięci, jeśli zakładać, że rozmiar domyślny bufora wstępnie skompilowanego nagłówka to 75 MB.

|Wartość atrybutu *współczynnik*|Limit alokacji pamięci|
|-----------------------|-----------------------------|
|10|W WERSJI 7.5 MB|
|100|75 MB|
|200|150 MB|
|1000|750 MB|
|2000|1500 MB|

## <a name="other-ways-to-set-the-memory-allocation-limit"></a>Inne sposoby ustawiania limitu alokacji pamięci

#### <a name="to-set-the-zm-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić opcję kompilatora /Zm w środowisku programistycznym Visual Studio

1. Otwórz projekt **stron właściwości** okno dialogowe. Aby uzyskać więcej informacji, zobacz [Praca z właściwościami projektu](../../ide/working-with-project-properties.md).

1. W okienku nawigacji wybierz **właściwości konfiguracji**, **C/C++**, **wiersza polecenia**.

1. Wprowadź **/Zm** w — opcja kompilatora **dodatkowe opcje** pole.

#### <a name="to-set-the-zm-compiler-option-programmatically"></a>Aby programowo ustawić opcję kompilatora /Zm

- Zobacz <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Zobacz też

[Opcje kompilatora](../../build/reference/compiler-options.md)<br/>
[Ustawianie opcji kompilatora](../../build/reference/setting-compiler-options.md)