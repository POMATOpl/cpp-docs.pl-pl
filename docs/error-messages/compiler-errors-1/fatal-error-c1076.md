---
description: 'Dowiedz się więcej na temat: błąd krytyczny C1076'
title: Błąd krytyczny C1076
ms.date: 03/08/2019
f1_keywords:
- C1076
helpviewer_keywords:
- C1076
ms.assetid: 84ac1180-3e8a-48e8-9f77-7f18a778b964
ms.openlocfilehash: 2d2ca5ffc8970affa6ddd01011e1a37c7b5b778d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341805"
---
# <a name="fatal-error-c1076"></a>Błąd krytyczny C1076

> limit kompilatora : limit sterty wewnętrznej osiągnięty; użyj /Zm, aby określić wyższy limit

Ten błąd może być spowodowany przez zbyt wiele symboli lub zbyt wiele wystąpień szablonu. Począwszy od programu Visual Studio 2015, ten komunikat może być spowodowany przez zbyt wiele równoległych procesów kompilacji. W takim przypadku zalecenie dotyczące korzystania z opcji **/zm** powinno być ignorowane, chyba że używana jest `#pragma hdrstop` dyrektywa.

Aby rozwiązać ten błąd:

1. Jeśli prekompilowany nagłówek używa `#pragma hdrstop` dyrektywy, użyj opcji [/zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) , aby ustawić limit pamięci kompilatora na wartość określoną w komunikacie o błędzie [C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md) . Aby uzyskać więcej informacji dotyczących sposobu ustawiania tej wartości w programie Visual Studio, zobacz sekcję Uwagi w [/zm (Określ limit alokacji pamięci prekompilowanego nagłówka)](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md).

1. Rozważ zmniejszenie liczby procesów równoległych określonych przy użyciu opcji **/maxcpucount** , aby MSBUILD.EXE w połączeniu z opcją **/mp** , aby CL.EXE. Aby uzyskać więcej informacji, zobacz [artykuły prekompilowanego nagłówka (pch) i zalecenia](https://devblogs.microsoft.com/cppblog/precompiled-header-pch-issues-and-recommendations/).

1. Jeśli używasz kompilatorów dla hostów 32-bitowych w 64-bitowym systemie operacyjnym, użyj kompilatorów dla hostów 64-bitowych. Aby uzyskać więcej informacji, zobacz [How to: Enable a 64-bitowy zestaw narzędzi Visual C++ w wierszu polecenia](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md).

1. Wyeliminuj niepotrzebne pliki dołączane.

1. Wyeliminuj niepotrzebne zmienne globalne — na przykład poprzez przydzielanie pamięci dynamicznie zamiast deklarowania dużej tablicy.

1. Usuń nieużywane deklaracje.

Jeśli C1076 występuje natychmiast po rozpoczęciu kompilacji, wartość określona dla **/zm** jest prawdopodobnie zbyt wysoka dla programu. Zmniejsz wartość **/zm** .
