---
description: Dowiedz się więcej o obszarach nazw platform, Default i CLI (C++/CLI i C++/CX)
title: Przestrzeń nazw platformy, domyślna i cli  (C++/CLI i C++/CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- lang
- cli
helpviewer_keywords:
- lang namespace
- cli namespace
ms.assetid: 9d38bd1e-dc78-47d1-a84b-9b4683e52c9c
ms.openlocfilehash: 1b4b47a1568b1a137bc49a09b8b50feb8ec3a76b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185677"
---
# <a name="platform-default-and-cli-namespaces--ccli-and-ccx"></a>Przestrzeń nazw platformy, domyślna i cli  (C++/CLI i C++/CX)

Przestrzeń nazw kwalifikuje nazwy elementów języka, tak aby nazwy nie były sprzeczne z identycznymi nazwami zdefiniowanymi w innych miejscach w kodzie źródłowym. Na przykład kolizja nazw może uniemożliwić kompilatorowi rozpoznanie [słów kluczowych kontekstowych](context-sensitive-keywords-cpp-component-extensions.md). Przestrzenie nazw są używane przez kompilator, ale nie są zachowywane w skompilowanym zestawie.

## <a name="all-runtimes"></a>Wszystkie środowiska wykonawcze

Program Visual Studio udostępnia domyślną przestrzeń nazw dla projektu podczas tworzenia projektu. Można ręcznie zmienić nazwę przestrzeni nazw, chociaż w języku C++/CX nazwa pliku winmd musi być zgodna z nazwą głównej przestrzeni nazw.

## <a name="windows-runtime"></a>Środowisko wykonawcze systemu Windows

Aby uzyskać więcej informacji, zobacz [przestrzenie nazw i widoczność typów (C++/CX)](../cppcx/namespaces-and-type-visibility-c-cx.md).

### <a name="requirements"></a>Wymagania

Opcja kompilatora: `/ZW`

## <a name="common-language-runtime"></a>środowiska uruchomieniowe w trakcie wykonania

### <a name="syntax"></a>Składnia

```cpp
using namespace cli;
```

### <a name="remarks"></a>Uwagi

C++/CLI obsługuje przestrzeń nazw **interfejsu wiersza polecenia** . Podczas kompilowania przy użyciu `/clr` **`using`** instrukcji jest implikowana instrukcja w sekcji składni.

W przestrzeni nazw **interfejsu wiersza polecenia** znajdują się następujące funkcje języka:

- [Tablice](arrays-cpp-component-extensions.md)

- [interior_ptr (C++/CLI)](interior-ptr-cpp-cli.md)

- [pin_ptr (C++/CLI)](pin-ptr-cpp-cli.md)

- [safe_cast](safe-cast-cpp-component-extensions.md)

### <a name="requirements"></a>Wymagania

Opcja kompilatora: `/clr`

### <a name="examples"></a>Przykłady

Poniższy przykład kodu pokazuje, że można użyć symbolu w przestrzeni nazw **CLI** jako symbolu zdefiniowanego przez użytkownika w kodzie.  Jednak po wykonaniu tej czynności konieczne będzie jawne lub niejawne kwalifikowanie odwołań do elementu języka **interfejsu wiersza polecenia** o tej samej nazwie.

```cpp
// cli_namespace.cpp
// compile with: /clr
using namespace cli;
int main() {
   array<int> ^ MyArray = gcnew array<int>(100);
   int array = 0;

   array<int> ^ MyArray2 = gcnew array<int>(100);   // C2062

   // OK
   cli::array<int> ^ MyArray2 = gcnew cli::array<int>(100);
   ::array<int> ^ MyArray3 = gcnew ::array<int>(100);
}
```

## <a name="see-also"></a>Zobacz też

[Rozszerzenia składników dla platform .NET i platformy UWP](component-extensions-for-runtime-platforms.md)
