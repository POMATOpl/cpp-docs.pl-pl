---
description: 'Dowiedz się więcej na temat: marshal_as'
title: marshal_as
ms.date: 07/12/2019
ms.topic: reference
f1_keywords:
- marshal_as
- msclr.interop.marshal_as
- msclr::interop::marshal_as
helpviewer_keywords:
- marshal_as template [C++]
ms.assetid: 2ed717da-2b11-41e5-981d-47d251771989
ms.openlocfilehash: 0b0738b8778b287e2e97f074345a10841c70a7b1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97253627"
---
# <a name="marshal_as"></a>marshal_as

Ta metoda konwertuje dane między środowiskami macierzystymi i zarządzanymi.

## <a name="syntax"></a>Składnia

```
To_Type marshal_as<To_Type>(
   From_Type input
);
```

#### <a name="parameters"></a>Parametry

*klawiatur*<br/>
podczas Wartość, którą chcesz zorganizować na `To_Type` zmienną.

## <a name="return-value"></a>Wartość zwracana

Zmienna typu `To_Type` , która jest wartością przekonwertowaną `input` .

## <a name="remarks"></a>Uwagi

Ta metoda stanowi uproszczony sposób konwersji danych między typami natywnymi i zarządzanymi. Aby określić, jakie typy danych są obsługiwane, zobacz [Omówienie organizowania w języku C++](../dotnet/overview-of-marshaling-in-cpp.md). Niektóre konwersje danych wymagają kontekstu. Te typy danych można skonwertować przy użyciu [klasy marshal_context](../dotnet/marshal-context-class.md).

Jeśli spróbujesz zorganizować parę typów danych, które nie są obsługiwane, `marshal_as` program wygeneruje błąd [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) w czasie kompilacji. Przeczytaj komunikat dostarczony z tym błędem, aby uzyskać więcej informacji. Ten `C4996` błąd może być wygenerowany dla więcej niż tylko przestarzałych funkcji. Przykładem tej próby jest zorganizowanie pary typów danych, które nie są obsługiwane.

Biblioteka organizowania składa się z kilku plików nagłówkowych. Każda konwersja wymaga tylko jednego pliku, ale można dołączyć dodatkowe pliki, jeśli zachodzi potrzeba przeprowadzenia innych konwersji. Aby sprawdzić, które konwersje są skojarzone z tymi plikami, należy poszukać w tabeli w temacie `Marshaling Overview` . Bez względu na to, jaką konwersję chcesz wykonać, wymaganie przestrzeni nazw jest zawsze włączone.

Zgłasza `System::ArgumentNullException(_EXCEPTION_NULLPTR)` , czy parametr wejściowy ma wartość null.

## <a name="example"></a>Przykład

Ten przykład ma kierowanie od a `const char*` do `System::String` typu zmiennej.

```cpp
// marshal_as_test.cpp
// compile with: /clr
#include <stdlib.h>
#include <string.h>
#include <msclr\marshal.h>

using namespace System;
using namespace msclr::interop;

int main() {
   const char* message = "Test String to Marshal";
   String^ result;
   result = marshal_as<String^>( message );
   return 0;
}
```

## <a name="requirements"></a>Wymagania

**Plik nagłówkowy:** \<msclr\marshal.h> , \<msclr\marshal_windows.h> , \<msclr\marshal_cppstd.h> lub \<msclr\marshal_atl.h>

**Przestrzeń nazw:** msclr:: Interop

## <a name="see-also"></a>Zobacz też

[Omówienie organizowania w języku C++](../dotnet/overview-of-marshaling-in-cpp.md)<br/>
[Klasa marshal_context](../dotnet/marshal-context-class.md)
