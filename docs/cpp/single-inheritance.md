---
description: 'Dowiedz się więcej na temat: Dziedziczenie pojedyncze'
title: Pojedyncze dziedziczenie
ms.date: 11/19/2018
helpviewer_keywords:
- single inheritance
- base classes [C++], indirect
- scope, scope resolution operator
- operators [C++], scope resolution
- scope resolution operator
- derived classes [C++], single base class
- inheritance, single
ms.assetid: 1cb946ed-8b1b-4cf1-bde0-d9cecbfdc622
ms.openlocfilehash: a750cf66074612ce40f9a4fa03d8453ae2decfef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97116954"
---
# <a name="single-inheritance"></a>Pojedyncze dziedziczenie

W obszarze "pojedyncze dziedziczenie" wspólna forma dziedziczenia klasy mają tylko jedną klasę bazową. Rozważmy zależność podaną na poniższej ilustracji.

![Wykres podstawowego dziedziczenia pojedynczego&#45;](../cpp/media/vc38xj1.gif "Wykres podstawowego dziedziczenia pojedynczego&#45;") <br/>
Prosty Graf Single-Inheritance

Zwróć uwagę na postęp od ogólnego do określonego na rysunku. Innym wspólnym atrybutem znalezionym w projekcie większości hierarchii klas jest to, że Klasa pochodna ma relację "rodzaj" z klasą bazową. Na rysunku, a `Book` jest rodzajem a `PrintedDocument` , a a `PaperbackBook` jest rodzajem a `book` .

Jeden inny element notatki na rysunku: `Book` jest klasą pochodną (od `PrintedDocument` ) i klasą bazową ( `PaperbackBook` pochodną `Book` ). Deklaracja szkieletowa tej hierarchii klas jest pokazana w poniższym przykładzie:

```cpp
// deriv_SingleInheritance.cpp
// compile with: /LD
class PrintedDocument {};

// Book is derived from PrintedDocument.
class Book : public PrintedDocument {};

// PaperbackBook is derived from Book.
class PaperbackBook : public Book {};
```

`PrintedDocument` jest traktowana jako Klasa "Direct Base" do `Book` ; jest to Klasa "pośrednia podstawowa" do `PaperbackBook` . Różnica polega na tym, że bezpośrednia klasa bazowa pojawia się na liście podstawowej deklaracji klasy, a pośrednia podstawowa nie.

Klasa bazowa, z której każda klasa jest pochodna jest zadeklarowana przed deklaracją klasy pochodnej. Nie wystarcza do zapewnienia deklaracji odwołującej się do przodu dla klasy bazowej; musi być kompletną deklaracją.

W poprzednim przykładzie **`public`** używany jest specyfikator dostępu. Znaczenie publicznego, chronionego i prywatnego dziedziczenia jest opisane w [Access Control członkowskich.](../cpp/member-access-control-cpp.md)

Klasa może stanowić klasę bazową dla wielu określonych klas, jak pokazano na poniższej ilustracji.

![Ukierunkowany wykres acykliczne](../cpp/media/vc38xj2.gif "Ukierunkowany wykres acykliczne") <br/>
Przykład ukierunkowanego wykresu acykliczne

Na schemacie pokazanym powyżej, nazywany "bezpośrednim wykresem acykliczne" (lub "DAG"), niektóre klasy są klasami podstawowymi dla więcej niż jednej klasy pochodnej. Jednak odwrócenie nie jest prawdziwe: istnieje tylko jedna bezpośrednia klasa bazowa dla danej klasy pochodnej. Wykres na rysunku przedstawia strukturę "pojedynczego dziedziczenia".

> [!NOTE]
> Ukierunkowane wykresy acykliczne nie są unikatowe dla pojedynczego dziedziczenia. Są one również używane do przedstawiania wykresów o wielu dziedziczeniu.

W obszarze dziedziczenia Klasa pochodna zawiera elementy członkowskie klasy bazowej oraz dowolnych nowych członków. W efekcie Klasa pochodna może odwoływać się do elementów członkowskich klasy podstawowej (chyba że te elementy członkowskie są ponownie zdefiniowane w klasie pochodnej). Operatora rozpoznawania zakresu ( `::` ) można użyć do odwoływania się do członków bezpośrednich lub pośrednich klas podstawowych, gdy te elementy członkowskie zostały ponownie zdefiniowane w klasie pochodnej. Rozważ taki przykład:

```cpp
// deriv_SingleInheritance2.cpp
// compile with: /EHsc /c
#include <iostream>
using namespace std;
class Document {
public:
   char *Name;   // Document name.
   void PrintNameOf();   // Print name.
};

// Implementation of PrintNameOf function from class Document.
void Document::PrintNameOf() {
   cout << Name << endl;
}

class Book : public Document {
public:
   Book( char *name, long pagecount );
private:
   long  PageCount;
};

// Constructor from class Book.
Book::Book( char *name, long pagecount ) {
   Name = new char[ strlen( name ) + 1 ];
   strcpy_s( Name, strlen(Name), name );
   PageCount = pagecount;
};
```

Należy zauważyć, że Konstruktor dla `Book` , ( `Book::Book` ), ma dostęp do elementu członkowskiego danych, `Name` . W programie obiekt typu `Book` można utworzyć i użyć w następujący sposób:

```cpp
//  Create a new object of type Book. This invokes the
//   constructor Book::Book.
Book LibraryBook( "Programming Windows, 2nd Ed", 944 );

...

//  Use PrintNameOf function inherited from class Document.
LibraryBook.PrintNameOf();
```

Jak pokazano w powyższym przykładzie, element członkowski klasy i dziedziczone dane oraz funkcje są używane identycznie. Jeśli implementacja klasy `Book` wywołuje dla ponownej implementacji `PrintNameOf` funkcji, funkcja, która należy do `Document` klasy, może być wywoływana tylko za pomocą operatora rozpoznawania zakresu ( `::` ):

```cpp
// deriv_SingleInheritance3.cpp
// compile with: /EHsc /LD
#include <iostream>
using namespace std;

class Document {
public:
   char *Name;          // Document name.
   void  PrintNameOf() {}  // Print name.
};

class Book : public Document {
   Book( char *name, long pagecount );
   void PrintNameOf();
   long  PageCount;
};

void Book::PrintNameOf() {
   cout << "Name of book: ";
   Document::PrintNameOf();
}
```

Wskaźniki i odwołania do klas pochodnych mogą być niejawnie konwertowane na wskaźniki i odwołania do ich klas bazowych, jeśli istnieje dostępna jednoznaczna Klasa bazowa. Poniższy kod ilustruje tę koncepcję przy użyciu wskaźników (ta sama zasada dotyczy odwołań):

```cpp
// deriv_SingleInheritance4.cpp
// compile with: /W3
struct Document {
   char *Name;
   void PrintNameOf() {}
};

class PaperbackBook : public Document {};

int main() {
   Document * DocLib[10];   // Library of ten documents.
   for (int i = 0 ; i < 5 ; i++)
      DocLib[i] = new Document;
   for (int i = 5 ; i < 10 ; i++)
      DocLib[i] = new PaperbackBook;
}
```

W poprzednim przykładzie tworzone są różne typy. Ponieważ jednak te typy są wszystkie pochodne od `Document` klasy, istnieje niejawna konwersja na `Document *` . W związku z `DocLib` tym jest "listą heterogeniczną" (lista, w której nie wszystkie obiekty są tego samego typu) zawierający różne rodzaje obiektów.

Ponieważ `Document` Klasa ma `PrintNameOf` funkcję, może ona drukować nazwę każdej książki w bibliotece, chociaż może pominąć niektóre informacje specyficzne dla typu dokumentu (liczba stron dla `Book` , liczba bajtów dla `HelpFile` itd.).

> [!NOTE]
> Wymuszanie implementacji przez klasę bazową funkcji, takiej jak `PrintNameOf` często nie jest najlepszym projektem. [Funkcje wirtualne](../cpp/virtual-functions.md) oferują inne alternatywy projektowe.
