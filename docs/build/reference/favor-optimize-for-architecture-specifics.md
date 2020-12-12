---
description: Dowiedz się więcej na temat:/Favor (Optymalizacja pod kątem specyfiki architektury)
title: /favor (optymalizacja pod kątem specyfiki architektury)
ms.date: 11/04/2016
f1_keywords:
- /favor
helpviewer_keywords:
- -favor compiler option [C++]
- /favor compiler option [C++]
ms.assetid: ad264df2-e30f-4d68-8bd0-10d6bee71a2a
ms.openlocfilehash: 184e81e1007214a09088601b6c579692a0dd20a7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192307"
---
# <a name="favor-optimize-for-architecture-specifics"></a>/favor (optymalizacja pod kątem specyfiki architektury)

**/Favor:** `option` Tworzy kod, który jest zoptymalizowany pod kątem określonej architektury lub dla określonych mikroarchitektur w architekturze AMD i Intel.

## <a name="syntax"></a>Składnia

> **/Favor:**{**Blend**  |  **Atom**  |  **amd64**  |  **Intel64**}

## <a name="remarks"></a>Uwagi

**/Favor: Blend**<br/>
(x86 i x64) generuje kod, który jest zoptymalizowany pod kątem określonych mikroarchitektur w architekturze AMD i Intel. Chociaż **/Favor: Blend** może nie zapewniać najlepszej wydajności na określonym procesorze, jest przeznaczona do zapewnienia najlepszej wydajności dla szerokiego zakresu procesorów x86 i x64. Domyślnie **/Favor: Blend** jest w efekcie.

**/Favor: ATOM**<br/>
(x86 i x64) generuje kod, który jest zoptymalizowany pod kątem określonych technologii procesora Intel Atom i procesorów Intel Centrino Atom. Kod generowany przy użyciu **/Favor: Atom** może również generować instrukcje Intel SSSE3, SSE3, SSE2 i SSE dla procesorów firmy Intel.

**/Favor: AMD64**<br/>
(tylko x64) optymalizuje wygenerowany kod dla procesorów AMD Opteron i Athlon, które obsługują rozszerzenia 64-bitowe. Zoptymalizowany kod można uruchomić na wszystkich platformach zgodnych z architekturą x64. Kod wygenerowany przy użyciu **/Favor: amd64** może spowodować gorszą wydajność procesorów Intel, które obsługują Intel64.

**/Favor: INTEL64**<br/>
(tylko x64) optymalizuje wygenerowany kod dla procesorów Intel, które obsługują Intel64, co zwykle zapewnia lepszą wydajność dla tej platformy. Otrzymany kod można uruchomić na dowolnej platformie x64. Kod wygenerowany przy użyciu **/Favor: Intel64** może spowodować gorszą wydajność w przypadku procesorów AMD Opteron i Athlon, które obsługują rozszerzenia 64-bitowe.

> [!NOTE]
> Architektura Intel64 była wcześniej znana jako technologia Extended Memory 64, a odpowiednia opcja kompilatora to **/Favor: EM64T**.

Aby uzyskać informacje na temat sposobu programowania architektury x64, zobacz [konwencje oprogramowania x64](../x64-software-conventions.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz folder **C/C++** .

1. Wybierz stronę właściwości **wiersza polecenia** .

1. Wprowadź opcję kompilatora w polu **dodatkowe opcje** .

### <a name="to-set-this-compiler-option-programmatically"></a>Aby programowo ustawić tę opcję kompilatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Zobacz też

[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)
