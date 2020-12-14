---
description: 'Dowiedz się więcej o: wyrażenia regularne (C++/CLI)'
title: Wyrażenia regularne (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- regular expressions [C++]
- .NET Framework [C++], regular expressions
- regular expressions [C++], about regular expressions
- parsing strings [C++]
- examples [C++], strings
- regular expressions [C++], parsing strings
- Split method, parsing strings
- strings [C++], parsing
- substrings, simple matches
- searching, exact substring matches
- strings [C++], exact substring matching
- regular expressions [C++], simple matching
- IsMatch method
- strings [C++], extracting data from
- formatted strings [C++]
- regular expressions [C++], extracting data fields
- data [C++], extracting from strings
- regular expressions [C++], rearranging data
- data [C++], rearranging
- search and replace
- Replace method
- regular expressions [C++], search and replace
- strings [C++], formatting
- data [C++], formatting
- regular expressions [C++], validating data formatting
ms.assetid: 838bab49-0dbc-4089-a604-ef146269ef5a
ms.openlocfilehash: 429a121ec7acad46437a344b089f5c6a1ce4243b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245814"
---
# <a name="regular-expressions-ccli"></a>Wyrażenia regularne (C++/CLI)

Pokazuje różne operacje na ciągach używające klas wyrażeń regularnych w .NET Framework.

W poniższych tematach przedstawiono sposób korzystania z <xref:System.Text.RegularExpressions> przestrzeni nazw .NET Framework (i w jednym przypadku <xref:System.String.Split%2A?displayProperty=fullName> metody) do wyszukiwania, analizowania i modyfikowania ciągów.

## <a name="parse-strings-using-regular-expressions"></a><a name="parse_regex"></a> Analizowanie ciągów za pomocą wyrażeń regularnych

Poniższy przykład kodu demonstruje prostą analizę ciągu przy użyciu <xref:System.Text.RegularExpressions.Regex> klasy w <xref:System.Text.RegularExpressions?displayProperty=fullName> przestrzeni nazw. Tworzony jest ciąg zawierający wiele typów wyrazów delineators. Ten ciąg jest następnie analizowany przy użyciu <xref:System.Text.RegularExpressions.Regex> klasy w połączeniu z <xref:System.Text.RegularExpressions.Match> klasą. Następnie każdy wyraz w zdaniu jest wyświetlany osobno.

### <a name="example"></a>Przykład

```cpp
// regex_parse.cpp
// compile with: /clr
#using <system.dll>

using namespace System;
using namespace System::Text::RegularExpressions;

int main( )
{
   int words = 0;
   String^ pattern = "[a-zA-Z]*";
   Console::WriteLine( "pattern : '{0}'", pattern );
   Regex^ regex = gcnew Regex( pattern );

   String^ line = "one\ttwo three:four,five six  seven";
   Console::WriteLine( "text : '{0}'", line );
   for( Match^ match = regex->Match( line );
        match->Success; match = match->NextMatch( ) )
   {
      if( match->Value->Length > 0 )
      {
         words++;
         Console::WriteLine( "{0}", match->Value );
      }
   }
   Console::WriteLine( "Number of Words : {0}", words );

   return 0;
}
```

## <a name="parse-strings-using-the-split-method"></a><a name="parse_split"></a> Analizowanie ciągów za pomocą metody Split

Poniższy przykład kodu demonstruje użycie <xref:System.String.Split%2A?displayProperty=fullName> metody do wyodrębnienia każdego wyrazu z ciągu. Ciąg zawierający wiele typów wyrazów delineators jest skonstruowany, a następnie przeanalizowany przez wywołanie <xref:System.String.Split%2A> z listą delineators. Następnie każdy wyraz w zdaniu jest wyświetlany osobno.

### <a name="example"></a>Przykład

```cpp
// regex_split.cpp
// compile with: /clr
using namespace System;

int main()
{
   String^ delimStr = " ,.:\t";
   Console::WriteLine( "delimiter : '{0}'", delimStr );
   array<Char>^ delimiter = delimStr->ToCharArray( );
   array<String^>^ words;
   String^ line = "one\ttwo three:four,five six seven";

   Console::WriteLine( "text : '{0}'", line );
   words = line->Split( delimiter );
   Console::WriteLine( "Number of Words : {0}", words->Length );
   for (int word=0; word<words->Length; word++)
      Console::WriteLine( "{0}", words[word] );

   return 0;
}
```

## <a name="use-regular-expressions-for-simple-matching"></a><a name="regex_simple"></a> Używanie wyrażeń regularnych w przypadku prostego dopasowywania

Poniższy przykład kodu używa wyrażeń regularnych, aby wyszukać dokładne dopasowania podciągów. Wyszukiwanie jest wykonywane przez metodę statyczną <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> , która pobiera dwa ciągi jako dane wejściowe. Pierwszy jest ciągiem, który ma być przeszukiwany, a drugi to wzorzec, który ma być wyszukiwany.

### <a name="example"></a>Przykład

```cpp
// regex_simple.cpp
// compile with: /clr
#using <System.dll>

using namespace System;
using namespace System::Text::RegularExpressions;

int main()
{
   array<String^>^ sentence =
   {
      "cow over the moon",
      "Betsy the Cow",
      "cowering in the corner",
      "no match here"
   };

   String^ matchStr = "cow";
   for (int i=0; i<sentence->Length; i++)
   {
      Console::Write( "{0,24}", sentence[i] );
      if ( Regex::IsMatch( sentence[i], matchStr,
                     RegexOptions::IgnoreCase ) )
         Console::WriteLine("  (match for '{0}' found)", matchStr);
      else
         Console::WriteLine("");
   }
   return 0;
}
```

## <a name="use-regular-expressions-to-extract-data-fields"></a><a name="regex_extract"></a> Używanie wyrażeń regularnych do wyodrębniania pól danych

Poniższy przykład kodu demonstruje użycie wyrażeń regularnych w celu wyodrębnienia danych z sformatowanego ciągu. Poniższy przykład kodu używa klasy, <xref:System.Text.RegularExpressions.Regex> Aby określić wzorzec, który odpowiada adresowi e-mail. Ten Patter zawiera identyfikatory pól, których można użyć do pobrania części nazwy użytkownika i hosta z poszczególnych adresów e-mail. <xref:System.Text.RegularExpressions.Match>Klasa jest używana do wykonywania rzeczywistego dopasowania do wzorca. Jeśli dany adres e-mail jest prawidłowy, nazwy użytkownika i hosta są wyodrębniane i wyświetlane.

### <a name="example"></a>Przykład

```cpp
// Regex_extract.cpp
// compile with: /clr
#using <System.dll>

using namespace System;
using namespace System::Text::RegularExpressions;

int main()
{
    array<String^>^ address=
    {
        "jay@southridgevideo.com",
        "barry@adatum.com",
        "treyresearch.net",
        "karen@proseware.com"
    };

    Regex^ emailregex = gcnew Regex("(?<user>[^@]+)@(?<host>.+)");

    for (int i=0; i<address->Length; i++)
    {
        Match^ m = emailregex->Match( address[i] );
        Console::Write("\n{0,25}", address[i]);

        if ( m->Success )
        {
            Console::Write("   User='{0}'",
            m->Groups["user"]->Value);
            Console::Write("   Host='{0}'",
            m->Groups["host"]->Value);
        }
        else
            Console::Write("   (invalid email address)");
        }

    Console::WriteLine("");
    return 0;
}
```

## <a name="use-regular-expressions-to-rearrange-data"></a><a name="regex_rearrange"></a> Używanie wyrażeń regularnych do zmiany rozmieszczenia danych

Poniższy przykład kodu demonstruje, jak .NET Framework Obsługa wyrażeń regularnych może służyć do ponownego rozmieszczania lub formatowania danych. Poniższy przykład kodu używa <xref:System.Text.RegularExpressions.Regex> klas i, <xref:System.Text.RegularExpressions.Match> Aby wyodrębnić imiona i nazwiska z ciągu, a następnie wyświetlać te elementy w kolejności odwrotnej.

<xref:System.Text.RegularExpressions.Regex>Klasa jest używana do konstruowania wyrażenia regularnego opisującego bieżący format danych. Przyjmuje się, że dwie nazwy są rozdzielone przecinkami i mogą korzystać z dowolnej ilości wolnego miejsca wokół przecinka. <xref:System.Text.RegularExpressions.Match>Metoda jest następnie używana do analizowania każdego ciągu. Jeśli to się powiedzie, imiona i nazwiska są pobierane z <xref:System.Text.RegularExpressions.Match> obiektu i wyświetlane.

### <a name="example"></a>Przykład

```cpp
// regex_reorder.cpp
// compile with: /clr
#using <System.dll>
using namespace System;
using namespace Text::RegularExpressions;

int main()
{
   array<String^>^ name =
   {
      "Abolrous, Sam",
      "Berg,Matt",
      "Berry , Jo",
      "www.contoso.com"
   };

   Regex^ reg = gcnew Regex("(?<last>\\w*)\\s*,\\s*(?<first>\\w*)");

   for ( int i=0; i < name->Length; i++ )
   {
      Console::Write( "{0,-20}", name[i] );
      Match^ m = reg->Match( name[i] );
      if ( m->Success )
      {
         String^ first = m->Groups["first"]->Value;
         String^ last = m->Groups["last"]->Value;
         Console::WriteLine("{0} {1}", first, last);
      }
      else
         Console::WriteLine("(invalid)");
   }
   return 0;
}
```

## <a name="use-regular-expressions-to-search-and-replace"></a><a name="regex_search"></a> Używanie wyrażeń regularnych do wyszukiwania i zamieniania

Poniższy przykład kodu demonstruje, jak Klasa wyrażenia regularnego <xref:System.Text.RegularExpressions.Regex> może służyć do wykonywania wyszukiwania i zamieniania. Jest to realizowane za pomocą <xref:System.Text.RegularExpressions.Regex.Replace%2A> metody. Używana wersja pobiera dwa ciągi jako dane wejściowe: ciąg do zmodyfikowania i ciąg, który ma zostać wstawiony zamiast sekcji (jeśli istnieją), które pasują do wzorca danego <xref:System.Text.RegularExpressions.Regex> obiektu.

Ten kod zastępuje wszystkie cyfry w ciągu znakami podkreślenia (_), a następnie zastępuje je ciągiem pustym i skutecznie je usuwając. Ten sam efekt można wykonać w jednym kroku, ale w celach demonstracyjnych użyto dwóch kroków.

### <a name="example"></a>Przykład

```cpp
// regex_replace.cpp
// compile with: /clr
#using <System.dll>
using namespace System::Text::RegularExpressions;
using namespace System;

int main()
{
   String^ before = "The q43uick bro254wn f0ox ju4mped";
   Console::WriteLine("original  : {0}", before);

   Regex^ digitRegex = gcnew Regex("(?<digit>[0-9])");
   String^ after = digitRegex->Replace(before, "_");
   Console::WriteLine("1st regex : {0}", after);

   Regex^ underbarRegex = gcnew Regex("_");
   String^ after2 = underbarRegex->Replace(after, "");
   Console::WriteLine("2nd regex : {0}", after2);

   return 0;
}
```

## <a name="use-regular-expressions-to-validate-data-formatting"></a><a name="regex_validate"></a> Używanie wyrażeń regularnych do sprawdzania poprawności formatowania danych

Poniższy przykład kodu demonstruje użycie wyrażeń regularnych w celu sprawdzenia formatowania ciągu. W poniższym przykładzie kodu ciąg powinien zawierać prawidłowy numer telefonu. Poniższy przykład kodu używa ciągu "\d {3} -\d {3} -\d {4} ", aby wskazać, że każde pole reprezentuje prawidłowy numer telefonu. "D" w ciągu wskazuje cyfrę, a argument po każdej "d" wskazuje liczbę cyfr, które muszą być obecne. W takim przypadku liczba jest wymagana do rozdzielenia przez łączniki.

### <a name="example"></a>Przykład

```cpp
// regex_validate.cpp
// compile with: /clr
#using <System.dll>

using namespace System;
using namespace Text::RegularExpressions;

int main()
{
   array<String^>^ number =
   {
      "123-456-7890",
      "444-234-22450",
      "690-203-6578",
      "146-893-232",
      "146-839-2322",
      "4007-295-1111",
      "407-295-1111",
      "407-2-5555",
   };

   String^ regStr = "^\\d{3}-\\d{3}-\\d{4}$";

   for ( int i = 0; i < number->Length; i++ )
   {
      Console::Write( "{0,14}", number[i] );

      if ( Regex::IsMatch( number[i], regStr ) )
         Console::WriteLine(" - valid");
      else
         Console::WriteLine(" - invalid");
   }
   return 0;
}
```

## <a name="related-sections"></a>Sekcje pokrewne

[.NET Framework — Wyrażenia regularne](/dotnet/standard/base-types/regular-expressions)

## <a name="see-also"></a>Zobacz też

[Programowanie .NET w języku C++/interfejsie wiersza polecenia (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
