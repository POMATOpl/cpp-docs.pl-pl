---
description: 'Dowiedz się więcej o: przegląd typów ogólnych w języku C++/CLI'
title: Przegląd typów ogólnych w języku C++/CLI
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- generics [C++], about generics
- default initializers [C++]
- type parameters [C++]
- constructed types
- type arguments [C++]
- constructed types, open [C++]
- open constructed types [C++]
- constructed types, closed [C++]
ms.assetid: 21f10637-0fce-4916-b925-6c86a126d3aa
ms.openlocfilehash: 4b84d16f7d76824f732865e3bf8b7bbfe674a1bd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97274154"
---
# <a name="overview-of-generics-in-ccli"></a>Przegląd typów ogólnych w języku C++/CLI

Typy ogólne są typami sparametryzowanymi obsługiwanymi przez środowisko uruchomieniowe języka wspólnego. Typ sparametryzowany jest typem, który jest zdefiniowany za pomocą nieznanego parametru typu, który jest określany podczas użycia generycznego.

## <a name="why-generics"></a>Dlaczego generyczne?

Język C++ obsługuje szablony, a zarówno szablony, jak i generyczne obsługują typy sparametryzowane do tworzenia klas kolekcji o określonym typie. Jednak szablony zapewniają parametryzacja czasu kompilacji. Nie można odwołać się do zestawu zawierającego definicję szablonu i utworzyć nowe specjalizacje szablonu. Po skompilowaniu wyspecjalizowany szablon wygląda podobnie do żadnej innej klasy lub metody. Z kolei typy ogólne są emitowane w języku MSIL jako typ sparametryzowany znany przez środowisko uruchomieniowe jako typ sparametryzowany. kod źródłowy, który odwołuje się do zestawu zawierającego typ ogólny, może tworzyć specjalizacje typu ogólnego. Aby uzyskać więcej informacji na temat porównania standardowych szablonów C++ i rodzajowych, zobacz [Ogólne i szablony (C++/CLI)](generics-and-templates-visual-cpp.md).

## <a name="generic-functions-and-types"></a>Funkcje i typy ogólne

Typy klas, o ile są typami zarządzanymi, mogą być ogólne. Przykładem może być `List` Klasa. Typ obiektu na liście jest parametrem typu. Jeśli potrzebujesz `List` klasy dla wielu różnych typów obiektów, przed użyciem generycznych, które mogą być używane `List` `System::Object` jako typ elementu. Ale może to spowodować użycie dowolnego obiektu (w tym obiektów niewłaściwego typu) na liście. Taka lista powinna być nazywana klasą kolekcji niewpisanej. Najlepiej sprawdzić typ w czasie wykonywania i zgłosić wyjątek. Może być też używany szablon, który spowodowałaby utratę jego jakości ogólnej po skompilowaniu do zestawu. Odbiorcy Twojego zestawu nie mogą utworzyć własnych specjalizacji szablonu. Typy ogólne umożliwiają tworzenie klas kolekcji typu, powiedzmy `List<int>` (Odczytaj jako "list of int") i `List<double>` ("list of Double"), która wygenerowała błąd czasu kompilacji, Jeśli podjęto próbę umieszczenia typu, który nie został zaprojektowany do akceptowania kolekcji w określonym zbiorze. Ponadto te typy pozostają ogólne po skompilowaniu.

Opis składni klas ogólnych można znaleźć w [klasach generycznych (C++/CLI)](generic-classes-cpp-cli.md). Nowy obszar nazw, <xref:System.Collections.Generic> , wprowadza zestaw sparametryzowane typy kolekcji, w tym <xref:System.Collections.Generic.Dictionary%602> , <xref:System.Collections.Generic.List%601> i <xref:System.Collections.Generic.LinkedList%601> .

Zarówno funkcja, jak i elementy członkowskie klasy statycznej, delegatów i funkcje globalne mogą być również ogólne. Funkcje generyczne mogą być niezbędne, jeśli parametry funkcji są nieznanego typu lub jeśli sama funkcja musi działać z typami ogólnymi. W wielu przypadkach `System::Object` , gdy mogły zostać użyte w przeszłości jako parametr dla nieznanego typu obiektu, zamiast tego można użyć parametru typu ogólnego, co pozwala na bardziej bezpieczny typ kodu. Każda próba przekazania w typie, do którego funkcja nie została zaprojektowana, zostanie oflagowana jako błąd w czasie kompilacji. Użycie `System::Object` jako parametru funkcji, nieoczekiwane przekazanie obiektu, do którego nie została zaprojektowana, nie zostanie wykryte i konieczne będzie rzutowanie nieznanego typu obiektu do określonego typu w treści funkcji i konta dla możliwości InvalidCastException. Przy użyciu generycznego kodu próba przekazania obiektu do funkcji spowodowałaby konflikt typu, aby treść funkcji była poprawna.

Te same korzyści dotyczą klas kolekcji opartych na typach ogólnych. Klasy kolekcji z przeszłości byłyby używane `System::Object` do przechowywania elementów w kolekcji. Wstawianie obiektów typu, dla których kolekcja nie została zaprojektowana, nie jest oflagowane w czasie kompilacji i często nie nawet po wstawieniu obiektów. Zazwyczaj obiekt zostałby przerzutowany do innego typu, gdy uzyskano do niego dostęp w kolekcji. Tylko wtedy, gdy rzutowanie nie powiodło się, zostanie wykryty nieoczekiwany typ. Typy ogólne rozwiązują ten problem w czasie kompilacji przez wykrycie dowolnego kodu, który wstawia typ, który jest niezgodny (lub niejawnie konwertowany na) parametr typu kolekcji ogólnej.

Aby zapoznać się z opisem składni, zobacz [funkcje ogólne (C++/CLI)](generic-functions-cpp-cli.md).

## <a name="terminology-used-with-generics"></a>Terminologia używana z typami ogólnymi

### <a name="type-parameters"></a>Parametry typu

Deklaracja generyczna zawiera jeden lub więcej nieznanych typów znanych jako *parametry typu*. Parametry typu mają nazwę oznaczającą typ w treści deklaracji ogólnej. Parametr typu jest używany jako typ w treści deklaracji ogólnej. Deklaracja ogólna dla `List<T>` zawiera parametr typu T.

### <a name="type-arguments"></a>Argumenty typu

*Argument typu* jest rzeczywistym typem używanym zamiast parametru typu, gdy ogólny jest wyspecjalizowany dla określonego typu lub typów. Na przykład, **`int`** jest argumentem typu w `List<int>` . Typy wartości i typy dojścia są jedynymi typami dozwolonymi w jako argument typu ogólnego.

### <a name="constructed-type"></a>Typ skonstruowany

Typ zbudowany z typu ogólnego jest określany jako *Typ skonstruowany*. Typ, który nie jest w pełni określony, na przykład `List<T>` jest *otwartym typem skonstruowanym*; w pełni określony typ, taki jak `List<double>,` jest *zamknięty typ skonstruowany* lub *Typ wyspecjalizowany*. Otwarte typy skonstruowane mogą być używane w definicji innych typów ogólnych lub metod i mogą nie być w pełni określone, dopóki nie zostanie określony element ogólny. Na przykład poniższy kod jest używany jako klasa bazowa dla ogólnego:

```cpp
// generics_overview.cpp
// compile with: /clr /c
generic <typename T>

ref class List {};

generic <typename T>

ref class Queue : public List<T> {};
```

### <a name="constraint"></a>Typu

Ograniczenie to ograniczenie typów, które mogą być używane jako parametr typu. Na przykład dana klasa generyczna może akceptować tylko klasy, które dziedziczą z określonej klasy, lub implementują określony interfejs. Aby uzyskać więcej informacji, zobacz [ograniczenia dotyczące parametrów typu ogólnego (C++/CLI)](constraints-on-generic-type-parameters-cpp-cli.md).

## <a name="reference-types-and-value-types"></a>Typy odwołań i typy wartości

Typy dojść i typy wartości mogą być używane jako argumenty typu. W definicji generycznej, w której można użyć dowolnego typu, składnia jest dla typów referencyjnych. Na przykład operator służy `->` do uzyskiwania dostępu do składowych typu parametru typu, niezależnie od tego, czy typ ostatecznie używany jest typem referencyjnym, czy typem wartości. Gdy typ wartości jest używany jako argument typu, środowisko uruchomieniowe generuje kod, który używa typów wartości bezpośrednio bez pakowania typów wartości.

W przypadku używania typu referencyjnego jako argumentu typu ogólnego należy użyć składni dojścia. W przypadku używania typu wartości jako argumentu typu ogólnego należy użyć nazwy typu bezpośrednio.

```cpp
// generics_overview_2.cpp
// compile with: /clr
generic <typename T>

ref class GenericType {};
ref class ReferenceType {};

value struct ValueType {};

int main() {
    GenericType<ReferenceType^> x;
    GenericType<ValueType> y;
}
```

## <a name="type-parameters"></a>Parametry typu

Parametry typu w klasie generycznej są traktowane jak inne identyfikatory. Jednak ponieważ typ nie jest znany, istnieją ograniczenia dotyczące ich użycia. Na przykład nie można używać składowych i metod klasy parametru typu, chyba że parametr typu jest znany do obsługi tych elementów członkowskich. Oznacza to, aby uzyskać dostęp do elementu członkowskiego za pomocą parametru typu, należy dodać typ, który zawiera element członkowski do listy ograniczeń parametru typu.

```cpp
// generics_overview_3.cpp
// compile with: /clr
interface class I {
   void f1();
   void f2();
};

ref struct R : public I {
   virtual void f1() {}
   virtual void f2() {}
   virtual void f3() {}
};

generic <typename T>
where T : I
void f(T t) {
   t->f1();
   t->f2();
   safe_cast<R^>(t)->f3();
}

int main() {
   f(gcnew R());
}
```

Te ograniczenia dotyczą również operatorów. W przypadku nieograniczonego parametru typu ogólnego nie można używać `==` `!=` operatorów i do porównywania dwóch wystąpień parametru typu, jeśli typ nie obsługuje tych operatorów. Te testy są konieczne w przypadku typów ogólnych, ale nie dla szablonów, ponieważ typy ogólne mogą być wyspecjalizowane w czasie wykonywania z dowolną klasą, która spełnia ograniczenia, gdy jest zbyt późno, aby sprawdzić użycie nieprawidłowych elementów członkowskich.

Domyślne wystąpienie parametru typu można utworzyć za pomocą `()` operatora. Na przykład:

`T t = T();`

gdzie `T` jest parametrem typu w klasie generycznej lub definicji metody, inicjuje zmienną do jej wartości domyślnej. Jeśli `T` jest klasą referencyjną, będzie pusty wskaźnik; Jeśli `T` jest klasą wartości, obiekt jest zainicjowany do zera. Jest to nazywane *inicjatorem domyślnym*.

## <a name="see-also"></a>Zobacz też

[Typy ogólne](generics-cpp-component-extensions.md)
