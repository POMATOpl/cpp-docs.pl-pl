---
description: 'Dowiedz się więcej na temat: Biblioteka agentów asynchronicznych'
title: Biblioteki agentów asynchronicznych
ms.date: 11/19/2018
helpviewer_keywords:
- Agents Library
- Asynchronous Agents Library
ms.assetid: d2a72a31-8ba6-4220-ad7a-e403a6acaa42
ms.openlocfilehash: 5d56bd84078d4c1a89fc489fba37edeb03b3739f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338304"
---
# <a name="asynchronous-agents-library"></a>Biblioteki agentów asynchronicznych

Biblioteka agentów asynchronicznych (lub tylko *Biblioteka agentów*) zapewnia model programowania, który pozwala zwiększyć niezawodność tworzenia aplikacji obsługujących współbieżność. Biblioteka agentów jest biblioteką szablonów języka C++, która wspiera model programowania oparty na aktorze i przetwarza komunikat w procesie, który jest przekazywany przez duże i przepływu danych zadania przetwarzania potokowego. Biblioteka agenci jest oparta na składnikach planowania i zarządzania zasobami środowisko uruchomieniowe współbieżności.

## <a name="programming-model"></a>Model programowania

Biblioteka agenci zapewnia alternatywy dla udostępnionego stanu, umożliwiając łączenie izolowanych składników za pośrednictwem asynchronicznego modelu komunikacji opartego na przepływu danych zamiast przepływu sterowania. *Przepływu danych* odnosi się do modelu programowania, w którym obliczenia są wykonywane, gdy wszystkie wymagane dane są dostępne; *przepływ sterowania* odnosi się do modelu programowania, w którym obliczenia są wykonywane we wstępnie określonej kolejności.

Model programowania przepływu danych jest powiązany z koncepcją *przekazywania komunikatów*, gdzie niezależne składniki programu komunikują się ze sobą przez wysyłanie komunikatów.

Biblioteka agentów składa się z trzech składników: *agentów asynchronicznych*, *bloków komunikatów asynchronicznych* i *funkcji przekazywania komunikatów*. Agenci utrzymują stan i używają bloków komunikatów oraz funkcji przekazywania komunikatów, aby komunikować się ze sobą i ze składnikami zewnętrznymi. Funkcje przekazywania komunikatów umożliwiają agentom wysyłanie i odbieranie komunikatów do i ze składników zewnętrznych. Bloki komunikatów asynchronicznych przechowują komunikaty i umożliwiają agentom komunikowanie się w sposób zsynchronizowany.

Na poniższej ilustracji przedstawiono, jak dwa agenci używają bloków komunikatów i funkcji przekazywania komunikatów do komunikacji. Na tej ilustracji `agent1` wysyła komunikat do `agent2` przy użyciu obiektu [concurrency:: Send](reference/concurrency-namespace-functions.md#send) i [concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md) . `agent2` używa funkcji [concurrency:: Receive](reference/concurrency-namespace-functions.md#receive) , aby odczytać komunikat. `agent2` używa tej samej metody do wysyłania komunikatu do `agent1` . Strzałki kreskowane reprezentują przepływ danych między agentami. Pełne strzałki łączą agentów z blokami komunikatów, do których zapisują lub odczytują.

![Składniki biblioteki agentów](../../parallel/concrt/media/agent_librarycomp.png "Składniki biblioteki agentów")

Przykład kodu, który implementuje tę ilustrację, przedstawiono w dalszej części tego tematu.

Model programowania agentów ma kilka zalet niż inne mechanizmy współbieżności i synchronizacji, na przykład zdarzenia. Jedną z zalety jest to, że dzięki użyciu przekazywania komunikatów do przesyłania zmian stanu między obiektami można izolować dostęp do zasobów udostępnionych, a tym samym zwiększyć skalowalność. Zalety przekazywania komunikatów polega na tym, że wiąże się z synchronizacją danych, zamiast połączyć ją z zewnętrznym obiektem synchronizacji. Upraszcza to przesyłanie danych między składnikami i może wyeliminować błędy programistyczne w aplikacjach.

## <a name="when-to-use-the-agents-library"></a>Kiedy należy używać biblioteki agentów

Biblioteka agentów jest używana, gdy istnieje wiele operacji, które muszą komunikować się ze sobą asynchronicznie. Bloki komunikatów i funkcje przekazywania komunikatów umożliwiają pisanie aplikacji równoległych, które nie wymagają mechanizmów synchronizacji, takich jak blokady. Dzięki temu można skoncentrować się na logice aplikacji.

Model programowania agentów jest często używany do tworzenia *potoków danych* lub *sieci*. Potok danych to seria składników, z których każdy wykonuje konkretne zadanie, które przyczynia się do większego celu. Każdy składnik w potoku przepływu danych wykonuje działanie, gdy odbierze komunikat z innego składnika. Wynik tej pracy jest przesyłany do innych składników w potoku lub sieci. Składniki mogą korzystać z bardziej precyzyjnych funkcji współbieżności z innych bibliotek, na przykład [biblioteki równoległych wzorców (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md).

## <a name="example"></a>Przykład

Poniższy przykład implementuje ilustrację przedstawioną wcześniej w tym temacie.

[!code-cpp[concrt-basic-agents#1](../../parallel/concrt/codesnippet/cpp/asynchronous-agents-library_1.cpp)]

Ten przykład generuje następujące wyniki:

```Output
agent1: sending request...
agent2: received 'request'.
agent2: sending response...
agent1: received '42'.
```

W poniższych tematach opisano funkcje używane w tym przykładzie.

## <a name="related-topics"></a>Tematy pokrewne

[Agenci asynchroniczni](../../parallel/concrt/asynchronous-agents.md)<br/>
Opisuje rolę agentów asynchronicznych w rozwiązywaniu większych zadań obliczeniowych.

[Bloki komunikatów asynchronicznych](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
Opisuje różne typy bloku komunikatów dostarczone przez bibliotekę agentów.

[Funkcje przekazywania komunikatów](../../parallel/concrt/message-passing-functions.md)<br/>
Opisuje różne procedury przekazywania komunikatów, które są dostarczane przez bibliotekę agentów.

[Instrukcje: implementowanie różnych wzorców Producer-Consumer](../../parallel/concrt/how-to-implement-various-producer-consumer-patterns.md)<br/>
W tym artykule opisano sposób implementacji wzorca producenta klienta w aplikacji.

[Instrukcje: zapewnianie funkcji pracy dla klas wywołania i transformatora](../../parallel/concrt/how-to-provide-work-functions-to-the-call-and-transformer-classes.md)<br/>
Ilustruje kilka sposobów udostępniania funkcji roboczych do klas [concurrency:: Call](../../parallel/concrt/reference/call-class.md) i [concurrency:: Transformer](../../parallel/concrt/reference/transformer-class.md) .

[Instrukcje: używanie transformatora w potoku danych](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)<br/>
Pokazuje, w jaki sposób używać klasy [concurrency:: Transformer](../../parallel/concrt/reference/transformer-class.md) w potoku danych.

[Instrukcje: wybieranie spośród ukończonych zadań](../../parallel/concrt/how-to-select-among-completed-tasks.md)<br/>
Pokazuje, w jaki sposób używać klas [concurrency:: Choice](../../parallel/concrt/reference/choice-class.md) i [concurrency:: join](../../parallel/concrt/reference/join-class.md) , aby wybrać pierwsze zadanie do ukończenia algorytmu wyszukiwania.

[Instrukcje: Wysyłanie komunikatu w regularnych odstępach czasu](../../parallel/concrt/how-to-send-a-message-at-a-regular-interval.md)<br/>
Pokazuje, w jaki sposób używać klasy [concurrency:: Timer](../../parallel/concrt/reference/timer-class.md) do wysyłania komunikatu w regularnych odstępach czasu.

[Instrukcje: korzystanie z filtru bloku komunikatów](../../parallel/concrt/how-to-use-a-message-block-filter.md)<br/>
Pokazuje, jak użyć filtru, aby włączyć asynchroniczny blok komunikatów do akceptowania lub odrzucania wiadomości.

[Biblioteka równoległych wzorców (PLL)](../../parallel/concrt/parallel-patterns-library-ppl.md)<br/>
Opisuje sposób używania różnych równoległych wzorców, takich jak algorytmy równoległe, w aplikacjach.

[Współbieżność środowiska wykonawczego](../../parallel/concrt/concurrency-runtime.md)<br/>
Opisuje środowisko uruchomieniowe współbieżności, które upraszczają programowanie równoległe i zawiera linki do powiązanych tematów.
