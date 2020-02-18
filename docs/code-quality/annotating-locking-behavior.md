---
title: Dodawanie adnotacji do zachowania blokującego
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- _Releases_nonreentrant_lock_
- _Lock_kind_mutex_
- _Lock_kind_critical_section_
- _Acquires_lock_
- _Releases_lock_
- _Has_lock_kind_
- _Releases_exclusive_lock_
- _Post_same_lock_
- _Requires_exclusive_lock_held_
- _Requires_shared_lock_held_
- _Lock_kind_semaphore_
- _Requires_lock_held_
- _Acquires_exclusive_lock_
- _Create_lock_level_
- _Acquires_nonreentrant_lock_
- _Releases_shared_lock_
- _Has_lock_level_
- _Lock_kind_spin_lock_
- _Requires_lock_not_held_
- _Acquires_shared_lock_
- _Requires_no_locks_held_
- _Lock_level_order_
- _Lock_kind_event_
ms.assetid: 07769c25-9b97-4ab7-b175-d1c450308d7a
ms.openlocfilehash: 8966d982b7bcbe9844a7bf1ec3088c2a9424b23a
ms.sourcegitcommit: 7bea0420d0e476287641edeb33a9d5689a98cb98
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2020
ms.locfileid: "77418642"
---
# <a name="annotating-locking-behavior"></a>Dodawanie adnotacji do zachowania blokującego

Aby uniknąć błędów współbieżności w programie wielowątkowym, zawsze postępuj zgodnie z odpowiednią dyscypliną blokowania i korzystaj z adnotacji SAL.

Błędy współbieżności są wielowątkowy bardzo trudne do odtworzenia, zdiagnozowania i debugowania, ponieważ nie są deterministyczne. Powodowanie odchodzenia między wątkami jest trudne i niepraktyczne, gdy projektujesz treść kodu, który ma więcej niż kilka wątków. W związku z tym dobrym sposobem jest przestrzeganie dyscypliny blokowania w programach wielowątkowych. Na przykład przestrzeganie kolejności blokowania podczas uzyskiwania wielu blokad pozwala uniknąć zakleszczenii i uzyskać właściwą blokadę ochrony przed uzyskaniem dostępu do udostępnionego zasobu, a tym samym zapobiegać sytuacjom wyścigu.

Niestety, pozornie proste reguły blokowania mogą być Surprisingly trudne do przestrzegania w ćwiczeniach. Podstawowe ograniczenie w dzisiejszych językach programowania i kompilatory polega na tym, że nie obsługują one bezpośrednio specyfikacji i analizy wymagań współbieżności. Programiści muszą polegać na nieformalnych komentarzach do kodu, aby wyrazić swoje zamiary, w jaki sposób używają blokad.

Adnotacje SAL concurrency są przeznaczone do określania blokowania efektów ubocznych, odpowiedzialności za blokowanie, ochrony danych, hierarchii kolejności blokady i inne oczekiwane zachowanie blokad. Dzięki wykorzystaniu jawnych zasad jawne adnotacje współbieżności SAL zapewniają spójny sposób dokumentowania sposobu używania reguł blokowania. Adnotacje współbieżności również rozszerzają możliwości narzędzi analizy kodu, aby znaleźć sytuacje, zakleszczenia, niezgodne operacje synchronizacji i inne błędy współbieżności.

## <a name="general-guidelines"></a>Ogólne wskazówki

Korzystając z adnotacji, można określać kontrakty, które są implikowane przez definicje funkcji między implementacjami (wywoływane) i klientami (wywołującymi), a także nieznacznymi i innymi właściwościami programu, które mogą dodatkowo poprawić analizę.

SAL obsługuje wiele różnych rodzajów blokowania elementów pierwotnych — na przykład sekcje krytyczne, muteksy, blokady i inne obiekty zasobów. Wiele adnotacji współbieżności przyjmuje wyrażenie blokady jako parametr. Zgodnie z Konwencją blokada jest wskazywana przez wyrażenie Path powiązanego obiektu blokady.

Niektóre reguły własności wątków, o których należy pamiętać:

- Blokady pokrętła są nielicznymi blokadami, które mają czysty własność wątku.

- Muteksy i sekcje krytyczne są wyliczanymi blokadami, które mają czysty własności wątku.

- Semafory i zdarzenia są wyliczanymi blokadami, które nie mają czystego własności wątku.

## <a name="locking-annotations"></a>Blokowanie adnotacji

Poniższa tabela zawiera listę adnotacji blokowania.

|Adnotacja|Opis|
|----------------|-----------------|
|`_Acquires_exclusive_lock_(expr)`|Adnotuj funkcję i wskazuje, że w stanie post funkcja jest zwiększana o jedną z wyłącznej blokady obiektu blokady o nazwie przez `expr`.|
|`_Acquires_lock_(expr)`|Adnotuj funkcję i wskazuje, że w stanie post funkcja zwiększa się o jedną liczbę blokad obiektu blokady o nazwie przez `expr`.|
|`_Acquires_nonreentrant_lock_(expr)`|Zostanie uzyskana blokada o nazwie `expr`.  Gdy blokada jest już utrzymywana, zgłaszany jest błąd.|
|`_Acquires_shared_lock_(expr)`|Adnotuj funkcję i wskazuje, że w stanie post funkcja zwiększa się o jedną współdzieloną liczbę blokad obiektu blokady, który jest nazwany przez `expr`.|
|`_Create_lock_level_(name)`|Instrukcja, która deklaruje symbol `name` być poziomem blokady, aby mogła być używana w `_Has_Lock_level_` adnotacji i `_Lock_level_order_`.|
|`_Has_lock_kind_(kind)`|Adnotuj każdy obiekt, aby uściślić informacje o typie obiektu zasobu. Czasami typowy typ jest używany dla różnych rodzajów zasobów i przeciążony typ nie jest wystarczający do odróżnienia wymagań semantycznych między różnymi zasobami. Poniżej znajduje się lista wstępnie zdefiniowanych parametrów `kind`:<br /><br /> `_Lock_kind_mutex_`<br /> Identyfikator typu blokady dla muteksów.<br /><br /> `_Lock_kind_event_`<br /> Identyfikator rodzaju blokady dla zdarzeń.<br /><br /> `_Lock_kind_semaphore_`<br /> Identyfikator rodzaju blokady dla semaforów.<br /><br /> `_Lock_kind_spin_lock_`<br /> Identyfikator typu blokady dla blokad pokrętła.<br /><br /> `_Lock_kind_critical_section_`<br /> Identyfikator rodzaju blokady dla sekcji krytycznych.|
|`_Has_lock_level_(name)`|Adnotuj obiekt blokady i nadaje mu poziom blokady `name`.|
|`_Lock_level_order_(name1, name2)`|Instrukcja, która zapewnia kolejność blokowania między `name1` i `name2`.  Blokady, które mają `name1` poziomu muszą zostać pobrane przed blokadami, które mają `name2`poziomu.|
|`_Post_same_lock_(expr1, expr2)`|Adnotuj funkcję i wskazuje, że w stanie post dwa blokady, `expr1` i `expr2`, są traktowane tak, jakby były tym samym obiektem blokady.|
|`_Releases_exclusive_lock_(expr)`|Umożliwia dodawanie adnotacji do funkcji i wskazuje, że w stanie post funkcja zmniejsza się o jedną liczbę blokad na wyłączność obiektu blokady o nazwie `expr`.|
|`_Releases_lock_(expr)`|Adnotuj funkcję i wskazuje, że w stanie post funkcja zmniejsza się o jedną liczbę blokad obiektu blokady o nazwie przez `expr`.|
|`_Releases_nonreentrant_lock_(expr)`|Zostanie wydaną blokadę o nazwie `expr`. Jeśli blokada nie jest obecnie utrzymywana, zgłaszany jest błąd.|
|`_Releases_shared_lock_(expr)`|Adnotuj funkcję i wskazuje, że w stanie post funkcja zmniejsza się o jedną współdzieloną liczbę blokad obiektu blokady, który jest nazwany przez `expr`.|
|`_Requires_lock_held_(expr)`|Adnotuj funkcję i wskazuje, że w wstępnym stanie liczba blokad obiektu, który jest nazwany przez `expr` jest co najmniej jeden.|
|`_Requires_lock_not_held_(expr)`|Adnotuj funkcję i wskazuje, że w wstępnym stanie liczba blokad obiektu o nazwie `expr` wynosi zero.|
|`_Requires_no_locks_held_`|Adnotuj funkcję i wskazuje, że liczba blokad wszystkich blokad, które są znane do sprawdzania, wynosi zero.|
|`_Requires_shared_lock_held_(expr)`|Adnotuj funkcję i wskazuje, że w wstępnej liczbie współużytkowanej liczby blokad obiektu o nazwie `expr` jest co najmniej jeden.|
|`_Requires_exclusive_lock_held_(expr)`|Umożliwia dodawanie adnotacji do funkcji i wskazuje, że w wstępnej liczbie niewyłącznej blokady obiektu o nazwie `expr` jest co najmniej jeden.|

## <a name="sal-intrinsics-for-unexposed-locking-objects"></a>Elementy wewnętrzne SAL dla nieuwidocznionych obiektów blokowania

Niektóre obiekty blokady nie są uwidaczniane przez implementację skojarzonych funkcji blokowania.  Poniższa tabela zawiera listę zmiennych wewnętrznych SAL, które umożliwiają adnotację w funkcjach, które działają w odniesieniu do nieuwidocznionych obiektów blokady.

|Adnotacja|Opis|
|----------------|-----------------|
|`_Global_cancel_spin_lock_`|Opisuje blokadę anulowania.|
|`_Global_critical_region_`|Opisuje region krytyczny.|
|`_Global_interlock_`|Opisuje operacje, które są blokowane.|
|`_Global_priority_region_`|Opisuje region priorytetu.|

## <a name="shared-data-access-annotations"></a>Adnotacje dostępu do danych udostępnionych

W poniższej tabeli wymieniono adnotacje dotyczące dostępu do danych udostępnionych.

|Adnotacja|Opis|
|----------------|-----------------|
|`_Guarded_by_(expr)`|Adnotuj zmienną i wskazuje, że za każdym razem, gdy uzyskuje się dostęp do zmiennej, liczba blokad obiektu blokady o nazwie `expr` jest równa co najmniej jeden.|
|`_Interlocked_`|Adnotuj zmienną i jest równoważne `_Guarded_by_(_Global_interlock_)`.|
|`_Interlocked_operand_`|Parametr funkcji z adnotacjami jest docelowym argumentem operacji jednej z różnych funkcji zablokowanych.  Te operandy muszą mieć określone dodatkowe właściwości.|
|`_Write_guarded_by_(expr)`|Adnotuj zmienną i wskazuje, że za każdym razem, gdy zmienna jest modyfikowana, liczba blokad obiektu blokady o nazwie `expr` jest równa co najmniej jeden.|

## <a name="smart-lock-and-raii-annotations"></a>Smart Lock i adnotacje RAII

Inteligentne blokady zwykle zawijają natywne blokady i zarządzają ich okresem istnienia. W poniższej tabeli wymieniono adnotacje, które mogą być używane z inteligentnymi blokadami i wzorcami kodowania RAII z obsługą semantyki `move`.

|Adnotacja|Opis|
|----------------|-----------------|
|`_Analysis_assume_smart_lock_acquired_`|Informuje Analizator, aby założyć, że inteligentna Blokada została pobrana. Ta adnotacja oczekuje typu blokady odwołania jako parametru.|
|`_Analysis_assume_smart_lock_released_`|Nakazuje analizatorowi założenie, że inteligentna Blokada została wydana. Ta adnotacja oczekuje typu blokady odwołania jako parametru.|
|`_Moves_lock_(target, source)`|Opisuje `move constructor` operacji, która przenosi stan blokady z obiektu `source` do `target`. `target` jest traktowany jako nowo skonstruowany obiekt, dlatego każdy stanie musiał przed utratą i został zastąpiony przez stan `source`. `source` jest również resetowany do stanu czystego bez liczby blokad ani obiektu docelowego aliasu, ale aliasy wskazujące, pozostaną bez zmian.|
|`_Replaces_lock_(target, source)`|Opisuje semantykę `move assignment operator`, w której wydano blokadę docelową przed przeniesieniem stanu ze źródła. Można to traktować jako kombinację `_Moves_lock_(target, source)` poprzedzonej `_Releases_lock_(target)`.|
|`_Swaps_locks_(left, right)`|Opisuje standardowe zachowanie `swap`, które zakłada, że obiekty `left` i `right` wymianę ich stanu. Wymieniany stan obejmuje liczbę blokad i obiekt docelowy aliasu, jeśli jest obecny. Aliasy wskazujące `left` i obiekty `right` pozostaną niezmienione.|
|`_Detaches_lock_(detached, lock)`|Opisuje scenariusz, w którym typ otoki blokady zezwala na skojarzenie z zawartym w nim zasobem. Jest to podobne do sposobu, w jaki `std::unique_ptr` współpracuje ze swoim wskaźnikiem wewnętrznym: umożliwia programistom wyodrębnienie wskaźnika i pozostawienie jego kontenera inteligentnego wskaźnika w stanie czystym. Podobna logika jest obsługiwana przez `std::unique_lock` i może być implementowana w niestandardowych otokach blokady. Odłączona blokada zachowuje swój stan (liczba zablokowanych i obiekt docelowy aliasu, jeśli istnieje), podczas gdy otoka jest resetowana, aby zawierała liczbę blokad równą zero i bez obiektu docelowego aliasu, zachowując własne aliasy. Nie ma operacji dotyczących liczby blokad (zwalniania i pozyskiwania). Ta adnotacja zachowuje się dokładnie tak, jak `_Moves_lock_`, z tą różnicą, że odłączony argument powinien być `return`, a nie `this`.|

## <a name="see-also"></a>Zobacz też

- [Korzystanie z adnotacji SAL w celu zmniejszenia liczby defektów kodu C/C++](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)
- [Informacje o języku SAL](../code-quality/understanding-sal.md)
- [Dodawanie adnotacji do parametrów funkcji i zwracanych wartości](../code-quality/annotating-function-parameters-and-return-values.md)
- [Zachowanie funkcji dodawania adnotacji](../code-quality/annotating-function-behavior.md)
- [Dodawanie adnotacji do struktur i klas](../code-quality/annotating-structs-and-classes.md)
- [Określanie miejsca i warunków stosowania adnotacji](../code-quality/specifying-when-and-where-an-annotation-applies.md)
- [Funkcje wewnętrzne](../code-quality/intrinsic-functions.md)
- [Najlepsze rozwiązania i przykłady](../code-quality/best-practices-and-examples-sal.md)
- [Blog zespołu ds. analizy kodu](https://blogs.msdn.microsoft.com/codeanalysis/)
