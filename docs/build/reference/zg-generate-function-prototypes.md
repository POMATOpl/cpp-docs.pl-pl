---
description: Dowiedz się więcej na temat:/zg (Generuj prototypy funkcji)
title: /Zg (Generuj prototypy funkcji)
ms.date: 11/04/2016
f1_keywords:
- /zg
helpviewer_keywords:
- Zg compiler option [C++]
- /Zg compiler option [C++]
- function prototypes, generate function prototypes compiler option
- -Zg compiler option [C++]
- generate function prototypes compiler option
ms.assetid: c8df1b46-24ff-46f2-8356-e0a144b21dd2
ms.openlocfilehash: ee0bed48f15acae867d344a60a6d42f3b17c7e85
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97178878"
---
# <a name="zg-generate-function-prototypes"></a>/Zg (Generuj prototypy funkcji)

Usuwane. Tworzy prototyp funkcji dla każdej funkcji zdefiniowanej w pliku źródłowym, ale nie kompiluje pliku źródłowego.

## <a name="syntax"></a>Składnia

```
/Zg
```

## <a name="remarks"></a>Uwagi

Ta opcja kompilatora nie jest już dostępna. Zostało usunięte w programie Visual Studio 2015. Ta strona nie jest dostępna dla użytkowników starszych wersji programu Visual Studio.

Prototyp funkcji zawiera typ zwracany funkcji i listę typów argumentów. Lista Typ argumentu jest tworzona na podstawie typów parametrów formalnych funkcji. Wszystkie prototypy funkcji, które znajdują się już w pliku źródłowym, są ignorowane.

Lista prototypów jest zapisywana w standardowym wyjściu. Ta lista może być przydatna do sprawdzenia, czy rzeczywiste argumenty i formalne parametry funkcji są zgodne. Możesz zapisać listę, przekierowując standardowe dane wyjściowe do pliku. Następnie możesz użyć **#include** , aby utworzyć listę prototypów funkcji dla części pliku źródłowego. Wykonanie tej czynności powoduje, że kompilator wykonuje sprawdzanie typu argumentu.

Jeśli używasz opcji **/zg** , a program zawiera formalne parametry, które mają typ struct, enum lub Union (lub wskaźniki do takich typów), deklaracja każdej struktury, wyliczenia lub typu Unii musi mieć tag (Name). W poniższym przykładzie nazwa tagu to `MyStruct` .

```C
// Zg_compiler_option.c
// compile with: /Zg
typedef struct MyStruct { int i; } T2;
void f2(T2 * t) {}
```

Opcja **/zg** była przestarzała w programie visual Studio 2005 i została usunięta w programie visual Studio 2015. Kompilator MSVC usunął obsługę starszego kodu języka C. Aby zapoznać się z listą przestarzałych opcji kompilatora, zobacz Opcje kompilatora **przestarzałe i usunięte** w [opcjach kompilatora wymienionych według kategorii](compiler-options-listed-by-category.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Kliknij folder **C/C++** .

1. Kliknij stronę właściwości **wiersza polecenia** .

1. Wpisz opcję kompilatora w polu **dodatkowe opcje** .

### <a name="to-set-this-compiler-option-programmatically"></a>Aby programowo ustawić tę opcję kompilatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Zobacz też

[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)
