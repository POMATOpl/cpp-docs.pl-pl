---
description: 'Dowiedz się więcej o: D. Klauzula Schedule'
title: D. Klauzula schedule
ms.date: 01/22/2019
ms.assetid: bf3d8f51-ea05-4803-bf55-657c12e91efe
ms.openlocfilehash: bd1bb4f9a6c661205e2e647fc9e45d81903008c8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342494"
---
# <a name="d-the-schedule-clause"></a>D. Klauzula schedule

Równoległy region ma co najmniej jedną barierę i może mieć dodatkowe bariery. W każdej barierie inni członkowie zespołu muszą oczekiwać na nadejście ostatniego wątku. Aby zminimalizować czas oczekiwania, współdzielonej pracy należy rozłożyć, tak aby wszystkie wątki docierali w tym samym czasie. Jeśli niektóre z tej udostępnionej pracy są zawarte w `for` konstrukcjach, w `schedule` tym celu można użyć klauzuli.

Jeśli istnieją powtarzające się odwołania do tych samych obiektów, wybór harmonogramu dla `for` konstrukcji może być określony głównie przez charakterystykę systemu pamięci, na przykład obecność i rozmiar pamięci podręcznych oraz czy czasy dostępu do pamięci są jednorodne czy niejednorodne. Takie zagadnienia mogą sprawić, że każdy wątek będzie spójnie odwoływać się do tego samego zestawu elementów tablicy w szeregu pętli, nawet jeśli niektóre wątki są przydzielone stosunkowo mniej pracy w niektórych pętlach. Tę konfigurację można wykonać przy użyciu `static` harmonogramu z tymi samymi ograniczeniami dla wszystkich pętli. W poniższym przykładzie wartość zero jest używana jako Dolna granica w drugiej pętli, nawet `k` Jeśli nie jest to ważne.

```cpp
#pragma omp parallel
{
#pragma omp for schedule(static)
  for(i=0; i<n; i++)
    a[i] = work1(i);
#pragma omp for schedule(static)
  for(i=0; i<n; i++)
    if(i>=k) a[i] += work2(i);
}
```

W pozostałych przykładach przyjęto założenie, że dostęp do pamięci nie jest dominującą kwestią. O ile nie określono inaczej, wszystkie wątki odbierają porównywalne zasoby obliczeniowe. W takich przypadkach wybór harmonogramu dla `for` konstrukcji zależy od całej udostępnionej pracy, która ma zostać wykonana między najbliższą poprzednią barierą a implikowaną zamykaną barierą lub najbliższą przyszłej bariery, jeśli istnieje `nowait` klauzula. Dla każdego rodzaju harmonogramu krótki przykład pokazuje, jak ten rodzaj harmonogramu może być najlepszym wyborem. Poniżej przedstawiono krótkie omówienie.

`static`Harmonogram jest również odpowiedni dla najprostszego przypadku, regionu równoległego zawierającego jedną `for` konstrukcję, przy każdej iteracji wymagającej tej samej ilości pracy.

```cpp
#pragma omp parallel for schedule(static)
for(i=0; i<n; i++) {
  invariant_amount_of_work(i);
}
```

`static`Harmonogram jest określany przez właściwości, które każdy wątek uzyskuje około tej samej liczby iteracji co inny wątek, a każdy wątek może niezależnie określić przypisane do niej iteracje. Z tego względu synchronizacja nie jest wymagana do dystrybucji pracy, a w przypadku założenia, że każda iteracja wymaga takiej samej ilości pracy, wszystkie wątki powinny zakończyć się w tym samym czasie.

W przypadku zespołu wątków *p* *pułap (n/p)* jest liczbą całkowitą *q*, która spełnia wymagania *n = p \* q-r* z *0 <= r < p*. Jedną z implementacji `static` harmonogramu tego przykładu jest przypisanie iteracji *q* do pierwszych wątków *p-1* i iteracji *q-r* do ostatniego wątku.  Inna akceptowalna implementacja spowoduje przypisanie iteracji *q* do pierwszych wątków *p-r* i iteracji *q-1* do pozostałych wątków *r* . Ten przykład ilustruje, dlaczego program nie powinien opierać się na szczegółach określonego wdrożenia.

`dynamic`Harmonogram jest odpowiedni dla przypadku `for` konstrukcji z iteracjami wymagającymi różnych lub nawet nieprzewidywalnych ilości pracy.

```cpp
#pragma omp parallel for schedule(dynamic)
  for(i=0; i<n; i++) {
    unpredictable_amount_of_work(i);
}
```

`dynamic`Harmonogram jest scharakteryzowany przez właściwość, która nie czeka na wątek dłużej niż przybiera kolejne wątki, aby wykonać ostateczną iterację. To wymaganie oznacza, że iteracje muszą być przypisane pojedynczo do wątków, gdy staną się dostępne, z synchronizacją dla każdego przydziału. Narzuty synchronizacji można zmniejszyć, określając minimalny rozmiar fragmentu *k* większy niż 1, dzięki czemu wątki *są przypisywane w danym momencie do* momentu pozostawania mniej niż *k* . Gwarantuje to, że żaden wątek nie czeka na barierę dłużej niż przybiera kolejny wątek do wykonania końcowego fragmentu ( *maksymalnie) iteracji* .

`dynamic`Harmonogram może być przydatny, jeśli wątki odbierają różne zasoby obliczeniowe, które znacznie wpływają na różne ilości pracy dla każdej iteracji. Podobnie harmonogram dynamiczny może być również przydatny, jeśli wątki docierają do `for` konstrukcji w różnym czasie, chociaż w niektórych z tych przypadków `guided` harmonogram może być preferowany.

`guided`Harmonogram jest odpowiedni dla sytuacji, w której wątki mogą dotrzeć w różnych porach w `for` konstrukcji, z których każda iteracja wymaga tego samego nakładu pracy. Taka sytuacja może wystąpić, jeśli na przykład `for` konstrukcja jest poprzedzona jedną lub więcej sekcjami lub `for` konstrukcjami z `nowait` klauzulami.

```cpp
#pragma omp parallel
{
  #pragma omp sections nowait
  {
    // ...
  }
  #pragma omp for schedule(guided)
  for(i=0; i<n; i++) {
    invariant_amount_of_work(i);
  }
}
```

`dynamic`Zgodnie z `guided` harmonogramem program gwarantuje, że żaden wątek nie czeka na przeszkodę dłużej niż przybiera Następny wątek, aby wykonać ostateczną  iterację, lub ostateczną liczbę iteracji w przypadku określenia rozmiaru fragmentu *k* . W ramach tych harmonogramów `guided` harmonogram jest scharakteryzowany przez właściwość, która wymaga najmniejszej liczby synchronizacji. Dla rozmiaru fragmentu *k*, typowa implementacja spowoduje przypisanie iteracji *q = pułap (n/p)* do pierwszego dostępnego wątku, ustawienie *n* do większej liczby *n-q* i *p \* k* i powtarzanie do momentu przypisania wszystkich iteracji.

Jeśli wybór optymalnego harmonogramu nie jest tak jasny jak w przypadku tych przykładów, `runtime` harmonogram jest wygodny do eksperymentowania z różnymi harmonogramami i rozmiarami fragmentów bez konieczności modyfikowania i ponownego kompilowania programu. Może być również przydatne, gdy optymalny harmonogram zależy od (w niektórych przewidywalny sposób) danych wejściowych, do których program jest stosowany.

Aby wyświetlić przykładowy kompromis między różnymi harmonogramami, należy rozważyć udostępnienie 1000 iteracji między osiem wątków. Załóżmy, że w każdej iteracji istnieje niezmienna ilość pracy, i użyjesz jej jako jednostki czasu.

Jeśli wszystkie wątki zaczynają się w tym samym czasie, `static` harmonogram spowoduje wykonanie konstruowania w 125 jednostkach bez synchronizacji. Jednak Przypuśćmy, że jeden wątek jest 100 jednostek do osiągnięcia. Następnie pozostałe siedem wątków czeka na 100 jednostek w ramach bariery, a czas wykonywania dla całej konstrukcji wzrosną do 225.

Ponieważ `dynamic` harmonogramy i zapewniają, `guided` że żaden wątek nie czeka na więcej niż jedną jednostkę w ramach bariery, opóźniony wątek powoduje, że czasy wykonywania konstrukcji zwiększają się tylko do 138 jednostek, które prawdopodobnie wzrosły przez opóźnienia synchronizacji. Jeśli takie opóźnienia nie są znikome, ważne jest, aby liczba synchronizacji była 1000 dla `dynamic` , ale tylko 41 dla `guided` , przy założeniu, że domyślny rozmiar fragmentu to 1. O rozmiarze fragmentu 25 `dynamic` i `guided` obu końcach w 150 jednostkach oraz wszelkich opóźnień od wymaganych synchronizacji, które są teraz odpowiednio liczbowe 40 i 20.
