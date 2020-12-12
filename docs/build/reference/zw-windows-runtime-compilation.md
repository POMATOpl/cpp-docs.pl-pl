---
description: Dowiedz się więcej na temat:/ZW (kompilacja środowisko wykonawcze systemu Windows)
title: /ZW (Kompilacja środowiska wykonawczego systemu Windows)
ms.date: 04/08/2019
f1_keywords:
- VC.Project.VCCLCompilerTool.CompileAsWinRT
- /zw
helpviewer_keywords:
- /ZW
- -ZW compiler option
- /ZW compiler option
- -ZW
- Windows Runtime compiler option
ms.assetid: 0fe362b0-9526-498b-96e0-00d7a965a248
ms.openlocfilehash: b2c39cdfb3f1d22d12c8d07b1e844c550a7a0e3a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97273920"
---
# <a name="zw-windows-runtime-compilation"></a>/ZW (Kompilacja środowiska wykonawczego systemu Windows)

Kompiluje kod źródłowy, aby obsługiwał rozszerzenia Microsoft C++ Component Extensions C++/CX na potrzeby tworzenia aplikacji platforma uniwersalna systemu Windows (platformy UWP).

W przypadku użycia **/zw** do skompilowania zawsze należy określić również **/EHsc** .

## <a name="syntax"></a>Składnia

```cpp
/ZW /EHsc
/ZW:nostdlib /EHsc
```

## <a name="arguments"></a>Argumenty

**nostdlib**<br/>
Wskazuje, że w kompilacji nie są automatycznie dołączane pliki platform. winmd, Windows, Foundation. winmd i innych domyślnych plików metadanych systemu Windows (WinMD). Zamiast tego należy użyć opcji kompilatora [/Fu (Name force #using File)](fu-name-forced-hash-using-file.md) , aby jawnie określić pliki metadanych systemu Windows.

## <a name="remarks"></a>Uwagi

Po określeniu opcji **/zw** kompilator obsługuje następujące funkcje:

- Wymagane pliki metadanych, przestrzenie nazw, typy danych i funkcje wymagane przez aplikację do wykonania w środowisko wykonawcze systemu Windows.

- Automatyczne odwołanie-Zliczanie obiektów środowisko wykonawcze systemu Windows i automatyczne odrzucanie obiektu, gdy jego liczba odwołań spadnie do zera.

Ponieważ przyrostowy konsolidator nie obsługuje metadanych systemu Windows zawartych w plikach. obj przy użyciu opcji **/zw** , przestarzałe [/GM (Włącz minimalną](gm-enable-minimal-rebuild.md) ponowną kompilację) nie są zgodne z **/zw**.

Aby uzyskać więcej informacji, zobacz [informacje dotyczące języka Visual C++](../../cppcx/visual-c-language-reference-c-cx.md).

## <a name="requirements"></a>Wymagania

## <a name="see-also"></a>Zobacz też

[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)
