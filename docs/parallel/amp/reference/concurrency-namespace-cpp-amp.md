---
description: 'Dowiedz się więcej o: przestrzeni nazw współbieżności (C++ AMP)'
title: Przestrzeń nazw współbieżności (C++ AMP)
ms.date: 11/04/2016
f1_keywords:
- AMP/Concurrency
helpviewer_keywords:
- Concurrency namespace
ms.assetid: b5aab265-3bac-42c5-8ead-f92ce05ef267
ms.openlocfilehash: 9334634dc3d332b24f067c04f00e82feea5a6001
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342585"
---
# <a name="concurrency-namespace-c-amp"></a>Przestrzeń nazw współbieżności (C++ AMP)

Dostarcza klasy i funkcje, które przyspieszają wykonywanie kodu C++ na urządzeniach równoległych danych. Aby uzyskać więcej informacji, zobacz [C++ amp przegląd](../cpp-amp-overview.md)

## <a name="syntax"></a>Składnia

```cpp
namespace Concurrency;
```

## <a name="members"></a>Elementy członkowskie

### <a name="namespaces"></a>Przestrzenie nazw

|Nazwa|Opis|
|----------|-----------------|
|[Concurrency::direct3d — Przestrzeń nazw](concurrency-direct3d-namespace.md)|Udostępnia funkcje, które obsługują współdziałanie D3D. Pozwala bezproblemowo korzystać z zasobów D3D do obliczeń w kodzie AMP i używania zasobów utworzonych w AMP w kodzie D3D, bez tworzenia nadmiarowych kopii pośrednich. Za pomocą C++ AMP można stopniowo przyspieszyć sekcje aplikacji DirectX intensywnie korzystających z mocy obliczeniowej i korzystać z interfejsu API D3D na danych wyprodukowanych z obliczeń AMP.|
|[Concurrency::fast_math — Przestrzeń nazw](concurrency-fast-math-namespace.md)|Funkcje w `fast_math` przestrzeni nazw nie są zgodne z C99. Udostępniane są tylko wersje o pojedynczej precyzji każdej funkcji. Te funkcje korzystają z funkcji wewnętrznych DirectX, które są szybsze niż odpowiednie funkcje w `precise_math` przestrzeni nazw i nie wymagają rozszerzonej podwójnej precyzji wsparcia dla akceleratora, ale są mniej dokładne. Istnieją dwie wersje każdej funkcji dla zgodności na poziomie źródła z kodem C99; Obie wersje pobierają i zwracają wartości pojedynczej precyzji.|
|[Concurrency::graphics — Przestrzeń nazw](concurrency-graphics-namespace.md)|Zawiera typy i funkcje, które są przeznaczone do programowania grafiki.|
|[Współbieżność::p recise_math przestrzeni nazw](concurrency-precise-math-namespace.md)|Funkcje w `precise_math` przestrzeni nazw są zgodne z C99. Dostępne są zarówno wersje o pojedynczej precyzji, jak i podwójnej precyzji każdej funkcji. Te funkcje — obejmuje funkcje o pojedynczej precyzji — wymagają rozszerzonej obsługi podwójnej precyzji dla akceleratora.|

### <a name="classes"></a>Klasy

|Nazwa|Opis|
|----------|-----------------|
|[Accelerator — Klasa](accelerator-class.md)|Reprezentuje abstrakcję fizycznego węzła obliczeniowego zoptymalizowanego pod kątem DP.|
|[Klasa accelerator_view](accelerator-view-class.md)|Reprezentuje abstrakcję urządzenia wirtualnego na C++ AMP akceleratora równoległego danych.|
|[Klasa accelerator_view_removed](accelerator-view-removed-class.md)|Wyjątek, który jest generowany, gdy bazowe wywołanie programu DirectX nie powiedzie się z powodu przekroczenia limitu czasu systemu Windows — wykrywania i odzyskiwania.|
|[Array — Klasa](array-class.md)|Agregacja danych w `accelerator_view` domenie siatki. Jest to zbiór zmiennych, po jednym dla każdego elementu w domenie siatki. Każda zmienna przechowuje wartość odpowiadającą typowi języka C++.|
|[Klasa array_view](array-view-class.md)|Reprezentuje widok danych w tablicy \<T,N> .|
|[Klasa completion_future](completion-future-class.md)|Reprezentuje przyszłość, która odnosi się do C++ AMP operacji asynchronicznej.|
|[Klasa zakresu](extent-class.md)|Reprezentuje wektora N wartości całkowitych, które określają granice przestrzeni N-wymiarowej, która ma początek 0. Wartości w wektorze współrzędnych są uporządkowane od najbardziej do najmniej znaczących. Na przykład w kartezjańskiego trójwymiarowej przestrzeni wektor zakresu (7, 5, 3) reprezentuje miejsce, w którym Współrzędna z przedziału od 0 do 7, Współrzędna y z zakresu od 0 do 5, a Współrzędna x z przedziału od 0 do 3.|
|[index — Klasa](index-class.md)|Definiuje N-wymiarowy punkt indeksu.|
|[Klasa invalid_compute_domain](invalid-compute-domain-class.md)|Wyjątek, który jest generowany, gdy środowisko uruchomieniowe nie może uruchomić jądra przy użyciu domeny obliczeniowej określonej w `parallel_for_each` witrynie wywołania.|
|[Klasa out_of_memory](out-of-memory-class.md)|Wyjątek, który jest generowany, gdy metoda nie powiedzie się z powodu braku pamięci systemowej lub urządzenia.|
|[Klasa runtime_exception](runtime-exception-class.md)|Typ podstawowy dla wyjątków w bibliotece C++ AMP.|
|[Klasa tile_barrier](tile-barrier-class.md)|Klasa możliwości, która jest tylko do utworzenia przez system i jest przenoszona do sąsiadujących `parallel_for_each` wyrażeń lambda jako część `tiled_index` parametru. Zawiera jedną metodę, `wait()` której celem jest synchronizowanie wykonywania wątków, które są uruchomione w grupie wątków (kafelek).|
|[Klasa tiled_extent](tiled-extent-class.md)|`tiled_extent`Obiekt to `extent` obiekt od jednego do trzech wymiarów, który dzieli miejsce na jednowymiarowe, dwuwymiarowe lub trójwymiarowe kafelki.|
|[Klasa tiled_index](tiled-index-class.md)|Dostarcza indeks do `tiled_grid` obiektu. Ta klasa ma właściwości do uzyskiwania dostępu do elementu względem lokalnego źródła kafelka i względem pierwotnego źródła.|
|[Klasa uninitialized_object](uninitialized-object-class.md)|Wyjątek, który jest generowany, gdy jest używany Niezainicjowany obiekt.|
|[Klasa unsupported_feature](unsupported-feature-class.md)|Wyjątek, który jest generowany w przypadku użycia nieobsługiwanej funkcji.|

### <a name="enumerations"></a>Wyliczenia

|Nazwa|Opis|
|----------|-----------------|
|[access_type, Wyliczenie](concurrency-namespace-enums-amp.md#access_type)|Określa typ dostępu do danych.|
|[queuing_mode, Wyliczenie](concurrency-namespace-enums-amp.md#queuing_mode)|Określa tryby kolejkowania, które są obsługiwane w akceleratorze.|

### <a name="operators"></a>Operatory

|Operator|Opis|
|--------------|-----------------|
|[operator = = — operator (C++ AMP)](concurrency-namespace-operators-amp.md#operator_eq_eq)|Określa, czy określone struktury danych są równe.|
|[operator! = — operator (C++ AMP)](concurrency-namespace-operators-amp.md#operator_neq)|Określa, czy określone struktury danych są nierówne.|
|[operator + — operator (C++ AMP)](concurrency-namespace-operators-amp.md#operator_add)|Oblicza sumę elementów dla określonych argumentów.|
|[operator-(C++ AMP)](concurrency-namespace-operators-amp.md#operator-)|Oblicza różnicę składnika między określonymi argumentami.|
|[operator * (C++ AMP)](concurrency-namespace-operators-amp.md#operator_star)|Oblicza produkt ze składnikami dla określonych argumentów.|
|[operator/— operator (C++ AMP)](concurrency-namespace-operators-amp.md#operator_div)|Oblicza iloraz składnika dla określonych argumentów.|
|[operator% (C++ AMP)](concurrency-namespace-operators-amp.md#operator_mod)|Oblicza moduł pierwszego określonego argumentu przez drugi określony argument.|

### <a name="functions"></a>Funkcje

|Nazwa|Opis|
|----------|-----------------|
|[all_memory_fence](concurrency-namespace-functions-amp.md#all_memory_fence)|Blokuje wykonywanie wszystkich wątków we fragmencie do momentu zakończenia wszystkich operacji dostępu do pamięci.|
|[amp_uninitialize](concurrency-namespace-functions-amp.md#amp_uninitialize)|Umożliwia odinicjowanie środowiska uruchomieniowego C++ AMP.|
|[atomic_compare_exchange](concurrency-namespace-functions-amp.md#atomic_compare_exchange)|Przeciążone. Jeśli wartość przechowywana w określonej lokalizacji jest porównywana równa pierwszej określonej wartości, druga określona wartość jest przechowywana w tej samej lokalizacji co operacja niepodzielna.|
|[atomic_exchange](concurrency-namespace-functions-amp.md#atomic_exchange)|Przeciążone. Ustawia wartość przechowywaną w określonej lokalizacji na określoną wartość jako operację niepodzielną.|
|[atomic_fetch_add](concurrency-namespace-functions-amp.md#atomic_fetch_add)|Przeciążone. Ustawia wartość przechowywaną w określonej lokalizacji na sumę tej wartości i określoną wartość jako operację niepodzielną.|
|[atomic_fetch_and](concurrency-namespace-functions-amp.md#atomic_fetch_and)|Przeciążone. Ustawia wartość przechowywaną w określonej lokalizacji na bitową `and` tej wartości i określoną wartość jako operację niepodzielną.|
|[atomic_fetch_dec](concurrency-namespace-functions-amp.md#atomic_fetch_dec)|Przeciążone. Zmniejsza wartość przechowywaną w określonej lokalizacji i zapisuje wynik w tej samej lokalizacji co operacja niepodzielna.|
|[atomic_fetch_inc](concurrency-namespace-functions-amp.md#atomic_fetch_inc)|Przeciążone. Zwiększa wartość przechowywaną w określonej lokalizacji i zapisuje wynik w tej samej lokalizacji co operacja niepodzielna.|
|[atomic_fetch_max](concurrency-namespace-functions-amp.md#atomic_fetch_max)|Przeciążone. Ustawia wartość przechowywaną w określonej lokalizacji do większej tej wartości i określoną wartość jako operację niepodzielną.|
|[atomic_fetch_min](concurrency-namespace-functions-amp.md#atomic_fetch_min)|Przeciążone. Ustawia wartość przechowywaną w określonej lokalizacji na mniejszą wartość i określoną wartość jako operację niepodzielną.|
|[atomic_fetch_or](concurrency-namespace-functions-amp.md#atomic_fetch_or)|Przeciążone. Ustawia wartość przechowywaną w określonej lokalizacji na bitową `or` tej wartości i określoną wartość jako operację niepodzielną.|
|[atomic_fetch_sub](concurrency-namespace-functions-amp.md#atomic_fetch_sub)|Przeciążone. Ustawia wartość przechowywaną w określonej lokalizacji na różnicę tej wartości i określoną wartość jako operację niepodzielną.|
|[atomic_fetch_xor](concurrency-namespace-functions-amp.md#atomic_fetch_xor)|Przeciążone. Ustawia wartość przechowywaną w określonej lokalizacji na bitową `xor` tej wartości i określoną wartość jako operację niepodzielną.|
|[kopiowane](concurrency-namespace-functions-amp.md#copy)|Kopiuje obiekt C++ AMP. Spełnione są wszystkie wymagania dotyczące synchronicznego transferu danych. Nie można skopiować danych, gdy kod uruchamia kod na akceleratorze. Ogólna forma tej funkcji to `copy(src, dest)` .|
|[copy_async](concurrency-namespace-functions-amp.md#copy_async)|Kopiuje obiekt C++ AMP i zwraca [completion_future](completion-future-class.md) , które mogą być oczekiwane. Nie można skopiować danych, gdy kod jest uruchomiony na akceleratorze. Ogólna forma tej funkcji to `copy(src, dest)` .|
|[direct3d_abort](concurrency-namespace-functions-amp.md#direct3d_abort)|Przerywa wykonywanie funkcji z `restrict(amp)` klauzulą ograniczenia.|
|[direct3d_errorf](concurrency-namespace-functions-amp.md#direct3d_errorf)|Drukuje sformatowany ciąg w oknie **danych wyjściowych** programu Visual Studio i wywołuje [runtime_exception](runtime-exception-class.md) wyjątek, który ma ten sam ciąg formatowania.|
|[direct3d_printf](concurrency-namespace-functions-amp.md#direct3d_printf)|Drukuje sformatowany ciąg w oknie **danych wyjściowych** programu Visual Studio. Jest wywoływana z funkcji, która ma `restrict(amp)` klauzulę ograniczenia.|
|[global_memory_fence](concurrency-namespace-functions-amp.md#global_memory_fence)|Blokuje wykonywanie wszystkich wątków w kafelku do momentu zakończenia wszystkich dostępów do pamięci globalnej.|
|[Funkcja parallel_for_each (C++ AMP)](concurrency-namespace-functions-amp.md#parallel_for_each)|Uruchamia funkcję w całej domenie obliczeniowej.|
|[tile_static_memory_fence](concurrency-namespace-functions-amp.md#tile_static_memory_fence)|Blokuje wykonywanie wszystkich wątków w kafelku do momentu `tile_static` ukończenia dostępu do pamięci.|

## <a name="constants"></a>Stałe

|Nazwa|Opis|
|----------|-----------------|
|[HLSL_MAX_NUM_BUFFERS stała](concurrency-namespace-constants-amp.md#hlsl_max_num_buffers)|Maksymalna liczba buforów dozwolona przez program DirectX.|
|[MODULENAME_MAX_LENGTH stała](concurrency-namespace-constants-amp.md#modulename_max_length)|Przechowuje maksymalną długość nazwy modułu. Ta wartość musi być taka sama w kompilatorze i środowisku uruchomieniowym.|

## <a name="requirements"></a>Wymagania

**Nagłówek:** amp. h

## <a name="see-also"></a>Zobacz też

[Odwołanie (C++ AMP)](reference-cpp-amp.md)
