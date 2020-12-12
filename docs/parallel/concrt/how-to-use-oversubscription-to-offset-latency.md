---
description: 'Dowiedz się więcej o: Instrukcje: używanie nadsubskrypcji do opóźnienia przesunięcia'
title: 'Porady: używanie nadsubskrypcji do przesuwania opóźnienia'
ms.date: 11/04/2016
helpviewer_keywords:
- oversubscription, using [Concurrency Runtime]
- using oversubscription [Concurrency Runtime]
ms.assetid: a1011329-2f0a-4afb-b599-dd4043009a10
ms.openlocfilehash: ec7b96703da2cbbe8a4d3caac3bfb1a1ff6f602a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341571"
---
# <a name="how-to-use-oversubscription-to-offset-latency"></a>Porady: używanie nadsubskrypcji do przesuwania opóźnienia

Nadpłata może zwiększyć ogólną wydajność niektórych aplikacji, które zawierają zadania o dużej ilości opóźnienia. W tym temacie przedstawiono sposób użycia nadsubskrypcji w celu przesunięcia opóźnienia, który jest spowodowany odczytem danych z połączenia sieciowego.

## <a name="example"></a>Przykład

Ten przykład używa [biblioteki agentów asynchronicznych](../../parallel/concrt/asynchronous-agents-library.md) do pobierania plików z serwerów HTTP. `http_reader`Klasa pochodzi od [concurrency:: Agent](../../parallel/concrt/reference/agent-class.md) i używa komunikatów przekazujących do asynchronicznego odczytywania nazw adresów URL do pobrania.

`http_reader`Klasa używa klasy [concurrency:: task_group](reference/task-group-class.md) , aby jednocześnie odczytać każdy plik. Każde zadanie wywołuje metodę [concurrency:: Context::](reference/context-class.md#oversubscribe) `_BeginOversubscription` subsubscription z parametrem ustawionym na wartość **`true`** , aby włączyć nadsubskrybowanie w bieżącym kontekście. Każde zadanie następnie używa klasy Microsoft Foundation Classes (MFC) [CInternetSession](../../mfc/reference/cinternetsession-class.md) i [CHttpFile](../../mfc/reference/chttpfile-class.md) , aby pobrać plik. Na koniec każde wywołanie zadania `Context::Oversubscribe` z `_BeginOversubscription` parametrem ustawionym na aby wyłączyć nadchodzące **`false`** subskrypcje.

Gdy subskrypcja jest włączona, środowisko uruchomieniowe tworzy jeden dodatkowy wątek, w którym będą uruchamiane zadania podrzędne. Każdy z tych wątków może również zasubskrybować bieżący kontekst i w efekcie utworzyć dodatkowe wątki. `http_reader`Klasa używa obiektu [concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md) , aby ograniczyć liczbę wątków używanych przez aplikację. Agent inicjuje bufor ze stałą liczbą wartości tokenu. Dla każdej operacji pobierania Agent odczytuje wartość tokenu z buforu przed rozpoczęciem operacji, a następnie zapisuje tę wartość z powrotem do buforu po zakończeniu operacji. Gdy bufor jest pusty, Agent czeka na jedną z operacji pobierania, aby zapisać wartość z powrotem do buforu.

Poniższy przykład ogranicza liczbę równoczesnych zadań do dwóch razy większej liczby dostępnych wątków sprzętowych. Ta wartość jest dobrym punktem wyjścia do użycia podczas eksperymentowania z nadsubskrypcją. Można użyć wartości, która pasuje do określonego środowiska przetwarzania lub dynamicznie zmienić tę wartość, aby odpowiadały rzeczywistemu obciążeniu.

[!code-cpp[concrt-download-oversubscription#1](../../parallel/concrt/codesnippet/cpp/how-to-use-oversubscription-to-offset-latency_1.cpp)]

Ten przykład generuje następujące dane wyjściowe na komputerze, który ma cztery procesory:

```Output
Downloading http://www.adatum.com/...
Downloading http://www.adventure-works.com/...
Downloading http://www.alpineskihouse.com/...
Downloading http://www.cpandl.com/...
Downloading http://www.cohovineyard.com/...
Downloading http://www.cohowinery.com/...
Downloading http://www.cohovineyardandwinery.com/...
Downloading http://www.contoso.com/...
Downloading http://www.consolidatedmessenger.com/...
Downloading http://www.fabrikam.com/...
Downloading http://www.fourthcoffee.com/...
Downloading http://www.graphicdesigninstitute.com/...
Downloading http://www.humongousinsurance.com/...
Downloading http://www.litwareinc.com/...
Downloading http://www.lucernepublishing.com/...
Downloading http://www.margiestravel.com/...
Downloading http://www.northwindtraders.com/...
Downloading http://www.proseware.com/...
Downloading http://www.fineartschool.net...
Downloading http://www.tailspintoys.com/...
Downloaded 1801040 bytes in 3276 ms.
```

Przykład może działać szybciej, gdy subskrypcja jest włączona, ponieważ zadania podrzędne są uruchamiane, podczas gdy inne zadania oczekują na zakończenie operacji ukrytego.

## <a name="compiling-the-code"></a>Kompilowanie kodu

Skopiuj przykładowy kod i wklej go w projekcie programu Visual Studio lub wklej go w pliku o nazwie, `download-oversubscription.cpp` a następnie Uruchom jedno z następujących poleceń w oknie **wiersza polecenia programu Visual Studio** .

```cmd
cl.exe /EHsc /MD /D "_AFXDLL" download-oversubscription.cpp
cl.exe /EHsc /MT download-oversubscription.cpp
```

## <a name="robust-programming"></a>Niezawodne programowanie

Zawsze należy wyłączyć nadsubskrypcji, gdy nie są już potrzebne. Rozważmy funkcję, która nie obsługuje wyjątku, który jest generowany przez inną funkcję. Jeśli nie wyłączysz nadsubskrypcji przed zwróceniem przez funkcję, wszelkie dodatkowe równoległe zadania również zasubskrybują bieżący kontekst.

Możesz użyć wzorca *pozyskiwania zasobów* (RAII), aby ograniczyć nadsubskrypcję do danego zakresu. Pod wzorcem RAII, struktura danych jest przypisana na stosie. Ta struktura danych inicjuje lub uzyskuje zasób podczas jego tworzenia i niszczy lub zwalnia ten zasób, gdy struktura danych zostanie zniszczona. Wzorzec RAII gwarantuje, że destruktor jest wywoływany przed wyjściem z otaczającego zakresu. W związku z tym zasób jest prawidłowo zarządzany, gdy wyjątek jest zgłaszany lub funkcja zawiera wiele **`return`** instrukcji.

W poniższym przykładzie zdefiniowano strukturę o nazwie `scoped_blocking_signal` . Konstruktor `scoped_blocking_signal` struktury umożliwia nadsubskrypcji i destruktor wyłącza nadsubskrypcji.

[!code-cpp[concrt-download-oversubscription#2](../../parallel/concrt/codesnippet/cpp/how-to-use-oversubscription-to-offset-latency_2.cpp)]

Poniższy przykład modyfikuje treść `download` metody, aby użyć RAII, aby upewnić się, że nadsubskrypcja jest wyłączona przed zwróceniem funkcji. Ta technika zapewnia, że `download` Metoda jest bezpieczna pod względem wyjątków.

[!code-cpp[concrt-download-oversubscription#3](../../parallel/concrt/codesnippet/cpp/how-to-use-oversubscription-to-offset-latency_3.cpp)]

## <a name="see-also"></a>Zobacz też

[Konteksty](../../parallel/concrt/contexts.md)<br/>
[Context:: subsubskrybuj — Metoda](reference/context-class.md#oversubscribe)
