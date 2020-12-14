---
description: 'Dowiedz się więcej o: Błędy kompilatora C3100 przez C3199'
title: Błędy kompilatora — od C3100 do C3199
ms.date: 04/21/2019
f1_keywords:
- C3102
- C3105
- C3107
- C3108
- C3109
- C3111
- C3112
- C3119
- C3122
- C3123
- C3124
- C3125
- C3127
- C3128
- C3129
- C3143
- C3144
- C3146
- C3147
- C3148
- C3151
- C3158
- C3164
- C3165
- C3169
- C3177
- C3178
- C3184
- C3188
- C3191
- C3193
helpviewer_keywords:
- C3102
- C3105
- C3107
- C3108
- C3109
- C3111
- C3112
- C3119
- C3122
- C3123
- C3124
- C3125
- C3127
- C3128
- C3129
- C3143
- C3144
- C3146
- C3147
- C3148
- C3151
- C3158
- C3164
- C3165
- C3169
- C3177
- C3178
- C3184
- C3188
- C3191
- C3193
ms.assetid: 7bc40c2f-6a8d-488a-b665-f39375afee77
ms.openlocfilehash: d2398fa8ae783a34662efc361730a5054a982458
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97238716"
---
# <a name="compiler-errors-c3100-through-c3199"></a>Błędy kompilatora — od C3100 do C3199

W artykułach w tej sekcji dokumentacji wyjaśniono podzestaw komunikatów o błędach generowanych przez kompilator.

[!INCLUDE[error-boilerplate](../../error-messages/includes/error-boilerplate.md)]

## <a name="error-messages"></a>Komunikaty o błędach

|Błąd|Wiadomość|
|-----------|-------------|
|[Błąd kompilatora C3100](compiler-error-c3100.md)|"*Identyfikator*": nieznany kwalifikator atrybutu|
|[Błąd kompilatora C3101](compiler-error-c3101.md)|niedozwolone wyrażenie nazwanego argumentu atrybutu "*Identifier*"|
|Błąd kompilatora C3102|Nieaktualne.|
|[Błąd kompilatora C3103](compiler-error-c3103.md)|"*Identyfikator*": powtórzony nazwany argument|
|[Błąd kompilatora C3104](compiler-error-c3104.md)|niedozwolony argument atrybutu|
|Błąd kompilatora C3105|"*symbol*": nie można użyć jako atrybutu|
|[Błąd kompilatora C3106](compiler-error-c3106.md)|"*Attribute*": nienazwane argumenty muszą poprzedzać nazwane argumenty|
|Błąd kompilatora C3107|"*Attribute*": funkcje składowe atrybutów natywnych nie mogą być zdefiniowane|
|Błąd kompilatora C3108|nie można wywnioskować typu, ponieważ lista inicjalizatora nie jest wyrażeniem|
|Błąd kompilatora C3109|"*Identyfikator*": metody interfejsu muszą używać konwencji wywoływania "__stdcall" lub "__cdecl"|
|[Błąd kompilatora C3110](compiler-error-c3110.md)|"*Function*": nie można przeciążyć metody interfejsu com|
|Błąd kompilatora C3111|Nie można użyć listy inicjalizatora jako domyślnego argumentu dla parametru szablonu|
|Błąd kompilatora C3112|"*Interface*": interfejs może być zadeklarowany tylko w globalnym lub zakresie przestrzeni nazw|
|[Błąd kompilatora C3113](compiler-error-c3113.md)|element "Interface/enum" nie może być szablonem/rodzajowym|
|[Błąd kompilatora C3114](compiler-error-c3114.md)|"*Identyfikator*": nie jest prawidłowym argumentem nazwanego atrybutu|
|[Błąd kompilatora C3115](compiler-error-c3115.md)|"*Attribute*": ten atrybut jest niedozwolony w *konstrukcji*"|
|[Błąd kompilatora C3116](compiler-error-c3116.md)|"*specyfikator*": nieprawidłowa Klasa magazynu dla metody interfejsu|
|[Błąd kompilatora C3117](compiler-error-c3117.md)|"*Interface*": interfejs może mieć tylko jedną klasę bazową|
|[Błąd kompilatora C3118](compiler-error-c3118.md)|"*Interface*": interfejsy nie obsługują wirtualnego dziedziczenia|
|Błąd kompilatora C3119|alignas (void) nie jest dozwolony|
|[Błąd kompilatora C3120](compiler-error-c3120.md)|"*Identyfikator*": metody interfejsu nie mogą przyjmować zmiennej listy argumentów|
|[Błąd kompilatora C3121](compiler-error-c3121.md)|nie można zmienić identyfikatora GUID dla klasy "*Class*"|
|Błąd kompilatora C3122|"*Interface*": generyczny interfejs WinRT nie może mieć identyfikatora GUID|
|Błąd kompilatora C3123|Generyczny interfejs WinRT nie może mieć ograniczeń|
|Błąd kompilatora C3124|"podpisany char" nie jest prawidłowym typem danych WinRT. Zamiast tego należy użyć znaków "unsigned", "wchar_t" lub "unshortd".|
|Błąd kompilatora C3125|"*Type*": typ nie może bezpośrednio ani pośrednio dziedziczyć po "platform:: Exception"|
|[Błąd kompilatora C3126](compiler-error-c3126.md)|nie można zdefiniować elementu Union "*Union*" wewnątrz typu zarządzanego/WinRT "*Type*"|
|Błąd kompilatora C3127|"*Type*": cechy "*cecha*" można używać tylko w klasie ref WinRT|
|Błąd kompilatora C3128|element "*Type*" nie ma tabeli typu tablicowego, która została wprowadzona przez element "*Type*"|
|Błąd kompilatora C3129|"*Type*": __default_vptr_for_base może być używany tylko na lokalnie zdefiniowanych typach polimorficznych i bazach|
|[Błąd kompilatora C3130](compiler-error-c3130.md)|Wewnętrzny błąd kompilatora: nie można zapisać wstrzykniętego bloku kodu do PDB|
|[Błąd kompilatora C3131](compiler-error-c3131.md)|projekt musi mieć atrybut "module" z właściwością "name"|
|[Błąd kompilatora C3132](compiler-error-c3132.md)|"*Parameter*": tablice parametrów mogą być stosowane tylko do formalnego argumentu typu "tablica zarządzana/WinRT z jednym wymiarem"|
|[Błąd kompilatora C3133](compiler-error-c3133.md)|Nie można zastosować atrybutów do typu VarArgs języka C++|
|[Błąd kompilatora C3134](compiler-error-c3134.md)|"*Value*": wartość argumentu atrybutu "*argument*" nie ma prawidłowego typu "*Type*"|
|[Błąd kompilatora C3135](compiler-error-c3135.md)|"*Identyfikator*": właściwość nie może mieć typu "const" lub "volatile"|
|[Błąd kompilatora C3136](compiler-error-c3136.md)|"*Interface*": interfejs com może dziedziczyć tylko po innym interfejsie com,*interfejs* nie jest interfejsem com|
|[Błąd kompilatora C3137](compiler-error-c3137.md)|"*Identyfikator*": nie można zainicjować właściwości|
|[Błąd kompilatora C3138](compiler-error-c3138.md)|"*Identyfikator*": interfejs "*Attribute*" musi dziedziczyć z IDispatch lub z interfejsu, który dziedziczy z IDispatch|
|[Błąd kompilatora C3139](compiler-error-c3139.md)|"*Type*": nie można eksportować UDT bez składowych|
|[Błąd kompilatora C3140](compiler-error-c3140.md)|nie można mieć wielu atrybutów "module" w tej samej jednostce kompilacji|
|[Błąd kompilatora C3141](compiler-error-c3141.md)|"*Interface*": interfejsy obsługują tylko publiczne dziedziczenie|
|[Błąd kompilatora C3142](compiler-error-c3142.md)|"*Property*": nie można przyjąć adresu właściwości|
|Błąd kompilatora C3143|"*argument*": argument atrybutu nie może mieć wielu wartości|
|Błąd kompilatora C3144|"*Attribute*": atrybut wymaga jawnych argumentów, "*argument*" jest bez nazwy|
|[Błąd kompilatora C3145](compiler-error-c3145.md)|"*Identyfikator*": globalna lub statyczna zmienna może nie mieć typu zarządzanego/WinRT "*Type*"|
|Błąd kompilatora C3146|Nieaktualne.|
|Błąd kompilatora C3147|Nieaktualne.|
|Błąd kompilatora C3148|Nieaktualne.|
|[Błąd kompilatora C3149](compiler-error-c3149.md)|"*Type*": nie można użyć tego typu w tym miejscu bez *tokenu*"najwyższego poziomu"|
|[Błąd kompilatora C3150](compiler-error-c3150.md)|"*konstrukcja*": "*Attribute*" może być stosowana tylko do klasy, struktury, interfejsu, tablicy lub wskaźnika|
|Błąd kompilatora C3151|Nieaktualne.|
|[Błąd kompilatora C3152](compiler-error-c3152.md)|"*Function*":*słowo kluczowe*"Only" może być stosowane tylko do klasy, struktury lub wirtualnej funkcji składowej|
|[Błąd kompilatora C3153](compiler-error-c3153.md)|"*Interface*": nie można utworzyć wystąpienia interfejsu|
|[Błąd kompilatora C3154](compiler-error-c3154.md)|Oczekiwano znaku "," przed wielokropkiem. Wielokropek rozdzielonych przecinkami nie jest obsługiwany w funkcjach tablicy parametrów.|
|[Błąd kompilatora C3155](compiler-error-c3155.md)|atrybuty nie są dozwolone w indeksatorze właściwości|
|[Błąd kompilatora C3156](compiler-error-c3156.md)|"*Class*": nie można posiadać lokalnej definicji typu zarządzanego/WinRT|
|[Błąd kompilatora C3157](compiler-error-c3157.md)|Atrybut ParamArray może być stosowany tylko do ostatniego parametru|
|Błąd kompilatora C3158|"*Function*": "*słowo kluczowe*" może być stosowane tylko do wirtualnej funkcji składowej|
|[Błąd kompilatora C3159](compiler-error-c3159.md)|"*Identyfikator*": nie można zadeklarować tablicy wskaźników do typu wartościowego|
|[Błąd kompilatora C3160](compiler-error-c3160.md)|"*Type*": element członkowski danych klasy Managed/WinRT nie może mieć tego typu|
|[Błąd kompilatora C3161](compiler-error-c3161.md)|"*Interface*": zagnieżdżanie klasy, struktury lub interfejsu w interfejsie jest niedozwolone; Zagnieżdżanie interfejsu w klasie lub strukturze jest niedozwolone|
|[Błąd kompilatora C3162](compiler-error-c3162.md)|"*Type*": typu referencyjnego, który ma destruktor, nie można użyć jako typu statycznej składowej danych "*member*"|
|[Błąd kompilatora C3163](compiler-error-c3163.md)|"*Class*": atrybuty niespójne z poprzednią deklaracją|
|Błąd kompilatora C3164|Nieaktualne.|
|Błąd kompilatora C3165|"*Value*": nie można konwertować na wartość całkowitą lub zmiennoprzecinkową|
|[Błąd kompilatora C3166](compiler-error-c3166.md)|Nieaktualne. "*Type*": element członkowski danych klasy Managed/WinRT nie może mieć typu "*pointer_type* do wnętrza *managed_pointer_type*"|
|[Błąd kompilatora C3167](compiler-error-c3167.md)|Nie można zainicjować .NET Framework: Upewnij się, że jest zainstalowany|
|[Błąd kompilatora C3168](compiler-error-c3168.md)|"*Type*": niedozwolony typ podstawowy dla wyliczenia|
|Błąd kompilatora C3169|"*Type*": nie można wywnioskować typu dla elementu "Auto" z "*Type*"|
|[Błąd kompilatora C3170](compiler-error-c3170.md)|nie może mieć innych identyfikatorów modułu w projekcie|
|[Błąd kompilatora C3171](compiler-error-c3171.md)|"*module*": nie można określić innych atrybutów modułu w projekcie|
|[Błąd kompilatora C3172](compiler-error-c3172.md)|"*Identyfikator*": nie można określić różnych atrybutów idl_module w projekcie|
|[Błąd kompilatora C3173](compiler-error-c3173.md)|niezgodność wersji w scaleniu IDL|
|[Błąd kompilatora C3174](compiler-error-c3174.md)|nie określono atrybutu modułu|
|[Błąd kompilatora C3175](compiler-error-c3175.md)|"*Function*": nie można wywołać metody typu zarządzanego z niezarządzanej funkcji "*Function*"|
|[Błąd kompilatora C3176](compiler-error-c3176.md)|"*Type*": nie można zadeklarować lokalnego typu wartościowego|
|Błąd kompilatora C3177|nie można mieć funkcji konwersji do typu, który zawiera element "*Type*".|
|Błąd kompilatora C3178|"*Type*": nie można używać ParamArray w funkcji z argumentami domyślnymi|
|[Błąd kompilatora C3179](compiler-error-c3179.md)|nienazwany typ zarządzany/WinRT jest niedozwolony|
|[Błąd kompilatora C3180](compiler-error-c3180.md)|"*Type*": nazwa przekracza limit meta danych znaków "*Number*"|
|[Błąd kompilatora C3181](compiler-error-c3181.md)|"*Type*": nieprawidłowy operand dla *operatora*|
|[Błąd kompilatora C3182](compiler-error-c3182.md)|"*Type*": Deklaracja składowej using lub Deklaracja dostępu jest niedozwolona w ramach typu zarządzanego/WinRT|
|[Błąd kompilatora C3183](compiler-error-c3183.md)|nie można zdefiniować nienazwanej klasy, struktury lub związku wewnątrz typu zarządzanego/WinRT "*Class*"|
|Błąd kompilatora C3184|Nieaktualne.|
|[Błąd kompilatora C3185](compiler-error-c3185.md)|"typeid": używany na typie zarządzanym/WinRT "*Type*", użyj "*operator*" zamiast niego|
|Błąd kompilatora C3186|Nieaktualne.|
|[Błąd kompilatora C3187](compiler-error-c3187.md)|"*Identyfikator*": jest dostępny tylko w treści funkcji|
|Błąd kompilatora C3188|Nieaktualne.|
|[Błąd kompilatora C3189](compiler-error-c3189.md)|"typeid<*deklarator*>": Ta składnia nie jest już obsługiwana, należy zamiast niej użyć:: typeid|
|[Błąd kompilatora C3190](compiler-error-c3190.md)|"*deklarator*" z podanymi argumentami szablonu nie jest jawnym wystąpieniem żadnej funkcji składowej "*Type*"|
|Błąd kompilatora C3191|Nieaktualne.|
|[Błąd kompilatora C3192](compiler-error-c3192.md)|Błąd składniowy: "^" nie jest operatorem prefiksowym (Czy chodziło o "*"?)|
|Błąd kompilatora C3193|"*konstrukcja*": wymaga opcji wiersza polecenia "/CLR" lub "/zw"|
|[Błąd kompilatora C3194](compiler-error-c3194.md)|"*Type*": typ wartości nie może mieć operatora przypisania|
|[Błąd kompilatora C3195](compiler-error-c3195.md)|*słowo kluczowe*": jest zarezerwowane i nie może być używane jako element członkowski klasy referencyjnej lub typu wartości. Operatory CLR/WinRT muszą być zdefiniowane za pomocą słowa kluczowego "operator"|
|[Błąd kompilatora C3196](compiler-error-c3196.md)|"*Identyfikator*": użyto więcej niż raz|
|[Błąd kompilatora C3197](compiler-error-c3197.md)|*słowo kluczowe*": może być używane tylko w definicjach|
|[Błąd kompilatora C3198](compiler-error-c3198.md)|nieprawidłowe użycie zmiennoprzecinkowych pragm: fenv_access pragma działa tylko w trybie precyzyjnym|
|[Błąd kompilatora C3199](compiler-error-c3199.md)|nieprawidłowe użycie zmiennoprzecinkowych pragm: wyjątki nie są obsługiwane w trybie bez dokładności|

## <a name="see-also"></a>Zobacz też

[Błędy i ostrzeżenia dotyczące kompilatora i narzędzi kompilacji C/C++](../compiler-errors-1/c-cpp-build-errors.md) \
[Błędy kompilatora C2000–C3999](../compiler-errors-1/compiler-errors-c2000-c3999.md)
