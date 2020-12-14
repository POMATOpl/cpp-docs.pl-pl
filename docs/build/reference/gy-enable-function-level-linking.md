---
description: Dowiedz się więcej na temat:/Gy (Włącz łączenie Function-Level)
title: /Gy (Włączenie łączenia na poziomie funkcji)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableFunctionLevelLinking
- /gy
- VC.Project.VCCLWCECompilerTool.EnableFunctionLevelLinking
helpviewer_keywords:
- enable function-level linking compiler option [C++]
- COMDAT function
- Gy compiler option [C++]
- -Gy compiler option [C++]
- /Gy compiler option [C++]
- packaged functions
ms.assetid: 0d3cf14c-ed7d-4ad3-b4b6-104e56f61046
ms.openlocfilehash: 3c4136b25001f7f6d6729b9c6089995d1bcd71bf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200133"
---
# <a name="gy-enable-function-level-linking"></a>/Gy (Włączenie łączenia na poziomie funkcji)

Umożliwia kompilatorowi pakowanie poszczególnych funkcji w postaci spakowanych funkcji (COMDAT).

## <a name="syntax"></a>Składnia

```
/Gy[-]
```

## <a name="remarks"></a>Uwagi

Konsolidator wymaga, aby funkcje zostały opakowane oddzielnie jako COMDAT, aby wykluczyć lub zamówić poszczególne funkcje w pliku DLL lub exe.

Można użyć opcji konsolidatora [/opt (optymalizacje)](opt-optimizations.md) do wykluczenia spakowanych funkcji, które nie są używane, z pliku. exe.

Można użyć opcji konsolidatora [/Order (Put funkcje w kolejności)](order-put-functions-in-order.md) , aby dołączyć spakowane funkcje w określonej kolejności w pliku. exe.

Wbudowane funkcje są zawsze opakowane, jeśli są tworzone jako wywołania (które występują na przykład wtedy, gdy funkcja deokładziny jest wyłączona lub przyjmujesz adres funkcji). Ponadto funkcje składowe języka C++ zdefiniowane w deklaracji klasy są automatycznie spakowane; inne funkcje nie są, a wybranie tej opcji jest wymagane do skompilowania ich jako spakowane funkcje.

> [!NOTE]
> Opcja [/Zi](z7-zi-zi-debug-information-format.md) używana do edycji i kontynuowania powoduje automatyczne ustawienie opcji **/Gy** .

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Kliknij folder **C/C++** .

1. Kliknij stronę właściwości **generowanie kodu** .

1. Zmodyfikuj właściwość **Włącz łączenie Function-Level** .

### <a name="to-set-this-compiler-option-programmatically"></a>Aby programowo ustawić tę opcję kompilatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableFunctionLevelLinking%2A>.

## <a name="see-also"></a>Zobacz też

[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)
