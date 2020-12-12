---
description: 'Dowiedz się więcej o: wywoływanie funkcji natywnych z kodu zarządzanego'
title: Wywoływanie funkcji natywnych z kodu zarządzanego
ms.date: 11/04/2016
helpviewer_keywords:
- native functions called from managed code [C++]
- managed code [C++], interoperability
- platform invoke [C++], interoperability
- interoperabiliy [C++], calling native functions from managed code
- calling native functions from managed code
- interop [C++], calling native functions from managed code
ms.assetid: 982cef18-20d9-42b4-8242-a77fa65f2e36
ms.openlocfilehash: b037027f863ff12ac83429715cdf50bff4549a93
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97282539"
---
# <a name="calling-native-functions-from-managed-code"></a>Wywoływanie funkcji natywnych z kodu zarządzanego

Środowisko uruchomieniowe języka wspólnego udostępnia usługi wywołań platformy, czyli funkcję PInvoke, która umożliwia kodowi zarządzanemu wywoływanie funkcji w stylu C w natywnych bibliotekach połączonych dynamicznie (dll). Takie samo kierowanie danych jest używane jak w przypadku współdziałania modelu COM z środowiskiem uruchomieniowym oraz dla "działa po prostu" lub IJW.

Aby uzyskać więcej informacji, zobacz:

- [Używanie jawnej funkcji PInvoke w języku C++ (atrybut DllImport)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)

- [Korzystanie z międzyoperacyjności języka C++ (niejawne PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)

Przykłady w tej sekcji ilustrują jak `PInvoke` można użyć. `PInvoke` może uprościć niestandardowe kierowanie danych, ponieważ udostępniają one informacje o kierowaniu w atrybutach zamiast pisania kodu kierującego procedurami.

> [!NOTE]
> Biblioteka Marshal oferuje alternatywny sposób organizowania danych między środowiskami macierzystymi i zarządzanymi w zoptymalizowany sposób. Więcej informacji o bibliotece Marshal można znaleźć [w temacie Omówienie organizowania w języku C++](../dotnet/overview-of-marshaling-in-cpp.md) . Biblioteka Marshal jest użyteczna tylko w przypadku danych, a nie dla funkcji.

## <a name="pinvoke-and-the-dllimport-attribute"></a>PInvoke i atrybut DllImport

W poniższym przykładzie pokazano sposób użycia programu `PInvoke` w programie Visual C++. Funkcja natywna jest definiowana w msvcrt.dll. Atrybut DllImport jest używany dla deklaracji elementów Put.

```cpp
// platform_invocation_services.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

[DllImport("msvcrt", CharSet=CharSet::Ansi)]
extern "C" int puts(String ^);

int main() {
   String ^ pStr = "Hello World!";
   puts(pStr);
}
```

Poniższy przykład jest równoważny z poprzednim przykładem, ale używa IJW.

```cpp
// platform_invocation_services_2.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

#include <stdio.h>

int main() {
   String ^ pStr = "Hello World!";
   char* pChars = (char*)Marshal::StringToHGlobalAnsi(pStr).ToPointer();
   puts(pChars);

   Marshal::FreeHGlobal((IntPtr)pChars);
}
```

### <a name="advantages-of-ijw"></a>Zalety IJW

- Nie ma potrzeby zapisywania `DLLImport` deklaracji atrybutów dla niezarządzanych interfejsów API używanych przez program. Po prostu Dołącz plik nagłówka i Połącz z biblioteką importu.

- Mechanizm IJW jest nieco szybszy (na przykład w przypadku wycinków IJW nie trzeba sprawdzać potrzeby przypinania lub kopiowania elementów danych, ponieważ są one wykonywane jawnie przez dewelopera).

- Jasno ilustruje to problemy z wydajnością. W tym przypadku jest to fakt, że tłumaczenie z ciągu Unicode na ciąg ANSI oraz że masz przydzieloną pamięć i cofa alokację. W takim przypadku programista piszący kod przy użyciu IJW mógłby spowodować, że wywołanie `_putws` i użycie `PtrToStringChars` byłyby lepszym rozwiązaniem dla wydajności.

- Jeśli wywołasz wiele niezarządzanych interfejsów API przy użyciu tych samych danych, przeorganizuje ją raz i przekazanie kopii zorganizowanej jest znacznie bardziej wydajne niż w każdym momencie.

### <a name="disadvantages-of-ijw"></a>Wady IJW

- Kierowanie musi być jawnie określone w kodzie zamiast według atrybutów (które często mają odpowiednie ustawienia domyślne).

- Kod kierujący jest wbudowany, gdzie bardziej inwazyjny w przepływie logiki aplikacji.

- Ze względu na to, że jawne kierowanie interfejsów API zwraca `IntPtr` typy dla 32-bitowych do 64-bitowych przenośności, należy użyć dodatkowych `ToPointer` wywołań.

Konkretną metodą uwidocznioną przez C++ jest bardziej wydajna, jawna Metoda, która jest kosztem pewnej dodatkowej złożoności.

Jeśli aplikacja używa głównie niezarządzanych typów danych lub wywołuje więcej niezarządzanych interfejsów API niż .NET Framework interfejsów API, zalecamy użycie funkcji IJW. Aby wywołać sporadyczny niezarządzany interfejs API w większości zarządzanej aplikacji, wybór jest bardziej delikatny.

## <a name="pinvoke-with-windows-apis"></a>Funkcje PInvoke z interfejsami API systemu Windows

Funkcja PInvoke jest wygodna do wywoływania funkcji w systemie Windows.

W tym przykładzie program Visual C++ współdziała z funkcją MessageBox, która jest częścią Win32 API.

```cpp
// platform_invocation_services_4.cpp
// compile with: /clr /c
using namespace System;
using namespace System::Runtime::InteropServices;
typedef void* HWND;
[DllImport("user32", CharSet=CharSet::Ansi)]
extern "C" int MessageBox(HWND hWnd, String ^ pText, String ^ pCaption, unsigned int uType);

int main() {
   String ^ pText = "Hello World! ";
   String ^ pCaption = "PInvoke Test";
   MessageBox(0, pText, pCaption, 0);
}
```

Dane wyjściowe to okno komunikatu z tytułem test PInvoke i zawiera tekst Hello world!.

Informacje o kierowaniu są również używane przez funkcję PInvoke do wyszukiwania funkcji w bibliotece DLL. W user32.dll nie ma żadnej funkcji MessageBox, ale CharSet = CharSet:: ANSI włącza funkcję PInvoke, która używa klasy MessageBox, zamiast MessageBoxW, która jest wersją Unicode. Ogólnie rzecz biorąc, zalecamy korzystanie z wersji Unicode niezarządzanych interfejsów API, ponieważ eliminuje to obciążenie związane z translacją z natywnego formatu Unicode .NET Framework obiektów String do ANSI.

## <a name="when-not-to-use-pinvoke"></a>Kiedy nie używać funkcji PInvoke

Używanie funkcji PInvoke nie jest odpowiednie dla wszystkich funkcje w stylu C w bibliotekach DLL. Załóżmy na przykład, że istnieje funkcja MakeSpecial w mylib.dll zadeklarowana w następujący sposób:

`char * MakeSpecial(char * pszString);`

Jeśli używamy funkcji PInvoke w aplikacji Visual C++, możemy napisać coś podobnego do poniższego:

```cpp
[DllImport("mylib")]
extern "C" String * MakeSpecial([MarshalAs(UnmanagedType::LPStr)] String ^);
```

Trudności nie można usunąć pamięci dla niezarządzanego ciągu zwracanego przez MakeSpecial. Inne funkcje wywoływane za pomocą funkcji PInvoke zwracają wskaźnik do wewnętrznego bufora, który nie musi zostać cofnięty alokacją przez użytkownika. W takim przypadku jest to oczywisty wybór przy użyciu funkcji IJW.

## <a name="limitations-of-pinvoke"></a>Ograniczenia PInvoke

Nie można zwrócić tego samego dokładnego wskaźnika z funkcji natywnej, która została wykonana jako parametr. Jeśli funkcja natywna zwraca wskaźnik, który został zorganizowany do niego przez PInvoke, uszkodzenie pamięci i wyjątki mogą być nastąpi.

```cpp
__declspec(dllexport)
char* fstringA(char* param) {
   return param;
}
```

Poniższy przykład przedstawia ten problem, a mimo że program może wydawać poprawne dane wyjściowe, dane wyjściowe pochodzą z pamięci, która została zwolniona.

```cpp
// platform_invocation_services_5.cpp
// compile with: /clr /c
using namespace System;
using namespace System::Runtime::InteropServices;
#include <limits.h>

ref struct MyPInvokeWrap {
public:
   [ DllImport("user32.dll", EntryPoint = "CharLower", CharSet = CharSet::Ansi) ]
   static String^ CharLower([In, Out] String ^);
};

int main() {
   String ^ strout = "AabCc";
   Console::WriteLine(strout);
   strout = MyPInvokeWrap::CharLower(strout);
   Console::WriteLine(strout);
}
```

## <a name="marshaling-arguments"></a>Kierowanie argumentów

W programie `PInvoke` nie jest wymagana kierowanie między typami zarządzanymi i natywnymi macierzystymi języka C++ z tym samym formularzem. Na przykład nie jest wymagane kierowanie między Int32 i int ani między Double i Double.

Należy jednak zorganizować typy, które nie mają tego samego formularza. Obejmuje to char, String i typy struktur. W poniższej tabeli przedstawiono mapowania używane przez organizatora dla różnych typów:

|wtypes. h|Visual C++|Visual C++ z/CLR|Środowisko uruchomieniowe języka wspólnego|
|--------------|------------------|-----------------------------|-----------------------------|
|UCHWYTY|pozycję \*|pozycję \*|IntPtr, UIntPtr|
|BYTE|unsigned char|unsigned char|Byte|
|WYBIERAK|short|short|Int16|
|WORD|unsigned short|unsigned short|UInt16|
|INT|int|int|Int32|
|UINT|unsigned int|unsigned int|UInt32|
|DŁUGO|długi|długi|Int32|
|LOGICZNA|długi|bool|Wartość logiczna|
|DWORD|unsigned long|unsigned long|UInt32|
|ULONG|unsigned long|unsigned long|UInt32|
|DELIKATN|char|char|Char|
|LPSTR|delikatn \*|Ciąg ^ [w], StringBuilder ^ [in, out]|Ciąg ^ [w], StringBuilder ^ [in, out]|
|LPCSTR|const — znak \*|Ciąg ^|Ciąg|
|LPWSTR|wchar_t \*|Ciąg ^ [w], StringBuilder ^ [in, out]|Ciąg ^ [w], StringBuilder ^ [in, out]|
|LPCWSTR|stała wchar_t \*|Ciąg ^|Ciąg|
|FLOAT|float|float|Pojedyncze|
|DOUBLE|double|double|Double|

Organizator automatycznie przypina pamięć przydzieloną na stercie środowiska uruchomieniowego, jeśli jego adres jest przekazywany do niezarządzanej funkcji. Przypinanie uniemożliwia przechodzenie przez moduł wyrzucania elementów bezużytecznych z przydzielonym blokiem pamięci podczas kompaktowania.

W przykładzie przedstawionym wcześniej w tym temacie, parametr CharSet elementu DllImport określa sposób organizowania ciągów zarządzanych; w takim przypadku powinny być przekazywane do ciągów ANSI dla strony natywnej.

Można określić informacje o kierowaniu dla pojedynczych argumentów funkcji natywnej przy użyciu atrybutu MarshalAs. Istnieje kilka opcji organizowania \* argumentu ciągu: BSTR, ANSIBStr, TBStr, LPStr, LPWStr i LPTStr. Wartość domyślna to LPStr.

W tym przykładzie ciąg jest zorganizowany jako dwubajtowy ciąg znaków Unicode, LPWStr. Dane wyjściowe są pierwszą literą Hello world! ponieważ drugi bajt ciągu organizowanego ma wartość null, a wartości są interpretowane jako znacznik końca ciągu.

```cpp
// platform_invocation_services_3.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

[DllImport("msvcrt", EntryPoint="puts")]
extern "C" int puts([MarshalAs(UnmanagedType::LPWStr)] String ^);

int main() {
   String ^ pStr = "Hello World!";
   puts(pStr);
}
```

Atrybut MarshalAs znajduje się w przestrzeni nazw System:: Runtime:: InteropServices. Ten atrybut może być używany z innymi typami danych, takimi jak tablice.

Jak wspomniano wcześniej w temacie, biblioteka marshaler udostępnia nową, zoptymalizowaną metodę organizowania danych między środowiskami macierzystymi i zarządzanymi. Aby uzyskać więcej informacji, zobacz [Omówienie organizowania w języku C++](../dotnet/overview-of-marshaling-in-cpp.md).

## <a name="performance-considerations"></a>Zagadnienia dotyczące wydajności

Element PInvoke ma narzuty z przedziału od 10 do 30 USD instrukcji dla każdego wywołania. Poza tym stałym kosztem kierowanie powoduje utworzenie dodatkowych kosztów. Nie ma kosztu kierowania między typami danych kopiowalnych, które mają taką samą reprezentację w kodzie zarządzanym i niezarządzanym. Na przykład nie ma kosztu do przetłumaczenia między int i Int32.

W celu uzyskania lepszej wydajności należy mieć mniejszą liczbę wywołań PInvoke, które umożliwiają kierowanie możliwie największej ilości danych, a nie większą liczbę wywołań, które dzielą mniejsze ilości danych na wywołanie.

## <a name="see-also"></a>Zobacz też

[Współdziałanie natywne i .NET](../dotnet/native-and-dotnet-interoperability.md)
