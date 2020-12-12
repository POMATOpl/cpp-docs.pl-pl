---
description: 'Dowiedz się więcej o: agenci asynchroniczni'
title: Agenci asynchroniczni
ms.date: 11/19/2018
helpviewer_keywords:
- asynchronous agents
- agents [Concurrency Runtime]
ms.assetid: 6cf6ccc6-87f1-4e14-af15-ea8ba58fef1a
ms.openlocfilehash: 38d2325404d83443ed0bd054793ca200a562359f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338293"
---
# <a name="asynchronous-agents"></a>Agenci asynchroniczni

*Agent asynchroniczny* (lub tylko *Agent*) to składnik aplikacji, który działa asynchronicznie z innymi agentami w celu rozwiązywania większych zadań obliczeniowych. Należy traktować agenta jako zadanie, które ma ustawiony cykl życia. Na przykład jeden Agent może odczytywać dane z urządzenia wejściowego/wyjściowego (takiego jak klawiatura, plik na dysku lub połączenie sieciowe), a inny agent może wykonać akcję na tych danych, gdy staną się dostępne. Pierwszy Agent korzysta z przekazywania komunikatów w celu informowania drugiego agenta o dostępności większej ilości danych. Harmonogram zadań środowisko uruchomieniowe współbieżności zapewnia wydajny mechanizm umożliwiający agentom zablokowanie i uzyskanie sprawności w zakresie współpracy bez konieczności przeprowadzenia mniejszego poziomu zastępujący.

Biblioteka agentów definiuje klasę [concurrency:: Agent](../../parallel/concrt/reference/agent-class.md) do reprezentowania agenta asynchronicznego. `agent` jest klasą abstrakcyjną, która deklaruje metodę wirtualną [concurrency:: Agent:: Run](reference/agent-class.md#run). `run`Metoda wykonuje zadanie wykonywane przez agenta. Ponieważ `run` jest abstrakcyjna, należy zaimplementować tę metodę w każdej klasie, z której pochodzą `agent` .

## <a name="agent-life-cycle"></a>Cykl życia agenta

Agenci mają ustawiony cykl życia. Wyliczenie [concurrency:: agent_status](reference/concurrency-namespace-enums.md#agent_status) definiuje różne stany agenta. Poniższa ilustracja przedstawia Diagram stanu, który pokazuje, jak agenci postępują z jednego stanu do drugiego. Na tej ilustracji pełny wiersz reprezentuje metody, które są wywoływane z aplikacji; linie kropkowane reprezentują metody, które są wywoływane z środowiska uruchomieniowego.

![Diagram stanu agenta](../../parallel/concrt/media/agentstate.png "Diagram stanu agenta")

W poniższej tabeli opisano każdy stan w `agent_status` wyliczeniu.

|Stan agenta|Opis|
|-----------------|-----------------|
|`agent_created`|Nie zaplanowano wykonania agenta.|
|`agent_runnable`|Środowisko uruchomieniowe planuje wykonanie.|
|`agent_started`|Agent został uruchomiony i jest uruchomiony.|
|`agent_done`|Agent został ukończony.|
|`agent_canceled`|Agent został anulowany przed wprowadzeniem `started` stanu.|

`agent_created` jest początkowym stanem agenta `agent_runnable` i są stanami `agent_started` aktywnymi, a `agent_done` i `agent_canceled` są stanami końcowymi.

Użyj metody [concurrency:: Agent:: status](reference/agent-class.md#status) , aby pobrać bieżący stan `agent` obiektu. Mimo że `status` Metoda jest bezpieczna pod kątem współbieżności, stan agenta może ulec zmianie przez moment, gdy `status` Metoda zwraca. Na przykład Agent może być w `agent_started` stanie w momencie wywołania `status` metody, ale jest przenoszony do `agent_done` stanu tuż po `status` powrocie metody.

## <a name="methods-and-features"></a>Metody i funkcje

W poniższej tabeli przedstawiono niektóre ważne metody należące do `agent` klasy. Aby uzyskać więcej informacji na temat wszystkich `agent` metod klasy, zobacz [Klasa agenta](../../parallel/concrt/reference/agent-class.md).

|Metoda|Opis|
|------------|-----------------|
|[Start](reference/agent-class.md#start)|Planuje `agent` wykonanie obiektu i ustawia go na `agent_runnable` stan.|
|[wykonane](reference/agent-class.md#run)|Wykonuje zadanie, które ma zostać wykonane przez `agent` obiekt.|
|[gotowe](reference/agent-class.md#done)|Przenosi agenta do `agent_done` stanu.|
|[Anuluj](../../parallel/concrt/cancellation-in-the-ppl.md#cancel)|Jeśli Agent nie został uruchomiony, ta metoda anuluje wykonywanie agenta i ustawia go na `agent_canceled` stan.|
|[Stany](reference/agent-class.md#status)|Pobiera bieżący stan `agent` obiektu.|
|[trwa](reference/agent-class.md#wait)|Czeka, aż `agent` obiekt wprowadzi wartość `agent_done` lub `agent_canceled` .|
|[wait_for_all](reference/agent-class.md#wait_for_all)|Czeka, aż wszystkie podane `agent` obiekty `agent_done` `agent_canceled` przestaną lub.|
|[wait_for_one](reference/agent-class.md#wait_for_one)|Czeka na co najmniej jeden z podanych `agent` obiektów, aby wprowadzić `agent_done` `agent_canceled` stan lub.|

Po utworzeniu obiektu agenta Wywołaj metodę [concurrency:: Agent:: Start](reference/agent-class.md#start) , aby zaplanować jej wykonanie. Środowisko uruchomieniowe wywołuje `run` metodę po zaplanowanym agencie i ustawi ją na `agent_runnable` stan.

Środowisko uruchomieniowe nie zarządza wyjątkami zgłoszonymi przez agentów asynchronicznych. Aby uzyskać więcej informacji na temat obsługi wyjątków i agentów, zobacz [Obsługa wyjątków](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).

## <a name="example"></a>Przykład

Aby zapoznać się z przykładem, który pokazuje, jak utworzyć podstawową aplikację opartą na agencie, zobacz [Przewodnik: Tworzenie aplikacji Agent-Based](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md).

## <a name="see-also"></a>Zobacz też

[Biblioteki agentów asynchronicznych](../../parallel/concrt/asynchronous-agents-library.md)
