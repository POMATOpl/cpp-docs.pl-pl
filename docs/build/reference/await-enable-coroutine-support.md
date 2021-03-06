---
description: Dowiedz się więcej na temat:/Await (Włącz obsługę wspólną)
title: /await (Włącz obsługę koprocedury)
ms.date: 08/15/2017
f1_keywords:
- /await
- -await
helpviewer_keywords:
- /await enable coroutine support [C++]
- -await enable coroutine support [C++]
- await enable coroutine support [C++]
ms.assetid: 302c8e69-09b6-4c58-bcdd-0a6a8713a8df
ms.openlocfilehash: a36c2233085a1c38ed61aed7d6ea757762179cc4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182765"
---
# <a name="await-enable-coroutine-support"></a>/await (Włącz obsługę koprocedury)

Użyj opcji kompilatora **/await** , aby włączyć obsługę kompilatora dla procedur wspólnych.

## <a name="syntax"></a>Składnia

> /await

## <a name="remarks"></a>Uwagi

Opcja kompilatora **/await** umożliwia obsługę kompilatora dla procedur wspólnych języka C++ i słów kluczowych **`co_await`** , **`co_yield`** i **`co_return`** . Ta opcja jest domyślnie wyłączona. Aby uzyskać informacje o obsłudze wspólnych procedur w programie Visual Studio, zapoznaj się z [blogiem zespołu programu Visual Studio](https://devblogs.microsoft.com/cppblog/category/coroutine/). Aby uzyskać więcej informacji na temat standardowej oferty wspólnej procedury, zobacz [N4628 Work robocza, Specyfikacja techniczna dla rozszerzeń języka C++ dla wspólnych procedur](https://wg21.link/n4628).

Opcja **/await** jest dostępna, zaczynając od programu Visual Studio 2015.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu.

1. W obszarze **Właściwości konfiguracji** rozwiń folder **C/C++** i wybierz stronę właściwości **wiersza polecenia** .

1. Wprowadź opcję kompilatora **/await** w polu **dodatkowe opcje** . Wybierz **przycisk OK** lub **Zastosuj** , aby zapisać zmiany.

### <a name="to-set-this-compiler-option-programmatically"></a>Aby programowo ustawić tę opcję kompilatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Zobacz też

[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)
