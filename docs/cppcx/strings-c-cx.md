---
description: 'Dowiedz się więcej o: ciągi (C++/CX)'
title: Ciągi (C++/CX)
ms.date: 01/22/2017
ms.assetid: 5b34e1df-7c2b-4269-aba8-b767d36c49d9
ms.openlocfilehash: 83ea4cd86b57e8bfd81968cbb617b7b8af81b978
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307616"
---
# <a name="strings-ccx"></a>Ciągi (C++/CX)

Tekst w środowisko wykonawcze systemu Windows jest reprezentowany w języku C++/CX przez [klasę platform:: String](../cppcx/platform-string-class.md). `Platform::String Class`W przypadku przekazywania ciągów z powrotem i do metod w klasach środowisko wykonawcze systemu Windows lub w przypadku korzystania z innych składników Środowisko wykonawcze systemu Windows na granicy interfejsu binarnego aplikacji (ABI). `Platform::String Class`Zapewnia metody dla kilku typowych operacji na ciągach, ale nie jest ona przeznaczona do obsługi w pełni funkcjonalnej klasy ciągów. W module języka C++ Użyj standardowych typów ciągów języka C++, takich jak [wstring](../standard-library/basic-string-class.md) , do dowolnego istotnego przetwarzania tekstu, a następnie przekonwertuj wynik końcowy na [platformę:: String ^](../cppcx/platform-string-class.md) przed przekazaniem go do lub z interfejsu publicznego. Konwersja między programami `wstring` lub `wchar_t*` i `Platform::String` .

**Szybki przebieg**

W niektórych przypadkach kompilator może sprawdzić, czy może bezpiecznie skonstruować `Platform::String` lub przekazać `String` do funkcji bez kopiowania danych ciągu bazowego. Takie operacje są nazywane *szybkim przebiegiem* i występują w sposób niewidoczny dla użytkownika.

## <a name="string-construction"></a>Konstrukcja ciągu

Wartość `String` obiektu jest niezmienne (tylko do odczytu) `char16` (16-bitowe znaki Unicode). Ponieważ `String` obiekt jest niezmienny, przypisanie nowego literału ciągu do `String` zmiennej faktycznie zastępuje oryginalny `String` obiekt nowym `String` obiektem. Operacje łączenia obejmują zniszczenie oryginalnego `String` obiektu i tworzenie nowego obiektu.

**Literały**

*Znak literału* jest znakiem, który jest ujęty w znaki pojedynczego cudzysłowu, a *ciąg literału* jest sekwencją znaków ujętych w znaki podwójnego cudzysłowu. Jeśli użyjesz literału w celu zainicjowania zmiennej ciągu ^ ^, kompilator zakłada, że literał zawiera `char16` znaki. Oznacza to, że nie trzeba poprzedzać literału modyfikatorem ciągu "L" ani ująć literału w makrze **_T ()** lub **tekstowym ()** . Aby uzyskać więcej informacji na temat obsługi języka Unicode w języku C++, zobacz [Podsumowanie programowania Unicode](../text/unicode-programming-summary.md).

Poniższy przykład przedstawia różne sposoby konstruowania `String` obiektów.

[!code-cpp[cx_strings#01](../cppcx/codesnippet/CPP/cppcx_strings/class1.cpp#01)]

## <a name="string-handling-operations"></a>Operacje obsługi ciągów

`String`Klasa zawiera metody i operatory umożliwiające łączenie, Porównywanie ciągów i wykonywanie innych podstawowych operacji na ciągach. Aby wykonać bardziej rozległe manipulowanie ciągami, użyj `String::Data()` funkcji elementu członkowskiego, aby pobrać wartość `String^` obiektu jako `const wchar_t*` . Następnie użyj tej wartości do zainicjowania `std::wstring` , która zapewnia funkcje obsługi ciągów rozbudowanych.

[!code-cpp[cx_strings#03](../cppcx/codesnippet/CPP/cppcx_strings/class1.cpp#03)]

## <a name="string-conversions"></a>Konwersje ciągów

`Platform::String`Może zawierać tylko `char16` znaki lub `NULL` znak. Jeśli aplikacja musi współpracować z znakami 8-bitowymi, użyj [ciągu::D ATA](../cppcx/platform-string-class.md#data) , aby wyodrębnić tekst jako `const wchar_t*` . Następnie można użyć odpowiednich funkcji systemu Windows lub standardowych funkcji biblioteki do działania na danych i przekonwertować ją z powrotem na `wchar_t*` lub [wstring](../standard-library/basic-string-class.md), których można użyć do utworzenia nowego `Platform::String` .

Poniższy fragment kodu przedstawia sposób konwersji `String^` zmiennej do i ze `wstring` zmiennej. Aby uzyskać więcej informacji na temat manipulowania ciągami używanymi w tym przykładzie, zobacz [basic_string:: Replace](../standard-library/basic-string-class.md#replace).

[!code-cpp[cx_strings#04](../cppcx/codesnippet/CPP/cppcx_strings/class1.cpp#04)]

## <a name="string-length-and-embedded-null-values"></a>Długość ciągu i osadzone wartości NULL

[Ciąg:: length](../cppcx/platform-string-class.md#length) zwraca liczbę znaków w ciągu, a nie liczbę bajtów. Kończący znak NULL nie jest liczony, chyba że zostanie jawnie określony podczas tworzenia ciągu przy użyciu semantyki stosu.

`Platform::String`Może zawierać osadzone wartości null, ale tylko wtedy, gdy wartość null jest wynikiem operacji łączenia. Osadzone wartości NULL nie są obsługiwane w literałach ciągu; w związku z tym nie można używać osadzonych wartości NULL w ten sposób, aby zainicjować `Platform::String` . Osadzone wartości NULL w elemencie `Platform::String` są ignorowane, gdy zostanie wyświetlony ciąg, na przykład, gdy zostanie przypisany do `TextBlock::Text` właściwości. Osadzone wartości NULL są usuwane, gdy wartość ciągu jest zwracana przez `Data` Właściwość.

## <a name="stringreference"></a>StringReference

W niektórych przypadkach kod (a) otrzymuje literał typu std:: wstring lub wchar_t lub L "", a po prostu przekazuje go do innej metody, która pobiera ciąg ^ jako parametr wejściowy. Tak długo, jak oryginalny bufor ciągu pozostanie ważny i nie zmienia się przed zwróceniem przez funkcję, można przekonwertować `wchar_t*` ciąg lub literał ciągu na [platformę:: StringReference](../cppcx/platform-stringreference-class.md)i przekazać go, zamiast `Platform::String^` . Jest to dozwolone `StringReference` , ponieważ ma zdefiniowaną przez użytkownika konwersję do `Platform::String^` . Za pomocą można `StringReference` uniknąć tworzenia dodatkowej kopii danych ciągu. W pętlach, w których przekazywana jest duża liczba ciągów lub podczas przekazywania bardzo dużych ciągów, można osiągnąć znaczącą poprawę wydajności przy użyciu programu `StringReference` . Ale ponieważ `StringReference` zasadniczo ponosi oryginalny bufor ciągu, należy użyć wyjątkowo zadbać, aby uniknąć uszkodzenia pamięci. Nie należy przekazywać `StringReference` do metody asynchronicznej, chyba że oryginalny ciąg musi znajdować się w zakresie, gdy ta metoda zwraca. Ciąg ^, który jest inicjowany z StringReference, wymusi alokację i kopię danych ciągu w przypadku wystąpienia drugiej operacji przypisania. W takim przypadku utracisz korzyść wydajności `StringReference` .

Należy pamiętać, że `StringReference` jest to standardowy typ klasy języka C++, a nie Klasa referencyjna, nie można używać go w publicznym interfejsie klas ref, które definiujesz.

Poniższy przykład pokazuje, jak używać StringReference:

```cpp
void GetDecodedStrings(std::vector<std::wstring> strings)
{
    using namespace Windows::Security::Cryptography;
    using namespace Windows::Storage::Streams;

    for (auto&& s : strings)
    {
        // Method signature is IBuffer^ CryptographicBuffer::DecodeFromBase64String (Platform::String^)
        // Call using StringReference:
        IBuffer^ buffer = CryptographicBuffer::DecodeFromBase64String(StringReference(s.c_str()));

        //...do something with buffer
    }
}
```
