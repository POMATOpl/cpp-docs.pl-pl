---
description: Dowiedz się więcej na temat:. Przetwarzanie pliku XML
title: Przetwarzanie pliku .Xml
ms.date: 11/04/2016
helpviewer_keywords:
- XML documentation, processing XML file
ms.assetid: e70fdeae-80ac-4872-ab24-771c5635cfbf
ms.openlocfilehash: ded4551adcc4bec4aef27fe38f47470065ea9ef4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192697"
---
# <a name="xml-file-processing"></a>Przetwarzanie pliku .Xml

Kompilator generuje ciąg identyfikatora dla każdej konstrukcji w kodzie, który jest oznaczony do generowania dokumentacji. Aby uzyskać więcej informacji, zobacz [Komentarze dokumentacji dotyczącej polecanych tagów](recommended-tags-for-documentation-comments-visual-cpp.md). Ciąg identyfikatora jednoznacznie identyfikuje konstrukcję. Programy, które przetwarzają plik. XML, mogą używać ciągu identyfikatora do identyfikowania odpowiednich metadanych .NET Framework lub elementu odbicia, do którego odnosi się dokumentacja.

Plik. XML nie jest hierarchiczną reprezentacją kodu, jest to płaska lista z wygenerowanym IDENTYFIKATORem dla każdego elementu.

Podczas generowania ciągów identyfikatorów kompilator przestrzega następujących reguł:

- Brak białego znaku w ciągu.

- Pierwsza część ciągu identyfikatora identyfikuje rodzaj identyfikowanego elementu członkowskiego z pojedynczym znakiem, po którym następuje dwukropek. Używane są następujące typy elementów członkowskich:

  | Znak | Opis |
  |---------------|-----------------|
  | N | namespace<br /><br /> Nie można dodać komentarzy do dokumentacji do przestrzeni nazw, cref odwołania do przestrzeni nazw są możliwe. |
  | T | Typ: Klasa, interfejs, struktura, Wyliczenie, delegat |
  | D |  — klasa typedef |
  | F | pole |
  | P | Właściwość (w tym indeksatory lub inne właściwości indeksowane) |
  | M | Metoda (łącznie z takimi metodami specjalnymi jak konstruktory, operatory itd.) |
  | E | event |
  | ! | ciąg błędu<br /><br /> Pozostała część ciągu zawiera informacje o błędzie. Kompilator MSVC generuje informacje o błędzie dla linków, których nie można rozpoznać. |

- Druga część ciągu to w pełni kwalifikowana nazwa elementu, rozpoczynając od elementu głównego przestrzeni nazw. Nazwa elementu, jego typ lub typy oraz przestrzeń nazw są oddzielone kropkami. Jeśli nazwa samego elementu ma okresy, są one zastępowane przez znak hash ("#"). Przyjęto założenie, że żaden element nie ma znaku skrótu bezpośrednio w nazwie. Na przykład w pełni kwalifikowana nazwa `String` konstruktora byłaby "System. String. #ctor".

- W przypadku właściwości i metod, jeśli istnieją argumenty metody, lista argumentów ujęta w nawiasy. Jeśli nie ma żadnych argumentów, nie ma nawiasów. Argumenty są rozdzielone przecinkami. Kodowanie każdego argumentu następuje bezpośrednio po zakodowaniu w sygnaturze .NET Framework:

  - Typy podstawowe. Zwykłe typy (ELEMENT_TYPE_CLASS lub ELEMENT_TYPE_VALUETYPE) są reprezentowane jako w pełni kwalifikowana nazwa typu.

  - Typy wewnętrzne (na przykład ELEMENT_TYPE_I4, ELEMENT_TYPE_OBJECT, ELEMENT_TYPE_STRING ELEMENT_TYPE_TYPEDBYREF. i ELEMENT_TYPE_VOID) są reprezentowane jako w pełni kwalifikowana nazwa odpowiedniego pełnego typu, na przykład **System. Int32** lub **System. TypedReference**.

  - ELEMENT_TYPE_PTR jest reprezentowane jako "*" po zmodyfikowanym typie.

  - ELEMENT_TYPE_BYREF jest reprezentowane jako " \@ " po zmodyfikowanym typie.

  - ELEMENT_TYPE_PINNED jest reprezentowane jako "^" po zmodyfikowanym typie. Kompilator MSVC nigdy nie generuje tego.

  - ELEMENT_TYPE_CMOD_REQ jest reprezentowane jako "&#124;" i w pełni kwalifikowana nazwa klasy modyfikującej, po zmodyfikowanym typie. Kompilator MSVC nigdy nie generuje tego.

  - ELEMENT_TYPE_CMOD_OPT jest reprezentowane jako "!" i w pełni kwalifikowana nazwa klasy modyfikującej, po zmodyfikowanym typie.

  - ELEMENT_TYPE_SZARRAY jest reprezentowane jako "[]" po typie elementu tablicy.

  - ELEMENT_TYPE_GENERICARRAY jest reprezentowane jako "[?]" po typie elementu tablicy. Kompilator MSVC nigdy nie generuje tego.

  - ELEMENT_TYPE_ARRAY jest reprezentowane jako [*lowerbound*: `size` ,*lowerbound*: `size` ], gdzie liczba przecinków jest rangą 1, a dolne granice i rozmiar każdego wymiaru, jeśli są znane, są reprezentowane w postaci dziesiętnej. Jeśli Dolna granica nie zostanie określona, zostanie ona po prostu pominięta. Jeśli Dolna granica i rozmiar określonego wymiaru zostaną pominięte, znak ":" również zostanie pominięty. Na przykład tablica 2-wymiarową z 1 jako dolne granice i nieokreślone rozmiary to [1:, 1:].

  - ELEMENT_TYPE_FNPTR jest reprezentowana jako "= FUNC: `type` (*Signature*)", gdzie `type` jest typem zwracanym, a *Signature* to argumenty metody. Jeśli nie ma żadnych argumentów, nawiasy są pomijane. Kompilator MSVC nigdy nie generuje tego.

  Następujące składniki podpisu nie są reprezentowane, ponieważ nie są nigdy używane do odróżniania przeciążonych metod:

  - Konwencja wywoływania

  - Typ zwracany

  - ELEMENT_TYPE_SENTINEL

- W przypadku tylko operatorów konwersji wartość zwracana metody jest zaszyfrowana jako "~", po której następuje zwracany typ, jak poprzednio zakodowany.

- W przypadku typów ogólnych nazwa typu będzie następować przez cykl tylny, a następnie liczbę, która wskazuje liczbę parametrów typu ogólnego.  Przykład:

    ```xml
    <member name="T:MyClass`2">
    ```

  Dla typu, który jest zdefiniowany jako `public class MyClass<T, U>` .

  Dla metod przyjmujących typy ogólne jako parametry parametry typu generycznego są określane jako liczby poprzedzone znakami powrotuka (na przykład \` 0, \` 1).  Każda liczba reprezentująca notację tablicową opartą na zero dla ogólnych parametrów typu.

## <a name="example"></a>Przykład

W poniższych przykładach pokazano, jak można generować ciągi identyfikatorów dla klasy i jej elementów członkowskich.

```cpp
// xml_id_strings.cpp
// compile with: /clr /doc /LD
///
namespace N {
// "N:N"

   /// <see cref="System" />
   //  <see cref="N:System"/>
   ref class X {
   // "T:N.X"

   protected:
      ///
      !X(){}
      // "M:N.X.Finalize", destructor's representation in metadata

   public:
      ///
      X() {}
      // "M:N.X.#ctor"

      ///
      static X() {}
      // "M:N.X.#cctor"

      ///
      X(int i) {}
      // "M:N.X.#ctor(System.Int32)"

      ///
      ~X() {}
      // "M:N.X.Dispose", Dispose function representation in metadata

      ///
      System::String^ q;
      // "F:N.X.q"

      ///
      double PI;
      // "F:N.X.PI"

      ///
      int f() { return 1; }
      // "M:N.X.f"

      ///
      int bb(System::String ^ s, int % y, void * z) { return 1; }
      // "M:N.X.bb(System.String,System.Int32@,System.Void*)"

      ///
      int gg(array<short> ^ array1, array< int, 2 >^ IntArray) { return 0; }
      // "M:N.X.gg(System.Int16[], System.Int32[0:,0:])"

      ///
      static X^ operator+(X^ x, X^ xx) { return x; }
     // "M:N.X.op_Addition(N.X,N.X)"

      ///
      property int prop;
      // "M:N.X.prop"

      ///
      property int prop2 {
      // "P:N.X.prop2"

         ///
         int get() { return 0; }
         // M:N.X.get_prop2

         ///
         void set(int i) {}
         // M:N.X.set_prop2(System.Int32)
      }

      ///
      delegate void D(int i);
      // "T:N.X.D"

      ///
      event D ^ d;
      // "E:N.X.d"

      ///
      ref class Nested {};
      // "T:N.X.Nested"

      ///
      static explicit operator System::Int32 (X x) { return 1; }
      // "M:N.X.op_Explicit(N.X!System.Runtime.CompilerServices.IsByValue)~System.Int32"
   };
}
```

## <a name="see-also"></a>Zobacz też

[Dokumentacja XML](xml-documentation-visual-cpp.md)
