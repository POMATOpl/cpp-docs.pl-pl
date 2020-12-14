---
description: 'Dowiedz się więcej o: Błędy kompilatora od C2500 przez C2599'
title: Błędy kompilatora — od C2500 do C2599
ms.date: 04/21/2019
f1_keywords:
- C2501
- C2508
- C2515
- C2519
- C2520
- C2522
- C2525
- C2527
- C2536
- C2538
- C2539
- C2546
- C2547
- C2559
- C2560
- C2564
- C2565
- C2576
- C2578
- C2580
- C2590
- C2591
- C2595
- C2596
helpviewer_keywords:
- C2501
- C2508
- C2515
- C2519
- C2520
- C2522
- C2525
- C2527
- C2536
- C2538
- C2539
- C2546
- C2547
- C2559
- C2560
- C2564
- C2565
- C2576
- C2578
- C2580
- C2590
- C2591
- C2595
- C2596
ms.assetid: a869aaed-e9f6-49e3-b273-00ea7f45bed7
ms.openlocfilehash: 36b0b1e0d1abbbd0b3752d275011eb12282aec18
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97238950"
---
# <a name="compiler-errors-c2500-through-c2599"></a>Błędy kompilatora — od C2500 do C2599

W artykułach w tej sekcji dokumentacji wyjaśniono podzestaw komunikatów o błędach generowanych przez kompilator.

[!INCLUDE[error-boilerplate](../../error-messages/includes/error-boilerplate.md)]

## <a name="error-messages"></a>Komunikaty o błędach

|Błąd|Wiadomość|
|-----------|-------------|
|[Błąd kompilatora C2500](compiler-error-C2500.md)|"*Identifier1*": "*identifier2*" jest już bezpośrednią klasą bazową|
|Błąd kompilatora C2501|"*Identyfikator*": "__declspec (*specyfikator*)" można stosować tylko do struktur, Unii, klas lub elementów członkowskich pola bitowego bez znaku|
|[Błąd kompilatora C2502](compiler-error-C2502.md)|"*Identyfikator*": zbyt wiele modyfikatorów dostępu dla klasy bazowej|
|[Błąd kompilatora C2503](compiler-error-C2503.md)|"*Class*": klasy bazowe nie mogą zawierać tablic o rozmiarze zerowym|
|[Błąd kompilatora C2504](compiler-error-C2504.md)|"*Class*": Klasa bazowa nie jest zdefiniowana|
|[Błąd kompilatora C2505](compiler-error-C2505.md)|"*symbol*": "__declspec (*specyfikator*)" można stosować tylko do deklaracji lub definicji obiektów globalnych lub statycznych elementów członkowskich danych|
|[Błąd kompilatora C2506](compiler-error-C2506.md)|*elementu "member*": "__declspec (*specyfikator*)" nie można zastosować do tego symbolu|
|[Błąd kompilatora C2507](compiler-error-C2507.md)|"*Identyfikator*": zbyt wiele modyfikatorów wirtualnych w klasie bazowej|
|Błąd kompilatora C2508|"*Identyfikator*": "__declspec (*specifier1*)" nie można łączyć z elementem "__declspec (*specifier2*)"|
|[Błąd kompilatora C2509](compiler-error-C2509.md)|"*Identyfikator*": funkcja członkowska nie została zadeklarowana w elemencie "*Class*"|
|[Błąd kompilatora C2510](compiler-error-C2510.md)|"*Identyfikator*": po lewej stronie "::" musi być klasą/strukturą/Unią|
|[Błąd kompilatora C2511](compiler-error-C2511.md)|"*Identyfikator*": przeciążona Funkcja składowa nie została znaleziona w "*Class*"|
|[Błąd kompilatora C2512](compiler-error-C2512.md)|"*Identyfikator*": Brak dostępnego odpowiedniego domyślnego konstruktora|
|[Błąd kompilatora C2513](compiler-error-C2513.md)|"* Type": Brak deklaracji zmiennej przed "="|
|[Błąd kompilatora C2514](compiler-error-C2514.md)|"*Class*": Klasa nie ma konstruktorów|
|Błąd kompilatora C2515|"*Identyfikator*": "vtguard" może być stosowany tylko do deklaracji lub definicji klasy|
|[Błąd kompilatora C2516](compiler-error-C2516.md)|"*Class*": nie jest dozwoloną klasą bazową|
|[Błąd kompilatora C2517](compiler-error-C2517.md)|"*Identyfikator*": po prawej ':: ' jest niezdefiniowane|
|[Błąd kompilatora C2518](compiler-error-C2518.md)|słowo kluczowe "*słowo kluczowe*" jest niedozwolone na liście klas bazowych; Ignoruj|
|Błąd kompilatora C2519|"*Identyfikator*": atrybuty WinRT mogą zawierać tylko pola publiczne|
|Błąd kompilatora C2520|"*Class*": brak niejawnego konstruktora dostępnego dla niejawnej konwersji|
|[Błąd kompilatora C2521](compiler-error-C2521.md)|destruktor/finalizator nie przyjmuje żadnych argumentów|
|Błąd kompilatora C2522|"*Identyfikator*": nie można użyć identyfikatora przeciążenia dla elementu "*Identifier1*", ponieważ jest on już określony w "*identifier2*"|
|[Błąd kompilatora C2523](compiler-error-C2523.md)|"*Class*:: ~*Identifier*": niezgodność tagów destruktora/finalizatora|
|[Błąd kompilatora C2524](compiler-error-C2524.md)|"*Identyfikator*": destruktor/finalizator musi mieć listę parametrów "void"|
|Błąd kompilatora C2525|"*Identyfikator*": parametr "*Identifier1*" ma nazwę "*identifier2*" w funkcji bazowej i musi pasować w opublikowanej implementacji|
|[Błąd kompilatora C2526](compiler-error-C2526.md)|"*Identifier1*": funkcja powiązania C nie może zwrócić klasy "*Identifier2*" języka C++|
|Błąd kompilatora C2527|"*Identyfikator*": DefaultOverload nie może być określony zarówno dla "*function1*", jak i "*function2*". Usuń jedną specyfikację lub zmień jej nazwę podczas implementacji|
|[Błąd kompilatora C2528](compiler-error-C2528.md)|"*Identyfikator*": wskaźnik do odwołania jest niedozwolony|
|[Błąd kompilatora C2529](compiler-error-C2529.md)|"*Identyfikator*": odwołanie do odwołania jest niedozwolone|
|[Błąd kompilatora C2530](compiler-error-C2530.md)|"*Identyfikator*": odwołania muszą być zainicjowane|
|[Błąd kompilatora C2531](compiler-error-C2531.md)|"*Identyfikator*": niedozwolone odwołanie do pola bitowego|
|[Błąd kompilatora C2532](compiler-error-C2532.md)|"*Identyfikator*": niedozwolony modyfikator dla odwołania|
|[Błąd kompilatora C2533](compiler-error-C2533.md)|"*Identyfikator*": konstruktory nie mogą być typem zwracanym|
|[Błąd kompilatora C2534](compiler-error-C2534.md)|"*Identyfikator*": Konstruktor nie może zwrócić wartości|
|[Błąd kompilatora C2535](compiler-error-C2535.md)|"*Identyfikator*": Funkcja składowa już zdefiniowana lub zadeklarowana|
|Błąd kompilatora C2536|Nieaktualne.|
|[Błąd kompilatora C2537](compiler-error-C2537.md)|"*specyfikator*": niedozwolona Specyfikacja powiązania|
|Błąd kompilatora C2538|Nieaktualne.|
|Błąd kompilatora C2539|Nieaktualne.|
|[Błąd kompilatora C2540](compiler-error-C2540.md)|wyrażenie nie stałe jako powiązane z tablicą|
|[Błąd kompilatora C2541](compiler-error-C2541.md)|"*Identyfikator*": nie można usunąć obiektów, które nie są wskaźnikami|
|[Błąd kompilatora C2542](compiler-error-C2542.md)|"*Identyfikator*": obiekt klasy nie ma konstruktora do inicjalizacji|
|[Błąd kompilatora C2543](compiler-error-C2543.md)|Oczekiwano znaku "]" dla operatora "[]"|
|[Błąd kompilatora C2544](compiler-error-C2544.md)|Oczekiwano znaku ")" dla operatora "()"|
|[Błąd kompilatora C2545](compiler-error-C2545.md)|"*operator*": nie można odnaleźć przeciążonego operatora|
|Błąd kompilatora C2546|"*Identyfikator*": Kiedy typ jest zdefiniowany zarówno jako Pia, jak i bez Pia, należy najpierw odwołać się do PIA|
|Błąd kompilatora C2547|"*Identyfikator*": wszystkie parametry opublikowanej metody muszą być jawnie nazwane w deklaracji|
|[Błąd kompilatora C2548](compiler-error-C2548.md)|"*Function*": Brak domyślnego parametru dla *parametru* parametru|
|[Błąd kompilatora C2549](compiler-error-C2549.md)|konwersja zdefiniowana przez użytkownika nie może określić zwracanego typu|
|[Błąd kompilatora C2550](compiler-error-C2550.md)|"*Identyfikator*": listy inicjatorów konstruktora są dozwolone tylko w definicjach konstruktorów|
|[Błąd kompilatora C2551](compiler-error-C2551.md)|Typ "void *" wymaga jawnego rzutowania|
|[Błąd kompilatora C2552](compiler-error-C2552.md)|"*Identyfikator*": nie można zainicjować wartości niezagregowanych za pomocą listy inicjalizatora|
|[Błąd kompilatora C2553](compiler-error-C2553.md)|"*type* *derived_class*::*Function*": przesłanianie typu zwracanego funkcji wirtualnej różni się od typu "*Type* *BASE_CLASS*::*Function*"|
|[Błąd kompilatora C2555](compiler-error-C2555.md)|"*derived_class*::*Function*": przesłanianie typu zwracanego funkcji wirtualnej różni się i nie jest współwariantem z elementu "*BASE_CLASS*::*Function*"|
|[Błąd kompilatora C2556](compiler-error-C2556.md)|"*Type1* *Class*::*Function*": przeciążona funkcja różni się tylko typem zwracanym z "*Type2* *Class*::*Function*"|
|[Błąd kompilatora C2557](compiler-error-C2557.md)|"*Identyfikator*": prywatnych i chronionych składowych nie można zainicjować bez konstruktora|
|[Błąd kompilatora C2558](compiler-error-C2558.md)|Klasa "*Class*": Brak dostępnego konstruktora kopiującego lub Konstruktor kopiujący jest zadeklarowany jako "Explicit"|
|Błąd kompilatora C2559|"*Identyfikator*": nie można przeciążyć funkcji składowej bez kwalifikatora ref funkcją członkowską z kwalifikatorem ref|
|Błąd kompilatora C2560|"*Identyfikator*": nie można przeciążyć funkcji składowej z kwalifikatorem ref funkcją składową bez kwalifikatora ref|
|[Błąd kompilatora C2561](compiler-error-C2561.md)|"*Function*": funkcja musi zwracać wartość|
|[Błąd kompilatora C2562](compiler-error-C2562.md)|"*Function*": funkcja "void" zwraca wartość|
|[Błąd kompilatora C2563](compiler-error-C2563.md)|niezgodność w formalnej liście parametrów|
|Błąd kompilatora C2564|Nieaktualne.|
|Błąd kompilatora C2565|"*Identyfikator*": kwalifikator ref jest niedozwolony dla konstruktorów/destruktorów|
|[Błąd kompilatora C2566](compiler-error-C2566.md)|przeciążona funkcja w wyrażeniu warunkowym|
|[Błąd kompilatora C2567](compiler-error-C2567.md)|nie można otworzyć metadanych w *pliku "filename*", *possible_reason*|
|[Błąd kompilatora C2568](compiler-error-C2568.md)|"*Identyfikator*": nie można rozpoznać przeciążenia funkcji|
|[Błąd kompilatora C2569](compiler-error-C2569.md)|"*Identyfikator*": Wyliczenie/Unia nie może być używane jako klasa bazowa|
|[Błąd kompilatora C2570](compiler-error-C2570.md)|"*Identyfikator*": Unia nie może mieć klas bazowych|
|[Błąd kompilatora C2571](compiler-error-C2571.md)|"*Identyfikator*": funkcja wirtualna nie może być w *Unii "Union*"|
|[Błąd kompilatora C2572](compiler-error-C2572.md)|"*Function*": Ponowna definicja domyślnego argumentu: *numer* parametru|
|[Błąd kompilatora C2573](compiler-error-C2573.md)|"*Class*": nie można usunąć wskaźników do obiektów tego typu; Klasa nie ma przeciążenia elementu "operator delete". Użyj::d Usuń lub Dodaj "operator delete (void *)" do klasy|
|[Błąd kompilatora C2574](compiler-error-C2574.md)|"*destruktor*": nie może być zadeklarowany jako statyczny|
|[Błąd kompilatora C2575](compiler-error-C2575.md)|"*Identyfikator*": tylko funkcje składowe i bazy mogą być wirtualne|
|Błąd kompilatora C2576|"*Identyfikator*": nie można wprowadzić nowej metody wirtualnej jako "Public". Rozważ zastosowanie metody niewirtualnej lub zmianę dostępności na "internal" lub "protected private"|
|[Błąd kompilatora C2577](compiler-error-C2577.md)|"*Identyfikator*": destruktor/finalizator nie może mieć zwracanego typu|
|Błąd kompilatora C2578|"*Class*": typ nie może mieć konstruktora "Protected" lub "protected public"|
|[Błąd kompilatora C2579](compiler-error-C2579.md)|nie można rozpoznać *typu* typu (*offset*). Jest oczekiwany w *nazwie pliku*|
|Błąd kompilatora C2580|"*Identyfikator*": nie można używać wielu wersji domyślnych specjalnych funkcji składowych|
|[Błąd kompilatora C2581](compiler-error-C2581.md)|"*Type*": statyczna funkcja "operator =" jest niedozwolona|
|[Błąd kompilatora C2582](compiler-error-C2582.md)|Funkcja *operatora* operatora jest niedostępna w elemencie "*Type*"|
|[Błąd kompilatora C2583](compiler-error-C2583.md)|"*Identyfikator*": "const/volatile" wskaźnik "This" jest niedozwolony dla konstruktorów/destruktorów|
|[Błąd kompilatora C2584](compiler-error-C2584.md)|"*Klasa*": bezpośrednia baza "*base_class2*" jest niedostępna; jest już podstawą elementu "*base_class1*"|
|[Błąd kompilatora C2585](compiler-error-C2585.md)|jawna konwersja na *Typ "Type*" jest niejednoznaczna|
|[Błąd kompilatora C2586](compiler-error-C2586.md)|Nieprawidłowa składnia konwersji zdefiniowanej przez użytkownika: niedozwolone elementy pośrednie|
|[Błąd kompilatora C2587](compiler-error-C2587.md)|"*Identyfikator*": niedozwolone użycie lokalnej zmiennej jako parametru domyślnego|
|[Błąd kompilatora C2588](compiler-error-C2588.md)|":: ~*Identyfikator*": niedozwolony globalny destruktor/finalizator|
|[Błąd kompilatora C2589](compiler-error-C2589.md)|"*Identyfikator*": niedozwolony token po prawej stronie "::"|
|Błąd kompilatora C2590|"*Identyfikator*": tylko Konstruktor może mieć listę inicjatorów podstawowych/składowych|
|Błąd kompilatora C2591|ExclusiveTo nie może używać elementu "*Type*" jako argumentu. Tylko "ref class" jest prawidłowym argumentem|
|[Błąd kompilatora C2592](compiler-error-C2592.md)|"*Class*": "*base_class2*" jest dziedziczona po elemencie "*base_class1*" i nie można go zmienić|
|[Błąd kompilatora C2593](compiler-error-C2593.md)|" *Identyfikator* operatora" jest niejednoznaczny|
|[Błąd kompilatora C2594](compiler-error-C2594.md)|"*operator*": niejednoznaczne konwersje z "*Type1*" na "*Type2*"|
|Błąd kompilatora C2595|"*Identyfikator*" typ atrybutu WinRT musi być zapieczętowany|
|Błąd kompilatora C2596|"*Identyfikator*" pole atrybutu WinRT może być tylko typu "Public enum Class", "int", "unsigned int", "bool", "platform:: Type", "platform:: String" lub "Windows:: Foundation:: HRESULT"|
|[Błąd kompilatora C2597](compiler-error-C2597.md)|niedozwolone odwołanie do niestatycznego elementu członkowskiego "*Identifier*"|
|[Błąd kompilatora C2598](compiler-error-C2598.md)|Specyfikacja powiązania musi znajdować się w zakresie globalnym|
|[Błąd kompilatora C2599](compiler-error-C2599.md)|"*Identyfikator*": Deklaracja do przodu wyliczenia Managed/WinRT jest niedozwolona|

## <a name="see-also"></a>Zobacz też

[Błędy i ostrzeżenia dotyczące kompilatora i narzędzi kompilacji C/C++](../compiler-errors-1/c-cpp-build-errors.md) \
[Błędy kompilatora C2000–C3999](../compiler-errors-1/compiler-errors-c2000-c3999.md)
