---
description: Dowiedz się więcej na temat:/GS (sprawdzanie zabezpieczeń bufora)
title: /GS (Sprawdzanie zabezpieczeń bufora)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLWCECompilerTool.BufferSecurityCheck
- VC.Project.VCCLCompilerTool.BufferSecurityCheck
helpviewer_keywords:
- buffers [C++], buffer overruns
- buffer overruns, compiler /GS switch
- GS compiler option [C++]
- /GS compiler option [C++]
- security check compiler option [C++]
- -GS compiler option [C++]
- buffers [C++], avoiding overruns
ms.assetid: 8d8a5ea1-cd5e-42e1-bc36-66e1cd7e731e
ms.openlocfilehash: 4d7fa3c2220260914c9ff931c2f2e7c76bf12ea1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191878"
---
# <a name="gs-buffer-security-check"></a>/GS (Sprawdzanie zabezpieczeń bufora)

Wykrywa niektóre przepełnienia buforów, które zastępują adres zwrotny funkcji, adres aparatu obsługi wyjątków lub niektóre typy parametrów. Przepełnianie buforu to technika używana przez hakerów do wykorzystywania luk w kodzie, który nie wymusza ograniczeń rozmiaru buforu.

## <a name="syntax"></a>Składnia

```
/GS[-]
```

## <a name="remarks"></a>Uwagi

**/GS** jest domyślnie włączony. Jeśli oczekujesz, że aplikacja nie ma żadnych zagrożeń bezpieczeństwa, użyj **/GS-**. Aby uzyskać więcej informacji na temat pomijania wykrywania przepełnienia buforu, zobacz [safebuffers](../../cpp/safebuffers.md).

## <a name="security-checks"></a>Sprawdzanie zabezpieczeń

W funkcjach, które kompilator uznaje za zagrożone problemem przepełnienia buforu, przydziela miejsce w stosie przed adresem zwrotnym. W przypadku wpisu funkcji przydzieloną przestrzeń jest ładowana z *plikiem cookie zabezpieczeń* , który jest obliczany raz podczas ładowania modułu. Podczas zamykania funkcji oraz podczas usuwania ramek ze stosu (unwinding) w 64-bitowych systemach operacyjnych następuje wywołanie funkcji pomocnika, która sprawdza, czy wartość pliku cookie jest wciąż taka sama. Inna wartość wskazuje, że mogło dojść do zastąpienia stosu. Wykrycie innej wartości powoduje przerwanie procesu.

## <a name="gs-buffers"></a>Bufory GS

Sprawdzanie zabezpieczeń przepełnienia buforu jest wykonywane w *buforze GS*. Buforem GS może być jeden z następujących obiektów:

- Tablica, która jest większa niż 4 bajty, ma więcej niż dwa elementy oraz zawiera element typu innego niż wskaźnik.

- Struktura danych, która ma więcej niż 8 bajtów i nie zawiera żadnych wskaźników.

- Bufor przydzielony przy użyciu funkcji [_alloca](../../c-runtime-library/reference/alloca.md) .

- Dowolna klasa lub struktura zawierająca bufor GS.

Na przykład poniższe instrukcje deklarują bufory GS.

```cpp
char buffer[20];
int buffer[20];
struct { int a; int b; int c; int d; } myStruct;
struct { int a; char buf[20]; };
```

Natomiast następujące instrukcje nie deklarują buforów GS. Dwie pierwsze deklaracje zawierają elementy będące wskaźnikami. Instrukcje trzecia i czwarta deklarują tablice, które są za małe. Piąta instrukcja deklaruje strukturę, której rozmiar na platformie x86 jest nie większy niż 8 bajtów.

```cpp
char *pBuf[20];
void *pv[20];
char buf[4];
int buf[2];
struct { int a; int b; };
```

## <a name="initialize-the-security-cookie"></a>Inicjowanie pliku cookie zabezpieczeń

Opcja kompilatora **/GS** wymaga, aby plik cookie zabezpieczeń został zainicjowany przed uruchomieniem jakiejkolwiek funkcji korzystającej z pliku cookie. Plik cookie zabezpieczeń musi być zainicjowany natychmiast po wprowadzeniu do pliku EXE lub DLL. Jest to wykonywane automatycznie w przypadku używania domyślnych punktów wejścia VCRuntime: mainCRTStartup, wmainCRTStartup, WinMainCRTStartup, wWinMainCRTStartup lub _DllMainCRTStartup. W przypadku korzystania z alternatywnego punktu wejścia należy ręcznie zainicjować plik cookie zabezpieczeń, wywołując [__security_init_cookie](../../c-runtime-library/reference/security-init-cookie.md).

## <a name="what-is-protected"></a>Co obejmuje ochrona

Opcja kompilatora **/GS** chroni następujące elementy:

- Adres zwrotny wywołania funkcji.

- Adres aparatu obsługi wyjątków funkcji.

- Zagrożone parametry funkcji.

Na wszystkich platformach **/GS** próbuje wykryć przepełnienia buforu w adresie zwrotnym. Przepełnienia buforów łatwiej wykonać na platformach takich jak x86 i x64, ponieważ używają one konwencji wywoływania, które przechowują adresy zwrotne wywołań funkcji w stosach.

Jeśli na platformie x86 funkcja używa aparatu obsługi wyjątków, kompilator wprowadza plik cookie zabezpieczeń chroniący adres tego aparatu. Plik cookie jest sprawdzany w trakcie usuwania ramek ze stosu.

**/GS** chroni *zagrożone parametry* , które są przesyłane do funkcji. Do takich parametrów zalicza się wskaźniki, odwołania do składni języka C++, struktury języka C (typu C++ POD) zawierające wskaźniki oraz bufory GS.

Parametr zagrożony jest przydzielany przed plikiem cookie i lokalnymi zmiennymi. Przepełnienie buforu może spowodować zastąpienie tych parametrów. Wtedy kod w funkcji wykorzystującej te parametry może doprowadzić do ataku, zanim funkcja zwróci wartość i zostanie wykonane sprawdzanie zabezpieczeń. Aby ograniczyć to zagrożenie, kompilator tworzy kopię zagrożonych parametrów w trakcie prologu funkcji i umieszcza je w obszarze pamięci masowej wykorzystywanym przez bufory.

Kompilator nie tworzy kopii zagrożonych parametrów w następujących sytuacjach:

- Funkcje, które nie zawierają buforu GS.

- Optymalizacje ([Opcje/o](o-options-optimize-code.md)) nie są włączone.

- Funkcje o zmiennej liczbie argumentów (...).

- Funkcje, które są oznaczone [](../../cpp/naked-cpp.md)jako wykorzystane.

- Funkcje, które w pierwszej instrukcji zawierają wbudowany kod zestawu.

- Parametr jest wykorzystywany tylko na sposoby stanowiące mniejsze zagrożenie w razie przepełnienia buforu.

## <a name="what-is-not-protected"></a>Czego nie obejmuje ochrona

Opcja kompilatora **/GS** nie chroni przed wszystkimi atakami zabezpieczającymi przepełnienie buforu. Jeśli na przykład istnieje bufor oraz tabela wirtualna w obiekcie, przepełnienie buforu może spowodować uszkodzenie tabeli.

Nawet jeśli używasz **/GS**, zawsze próbuj napisać bezpieczny kod, który nie przekroczy buforu.

### <a name="to-set-this-compiler-option-in-visual-studio"></a>Aby ustawić tę opcję kompilatora w programie Visual Studio

1. W **Eksplorator rozwiązań** kliknij prawym przyciskiem myszy projekt, a następnie kliknij polecenie **Właściwości**.

   Aby uzyskać więcej informacji, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. W oknie dialogowym **strony właściwości** kliknij folder **C/C++** .

1. Kliknij stronę właściwości **generowanie kodu** .

1. Zmodyfikuj właściwość **Sprawdzanie zabezpieczeń buforu** .

### <a name="to-set-this-compiler-option-programmatically"></a>Aby programowo ustawić tę opcję kompilatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BufferSecurityCheck%2A>.

## <a name="example"></a>Przykład

W tym przykładzie nastąpi przepełnienie buforu. Spowoduje to błąd aplikacji podczas wykonywania.

```C
// compile with: /c /W1
#include <cstring>
#include <stdlib.h>
#pragma warning(disable : 4996)   // for strcpy use

// Vulnerable function
void vulnerable(const char *str) {
   char buffer[10];
   strcpy(buffer, str); // overrun buffer !!!

   // use a secure CRT function to help prevent buffer overruns
   // truncate string to fit a 10 byte buffer
   // strncpy_s(buffer, _countof(buffer), str, _TRUNCATE);
}

int main() {
   // declare buffer that is bigger than expected
   char large_buffer[] = "This string is longer than 10 characters!!";
   vulnerable(large_buffer);
}
```

## <a name="see-also"></a>Zobacz też

[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)
