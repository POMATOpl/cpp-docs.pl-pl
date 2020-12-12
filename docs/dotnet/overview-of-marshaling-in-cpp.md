---
description: 'Dowiedz się więcej o: przegląd organizowania w języku C++/CLI'
title: Omówienie marshalingu w języku C++
ms.date: 07/12/2019
ms.topic: reference
f1_keywords:
- marshaling
- marshalling
helpviewer_keywords:
- Visual C++, marshaling
- C++ Support Library, marshaling
- marshaling, about marshaling
ms.assetid: 997dd4bc-5f98-408f-b890-f35de9ce3bb8
ms.openlocfilehash: 35294a204d338087a609746e6ae2e5e07ea07b59
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97255538"
---
# <a name="overview-of-marshaling-in-ccli"></a>Omówienie organizowania w języku C++/CLI

W trybie mieszanym czasami trzeba zorganizować dane między typami natywnymi i zarządzanymi. *Biblioteka organizowania* ułatwia organizowanie i konwertowanie danych w prosty sposób.  Biblioteka Marshal składa się z zestawu funkcji i `marshal_context` klasy, która wykonuje kierowanie dla typów wspólnych. Biblioteka jest zdefiniowana w tych nagłówkach w katalogu **include/msclr** dla wersji programu Visual Studio:

|Nagłówek|Opis|
|---------------|-----------------|
|Marshal. h|`marshal_context` funkcje organizowania klasy i kontekstu|
|marshal_atl. h| Funkcje do organizowania typów ATL|
|marshal_cppstd. h|Funkcje organizowania standardowych typów języka C++|
|marshal_windows. h|Funkcje do organizowania typów systemu Windows|

Ścieżka domyślna folderu **msclr** jest taka sama jak w zależności od wersji i numeru kompilacji:

```cmd
C:\\Program Files (x86)\\Microsoft Visual Studio\\Preview\\Enterprise\\VC\\Tools\\MSVC\\14.15.26528\\include\\msclr
```

Biblioteka Marshal może być używana z [klasą marshal_context](../dotnet/marshal-context-class.md)lub bez niej. Niektóre konwersje wymagają kontekstu. Inne konwersje można zaimplementować przy użyciu funkcji [marshal_as](../dotnet/marshal-as.md) . W poniższej tabeli wymieniono bieżące konwersje obsługiwane, niezależnie od tego, czy wymagają one kontekstu, oraz jaki plik organizacyjny należy uwzględnić:

|Typ z|Do typu|Marshal — Metoda|Plik dołączany|
|---------------|-------------|--------------------|------------------|
|System:: String ^|const — znak \*|marshal_context|Marshal. h|
|const — znak \*|System:: String ^|marshal_as|Marshal. h|
|delikatn \*|System:: String ^|marshal_as|Marshal. h|
|System:: String ^|stała wchar_t\*|marshal_context|Marshal. h|
|stała wchar_t \*|System:: String ^|marshal_as|Marshal. h|
|wchar_t \*|System:: String ^|marshal_as|Marshal. h|
|System:: IntPtr|UCHWYTY|marshal_as|marshal_windows. h|
|UCHWYTY|System:: IntPtr|marshal_as|marshal_windows. h|
|System:: String ^|ANI|marshal_context|marshal_windows. h|
|ANI|System:: String ^|marshal_as|Marshal. h|
|System:: String ^|bstr_t|marshal_as|marshal_windows. h|
|bstr_t|System:: String ^|marshal_as|marshal_windows. h|
|System:: String ^|std:: String|marshal_as|marshal_cppstd. h|
|std:: String|System:: String ^|marshal_as|marshal_cppstd. h|
|System:: String ^|std:: wstring|marshal_as|marshal_cppstd. h|
|std:: wstring|System:: String ^|marshal_as|marshal_cppstd. h|
|System:: String ^|CStringT\<char>|marshal_as|marshal_atl. h|
|CStringT\<char>|System:: String ^|marshal_as|marshal_atl. h|
|System:: String ^|CStringT<wchar_t>|marshal_as|marshal_atl. h|
|CStringT<wchar_t>|System:: String ^|marshal_as|marshal_atl. h|
|System:: String ^|CComBSTR|marshal_as|marshal_atl. h|
|CComBSTR|System:: String ^|marshal_as|marshal_atl. h|

Kierowanie wymaga kontekstu tylko wtedy, gdy jest organizowane z typów danych zarządzanych do natywnych, a natywny typ, który jest konwertowany, nie ma destruktora do automatycznego czyszczenia. Kontekst organizowania niszczy przydzielony natywny typ danych w jego destruktorze. W związku z tym konwersje wymagające kontekstu będą prawidłowe tylko do momentu usunięcia kontekstu. Aby zapisać wartości organizacyjne, należy skopiować wartości do własnych zmiennych.

> [!NOTE]
> Jeśli w ciągu występuje osadzona `NULL` wartość s, wynik organizowania ciągu nie jest gwarantowany. Osadzenie `NULL` s może spowodować obcięcie ciągu lub być zachowane.

Ten przykład pokazuje, jak uwzględnić katalog msclr w deklaracji nagłówka include:

`#include "msclr\marshal_cppstd.h"`

Biblioteka organizowania jest rozszerzalna, aby można było dodać własne typy organizowania. Aby uzyskać więcej informacji na temat rozszerzania biblioteki Marshaling, zobacz [How to: rozszerzanie biblioteki Marshaling](../dotnet/how-to-extend-the-marshaling-library.md).

## <a name="see-also"></a>Zobacz też

[Biblioteka obsługi języka C++](../dotnet/cpp-support-library.md)<br/>
[Instrukcje: rozszerzona biblioteka organizowania](../dotnet/how-to-extend-the-marshaling-library.md)
