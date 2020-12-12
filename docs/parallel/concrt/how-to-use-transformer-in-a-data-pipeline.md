---
description: 'Dowiedz się więcej na temat: jak używać transformatora w potoku danych'
title: 'Porady: używanie transformatora w potoku danych'
ms.date: 11/04/2016
helpviewer_keywords:
- transformer class, example
- data pipelines, using transformer [Concurrency Runtime]
- using transformer in data pipelines [Concurrency Runtime]
ms.assetid: ca49cb3f-4dab-4b09-a9c9-d3a109ae4c29
ms.openlocfilehash: 97b0af16a3ce89b940952117bb8639d281363a23
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97205619"
---
# <a name="how-to-use-transformer-in-a-data-pipeline"></a>Porady: używanie transformatora w potoku danych

Ten temat zawiera podstawowy przykład, który pokazuje, jak używać klasy [concurrency:: Transformer](../../parallel/concrt/reference/transformer-class.md) w potoku danych. Aby zapoznać się z bardziej kompletnym przykładem, który używa potoku danych do przetwarzania obrazu, zobacz [Przewodnik: tworzenie sieci Image-Processing](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md).

*Przetwarzanie potokowe danych* jest typowym wzorcem w współbieżnym programowaniu. Potok danych składa się z serii etapów, w których każdy etap wykonuje prace, a następnie przekazuje wynik pracy do następnego etapu. `transformer`Klasa a składnika w potokach danych, ponieważ odbiera wartość wejściową, wykonuje prace nad tą wartością, a następnie tworzy wynik dla innego składnika do użycia.

## <a name="example"></a>Przykład

Ten przykład używa potoku danych, aby wykonać serię transformacji przy użyciu początkowej wartości wejściowej:

1. Pierwszy etap oblicza wartość bezwzględną danych wejściowych.

1. Drugi etap Oblicza pierwiastek kwadratowy wartości wejściowej.

1. Trzeci etap oblicza kwadrat swoich danych wejściowych.

1. Etap z przodu wyklucza swoje dane wejściowe.

1. Piąty etap zapisuje końcowy wynik do buforu komunikatów.

Na koniec przykład drukuje wynik potoku do konsoli.

[!code-cpp[concrt-data-pipeline#1](../../parallel/concrt/codesnippet/cpp/how-to-use-transformer-in-a-data-pipeline_1.cpp)]

Ten przykład generuje następujące wyniki:

```Output
The result is -42.
```

Typowy dla etapu w potoku danych wyprowadza wartość, której typ różni się od wartości wejściowej. W tym przykładzie drugi etap przyjmuje wartość typu **`int`** jako dane wejściowe i tworzy pierwiastek kwadratowy tej wartości (a **`double`** ) jako dane wyjściowe.

> [!NOTE]
> Potok danych w tym przykładzie dotyczy ilustracji. Ponieważ każda operacja transformacji wykonuje niewiele pracy, obciążenie wymagane do przeprowadzenia przekazywania komunikatów może wzczerpać korzyści wynikające z używania potoku danych.

## <a name="compiling-the-code"></a>Kompilowanie kodu

Skopiuj przykładowy kod i wklej go w projekcie programu Visual Studio lub wklej go w pliku o nazwie, `data-pipeline.cpp` a następnie uruchom następujące polecenie w oknie wiersza polecenia programu Visual Studio.

> **cl.exe/EHsc Data-Pipeline. cpp**

## <a name="see-also"></a>Zobacz też

[Biblioteki agentów asynchronicznych](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Bloki komunikatów asynchronicznych](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Przewodnik: tworzenie sieci Image-Processing](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)
