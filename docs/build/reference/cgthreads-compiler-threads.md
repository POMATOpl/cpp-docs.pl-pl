---
description: Dowiedz się więcej o:/CGTHREADS (wątki kompilatora)
title: /CGTHREADS (wątki kompilatora)
ms.date: 11/04/2016
helpviewer_keywords:
- /CGTHREADS linker option
- -CGTHREADS linker option
- CGTHREADS linker option
ms.assetid: 4b52cfdb-3702-470b-9580-fabeb1417488
ms.openlocfilehash: 71c5031c7013ec6f8ddad153d9cc16bee2004751
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179255"
---
# <a name="cgthreads-compiler-threads"></a>/CGTHREADS (wątki kompilatora)

Ustawia liczbę cl.exe wątków do użycia na potrzeby optymalizacji i generowania kodu, gdy zostanie określone generowanie kodu w czasie konsolidacji.

## <a name="syntax"></a>Składnia

```
/CGTHREADS:[1-8]
```

## <a name="arguments"></a>Argumenty

*Liczba*<br/>
Maksymalna liczba cl.exe wątków do użycia w zakresie od 1 do 8.

## <a name="remarks"></a>Uwagi

Opcja **/cgthreads** określa maksymalną liczbę wątków, cl.exe równolegle używa dla fazy optymalizacji i generowania kodu podczas kompilowania, gdy określono generowanie kodu w czasie konsolidacji ([/LTCG](ltcg-link-time-code-generation.md)). Domyślnie cl.exe używa czterech wątków, tak jakby określono **/cgthreads: 4** . Jeśli jest dostępnych więcej rdzeni procesora, większa `number` wartość może skrócić czas kompilacji.

Dla kompilacji można określić wiele poziomów równoległości. Przełącznik msbuild.exe **/maxcpucount** określa liczbę procesów programu MSBuild, które mogą być uruchamiane równolegle. Flaga programu [/MP (kompilacja z wieloma procesami)](mp-build-with-multiple-processes.md) określa liczbę procesów cl.exe, które jednocześnie kompilują pliki źródłowe. Opcja kompilatora [/cgthreads](cgthreads-code-generation-threads.md) określa liczbę wątków używanych przez proces poszczególnych cl.exe. Ponieważ procesor może działać tylko w wielu wątkach w tym samym czasie, w którym występują rdzenie procesora, nie jest przydatne Określanie większych wartości dla wszystkich tych opcji w tym samym czasie i może być counterproductive. Aby uzyskać więcej informacji o tym, jak kompilować projekty równolegle, zobacz [kompilowanie wielu projektów równolegle](/visualstudio/msbuild/building-multiple-projects-in-parallel-with-msbuild).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz **Właściwości konfiguracji**, folder **konsolidatora** .

1. Wybierz stronę właściwości **wiersza polecenia** .

1. Zmodyfikuj właściwość **Opcje dodatkowe** , aby uwzględnić **/cgthreads:** `number` , gdzie `number` ma wartość od 1 do 8, a następnie wybierz **OK**.

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Zobacz też

[MSVC Opcje konsolidatora](linker-options.md)<br/>
[Dokumentacja konsolidatora MSVC](linking.md)
