---
description: Dowiedz się więcej o:/F (Ustaw rozmiar stosu)
title: /F (Ustaw rozmiar stosu)
ms.date: 11/04/2016
f1_keywords:
- /f
helpviewer_keywords:
- set stack size compiler option
- F compiler option [C++]
- -F compiler option [C++]
- /F compiler option [C++]
- stack, setting size
ms.assetid: 17320b6f-8305-445b-9ec2-75833f4b29e0
ms.openlocfilehash: 5bf8b0855c65fc39caf8935b06a877c62a4e0df0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200783"
---
# <a name="f-set-stack-size"></a>/F (Ustaw rozmiar stosu)

Ustawia rozmiar stosu programu w bajtach.

## <a name="syntax"></a>Składnia

>  *Liczba* /f

## <a name="arguments"></a>Argumenty

*Liczba*<br/>
Rozmiar stosu w bajtach.

## <a name="remarks"></a>Uwagi

Bez tej opcji rozmiar stosu ma wartość domyślną 1 MB. Argument *Number* może być w notacji dziesiętnej lub w języku C. Argument może mieć wartość z zakresu od 1 do maksymalnego rozmiaru stosu zaakceptowanego przez konsolidator. Konsolidator zaokrągla określoną wartość do najbliższej 4 bajtów. Spacja między elementami **/f** i *Number* jest opcjonalna.

Może być konieczne zwiększenie rozmiaru stosu, jeśli program pobiera komunikaty przepełnienia stosu.

Możesz również ustawić rozmiar stosu według:

- Korzystanie z opcji konsolidatora **/Stack** . Aby uzyskać więcej informacji, zobacz [/Stack](stack.md).

- Używanie polecenia EDITBIN w pliku. exe. Aby uzyskać więcej informacji, zobacz [polecenia EDITBIN Reference](editbin-reference.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz   >  stronę właściwości konfiguracja wiersza polecenia **C/C++**  >   .

1. Wpisz opcję kompilatora w polu **dodatkowe opcje** .

### <a name="to-set-this-compiler-option-programmatically"></a>Aby programowo ustawić tę opcję kompilatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Zobacz też

[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)
