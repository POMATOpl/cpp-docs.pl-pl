---
description: 'Dowiedz się więcej o: atrybuty metod'
title: Atrybuty metody (C++ COM)
ms.date: 10/02/2018
helpviewer_keywords:
- method attributes
- attributes [C++/CLI], reference topics
ms.assetid: b2313352-480d-488b-8c35-6242ffd3a549
ms.openlocfilehash: 29acb1f92b01e85960bc727c9b3e91f9a52732d5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327494"
---
# <a name="method-attributes"></a>Atrybuty metody

Następujące atrybuty mają zastosowanie do metod w klasie, klasie coclass lub interfejsie.

|Atrybut|Opis|
|---------------|-----------------|
|[bindable](bindable.md)|Wskazuje, że właściwość obsługuje powiązanie danych.|
|[call_as](call-as.md)|Umożliwia zamapowanie funkcji niezdalnych na funkcję zdalną.|
|[celnej](custom-cpp.md)|Umożliwia zdefiniowanie własnego atrybutu.|
|[db_column](db-column.md)|Wiąże określoną kolumnę z zestawem wierszy.|
|[db_command](db-command.md)|Tworzy polecenie OLE DB.|
|[db_param](db-param.md)|Kojarzy określoną zmienną członkowską z parametrem wejściowym lub wyjściowym i ogranicza zmienną.|
|[db_source](db-source.md)|Tworzy połączenie ze źródłem danych.|
|[db_table](db-table.md)|Otwiera tabelę OLE DB.|
|[defaultbind](defaultbind.md)|Wskazuje pojedynczą, możliwą do powiązania właściwość, która najlepiej reprezentuje obiekt.|
|[defaultcollelem](defaultcollelem.md)|Używane do optymalizacji kodu Visual Basic.|
|[displaybind](displaybind.md)|Wskazuje właściwość, która powinna być wyświetlana użytkownikowi jako możliwy do powiązania.|
|[helpcontext](helpcontext.md)|Określa identyfikator kontekstu, który umożliwia użytkownikowi wyświetlanie informacji o tym elemencie w pliku **pomocy** .|
|[helpfile](helpfile.md)|Ustawia nazwę pliku **pomocy** dla biblioteki typów.|
|[helpstring](helpstring.md)|Określa ciąg znaków, który jest używany do opisania elementu, do którego ma zastosowanie.|
|[helpstringcontext](helpstringcontext.md)|Określa identyfikator tematu pomocy w pliku HLP lub chm.|
|[helpstringdll](helpstringdll.md)|Określa nazwę biblioteki DLL, która ma być używana do przeszukiwania ciągu dokumentu (lokalizacja).|
|[ukryte](hidden.md)|Wskazuje, że element istnieje, ale nie powinien być wyświetlany w przeglądarce zorientowanej na użytkownika.|
|[id](id.md)|Określa identyfikator DISPID dla funkcji składowej (właściwości lub metody w interfejsie lub dispinterface).|
|[immediatebind](immediatebind.md)|Wskazuje, że baza danych zostanie natychmiast powiadomiona o wszystkich zmianach właściwości obiektu powiązanego z danymi.|
|[podczas](in-cpp.md)|Wskazuje, że parametr ma być przekazywać z procedury wywołującej do procedury wywoływanej.|
|[LAN](local-cpp.md)|Umożliwia użycie kompilatora MIDL jako generatora nagłówka, gdy jest używany w nagłówku interfejsu. W przypadku użycia w pojedynczej funkcji określa procedurę lokalną, dla której nie są generowane żadne wycinki.|
|[nonbrowsable](nonbrowsable.md)|Wskazuje, że element członkowski interfejsu nie powinien być wyświetlany w przeglądarce właściwości.|
|[propget](propget.md)|Określa funkcję akcesora właściwości.|
|[propput](propput.md)|Określa funkcję ustawienia właściwości.|
|[propputref](propputref.md)|Określa funkcję ustawienia właściwości, która używa odwołania zamiast wartości.|
|[ptr](ptr.md)|Wyznacza wskaźnik jako pełny wskaźnik.|
|[zakresu](range-cpp.md)|Określa zakres dozwolonych wartości dla argumentów lub pól, których wartości są ustawiane w czasie wykonywania.|
|[requestedit](requestedit.md)|Wskazuje, że właściwość obsługuje `OnRequestEdit` powiadomienie.|
|[podlega](restricted.md)|Określa, że element członkowski modułu, interfejsu lub dispinterface nie może zostać wywołany arbitralnie.|
|[satype](satype.md)|Określa typ danych `SAFEARRAY` struktury.|
|[zewnętrz](source-cpp.md)|Określa interfejsy źródłowe kontrolki dla punktów połączenia w klasie. W właściwości lub metodzie `source` atrybut wskazuje, że element członkowski zwraca obiekt lub wariant, który jest źródłem zdarzeń.|
|[synchronize](synchronize.md)|Synchronizuje dostęp do metody docelowej.|
|[vararg](vararg.md)|Określa, że funkcja przyjmuje zmienną liczbę argumentów.|

## <a name="see-also"></a>Zobacz też

[Atrybuty według użycia](attributes-by-usage.md)
