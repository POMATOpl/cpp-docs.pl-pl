---
description: 'Dowiedz się więcej na temat: jak udostępniać funkcje pracy do klas wywołań i transformatora'
title: 'Porady: zapewnianie funkcji pracy dla wywoływania oraz klasy transformatora'
ms.date: 11/04/2016
helpviewer_keywords:
- call class, example
- using the transformer class [Concurrency Runtime]
- using the call class [Concurrency Runtime]
ms.assetid: df715ce4-8507-41ca-b204-636d11707a73
ms.openlocfilehash: 05def4dcc8357e73a8606fbc4ce741eebb647d37
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97197364"
---
# <a name="how-to-provide-work-functions-to-the-call-and-transformer-classes"></a>Porady: zapewnianie funkcji pracy dla wywoływania oraz klasy transformatora

W tym temacie przedstawiono kilka sposobów udostępniania funkcji roboczych do klas [concurrency:: Call](../../parallel/concrt/reference/call-class.md) i [concurrency:: Transformer](../../parallel/concrt/reference/transformer-class.md) .

Pierwszy przykład pokazuje, jak przekazać wyrażenie lambda do `call` obiektu. Drugi przykład pokazuje, jak przekazać obiekt Function do `call` obiektu. Trzeci przykład pokazuje, jak powiązać metodę klasy z `call` obiektem.

W przypadku ilustracji, każdy przykład w tym temacie używa `call` klasy. Aby zapoznać się z przykładem, który korzysta z `transformer` klasy, zobacz [How to: use Transformer in a Potok danych](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md).

## <a name="example-call-class"></a>Przykład: wywoływanie klasy

Poniższy przykład przedstawia typowy sposób użycia `call` klasy. Ten przykład przekazuje funkcję lambda do `call` konstruktora.

[!code-cpp[concrt-call-lambda#1](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_1.cpp)]

Ten przykład generuje następujące dane wyjściowe.

```Output
13 squared is 169.
```

## <a name="example-call-class-with-function-object"></a>Przykład: wywoływanie klasy z obiektem Function

Poniższy przykład przypomina poprzednią, z tą różnicą, że używa `call` klasy razem z obiektem funkcji (Funktor).

[!code-cpp[concrt-call-functor#1](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_2.cpp)]

## <a name="example-functions-to-bind-call-object"></a>Przykład: funkcje do powiązania obiektu wywołania

Poniższy przykład przypomina poprzednią, z tą różnicą, że używa funkcji [std:: bind1st —](../../standard-library/functional-functions.md#bind1st) i [std:: mem_fun](../../standard-library/functional-functions.md#mem_fun) , aby powiązać `call` obiekt z metodą klasy.

Użyj tej techniki, jeśli musisz powiązać `call` `transformer` obiekt lub z konkretną metodą klasy zamiast operatora wywołania funkcji `operator()` .

[!code-cpp[concrt-call-method#1](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_3.cpp)]

Możesz również przypisać wynik `bind1st` funkcji do obiektu [std:: Function](../../standard-library/function-class.md) lub użyć **`auto`** słowa kluczowego, jak pokazano w poniższym przykładzie.

[!code-cpp[concrt-call-method#2](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_4.cpp)]

## <a name="compiling-the-code"></a>Kompilowanie kodu

Skopiuj przykładowy kod i wklej go w projekcie programu Visual Studio lub wklej go w pliku o nazwie, `call.cpp` a następnie uruchom następujące polecenie w oknie wiersza polecenia programu Visual Studio.

> **cl.exe/EHsc. cpp**

## <a name="see-also"></a>Zobacz też

[Biblioteki agentów asynchronicznych](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Bloki komunikatów asynchronicznych](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Instrukcje: używanie transformatora w potoku danych](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)<br/>
[Call, Klasa](../../parallel/concrt/reference/call-class.md)<br/>
[transformator — Klasa](../../parallel/concrt/reference/transformer-class.md)
