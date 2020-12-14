---
description: 'Dowiedz się więcej o: jednostki tłumaczenia i powiązania'
title: Jednostki translacji i powiązania (C++)
ms.date: 12/11/2019
ms.assetid: a6493ba0-24e2-4c89-956e-9da1dea660cb
ms.openlocfilehash: e03edb374a61e461b7a6b30fb88981e7d0cb15f0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97198573"
---
# <a name="translation-units-and-linkage"></a>Jednostki translacji i połączenie

W programie w języku C++ *symbol*, na przykład zmienna lub nazwa funkcji, można zadeklarować dowolną liczbę razy w swoim zakresie, ale można ją zdefiniować tylko raz. Ta reguła jest "jedną regułą definicji" (ODR). *Deklaracja* wprowadza (lub wprowadza) nazwę do programu. *Definicja* wprowadza nazwę. Jeśli nazwa reprezentuje zmienną, definicja jawnie inicjuje ją. *Definicja funkcji* składa się z podpisu i treści funkcji. Definicja klasy składa się z nazwy klasy, po której następuje blok zawierający listę wszystkich elementów członkowskich klasy. (Treść funkcji składowych może być opcjonalnie zdefiniowana osobno w innym pliku).

W poniższym przykładzie przedstawiono niektóre deklaracje:

```cpp
int i;
int f(int x);
class C;
```

W poniższym przykładzie przedstawiono niektóre definicje:

```cpp
int i{42};
int f(int x){ return x * i; }
class C {
public:
   void DoSomething();
};
```

Program składa się z co najmniej jednej *jednostki tłumaczenia*. Jednostka translacji składa się z pliku implementacji i wszystkich nagłówków, które zawiera bezpośrednio lub pośrednio. Pliki implementacji mają zwykle rozszerzenie *CPP* lub *CXX*. Pliki nagłówkowe zazwyczaj mają rozszerzenie *h* lub *HPP*. Każda jednostka translacji jest kompilowana niezależnie przez kompilator. Po zakończeniu kompilacji konsolidator Scala skompilowane jednostki translacji w jeden *program*. Naruszenia reguły ODR są zwykle wyświetlane jako błędy konsolidatora. Błędy konsolidatora występują, gdy ta sama nazwa ma dwie różne definicje w różnych jednostkach tłumaczenia.

Ogólnie rzecz biorąc, najlepszym sposobem, aby zmienna była widoczna w wielu plikach, została umieszczona w pliku nagłówkowym. Następnie Dodaj dyrektywę #include w każdym pliku *CPP* , który wymaga deklaracji. Dodając *osłony include* wokół zawartości nagłówka, upewnij się, że nazwy, które deklaruje, są zdefiniowane tylko raz.

W języku C++ 20 [moduły](modules-cpp.md) są wprowadzane jako ulepszona alternatywa dla plików nagłówkowych.

W niektórych przypadkach może być konieczne zadeklarować zmienną globalną lub klasę w pliku *CPP* . W takich przypadkach konieczne jest określenie kompilatora i konsolidatora rodzaju *powiązania* o nazwie. Typ powiązania określa, czy nazwa obiektu ma zastosowanie tylko do jednego pliku, czy do wszystkich plików. Koncepcja powiązania ma zastosowanie tylko do nazw globalnych. Koncepcja powiązania nie ma zastosowania do nazw, które są zadeklarowane w zakresie. Zakres jest określany przez zestaw otaczających nawiasów klamrowych, takich jak w definicjach funkcji lub klas.

## <a name="external-vs-internal-linkage"></a>Zewnętrzne a połączenie wewnętrzne

*Bezpłatna funkcja* to funkcja, która jest definiowana w globalnym lub zakresie przestrzeni nazw. Zmienne globalne inne niż const i bezpłatne funkcje domyślnie mają *powiązania zewnętrzne*; są one widoczne z dowolnej jednostki tłumaczenia w programie. W związku z tym, żaden inny obiekt globalny nie może mieć tej nazwy. Symbol z *wewnętrznym powiązaniem* lub *bez powiązania* jest widoczny tylko w obrębie jednostki tłumaczenia, w której jest zadeklarowany. Jeśli nazwa ma połączenie wewnętrzne, taka sama nazwa może istnieć w innej jednostce tłumaczenia. Zmienne zadeklarowane w definicjach klas lub treści funkcji nie mają powiązania.

Można wymusić, aby nazwa globalna miała połączenie wewnętrzne przez jawne zadeklarowanie go jako **`static`** . Pozwala to ograniczyć widoczność do tej samej jednostki tłumaczenia, w której jest zadeklarowana. W tym kontekście **`static`** oznacza coś innego niż w przypadku zastosowania do zmiennych lokalnych.

Następujące obiekty mają domyślnie powiązania wewnętrzne:

- obiekty const
- obiekty constexpr
- definicje typów
- obiekty statyczne w zakresie przestrzeni nazw

Aby nadać obiektowi const powiązania zewnętrzne, zadeklaruj go jako **`extern`** i przypisz mu wartość:

```cpp
extern const int value = 42;
```

Aby uzyskać więcej informacji, zobacz [extern](extern-cpp.md) .

## <a name="see-also"></a>Zobacz też

[Podstawowe pojęcia](../cpp/basic-concepts-cpp.md)
