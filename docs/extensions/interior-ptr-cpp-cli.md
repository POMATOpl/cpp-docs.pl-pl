---
title: interior_ptr (C++/CLI)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- stdcli::language::interior_ptr
- interior_ptr_cpp
- interior_ptr
helpviewer_keywords:
- interior_ptr keyword [C++]
ms.assetid: 25160f74-569e-492d-9e3c-67ece7486baa
ms.openlocfilehash: 573c78def0b5bbe790f3b8fec1ff70b907f9d820
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2019
ms.locfileid: "58787277"
---
# <a name="interiorptr-ccli"></a>interior_ptr (C++/CLI)

*Wskaźnika wewnętrznego* deklaruje wskaźnik do wewnątrz typu odwołania, ale nie do samego obiektu. Uchwyt odwołania, typ wartości, uchwyt typ spakowany, składowej typu zarządzanego lub element tablicy zarządzanej, można wskazać wskaźnika wewnętrznego.

## <a name="all-runtimes"></a>Wszystkie środowiska wykonawcze

(Nie ma żadnych uwag dla tej funkcji języka, które są stosowane do wszystkich środowisk uruchomieniowych).

## <a name="windows-runtime"></a>Środowisko wykonawcze systemu Windows

(Nie ma żadnych uwag dla tej funkcji języka, które dotyczą tylko środowiska uruchomieniowego Windows).

### <a name="requirements"></a>Wymagania

— Opcja kompilatora: `/ZW`

## <a name="common-language-runtime"></a>środowiska uruchomieniowe w trakcie wykonania

W poniższym przykładzie składnia pokazuje wskaźnika wewnętrznego.

### <a name="syntax"></a>Składnia

```cpp
cli::interior_ptr<cv_qualifier type> var = &initializer;
```

### <a name="parameters"></a>Parametry

*cv_qualifier*<br/>
**Const** lub **volatile** kwalifikatorów.

*type*<br/>
Typ *inicjatora*.

*var*<br/>
Nazwa **pomocą interior_ptr** zmiennej.

*initializer*<br/>
Element członkowski typu odwołania, element tablicy zarządzanej lub inny obiekt, który można przypisać na wskaźnik natywny.

### <a name="remarks"></a>Uwagi

Wskaźnik natywny nie jest w stanie śledzić element jako jego zmiany lokalizacji na zarządzanym stosie, które powstały na skutek przenoszenie wystąpień obiektu moduł odśmiecania pamięci. Wskaźnik do poprawnie odwołują się do wystąpienia, środowisko uruchomieniowe potrzebuje aktualizacji wskaźnik do nowo pozycjonowane obiektu.

**Pomocą interior_ptr** stanowi nadzbiór funkcji wskaźnik natywny.  W związku z tym, wszystkie elementy, które mogą być przypisane do wskaźnik natywny można również przypisać do **pomocą interior_ptr**.  Wskaźnika wewnętrznego może wykonać ten sam zestaw operacji co natywnymi wskaźnikami, w tym porównania i arytmetyka wskaźnika.

Wskaźnika wewnętrznego, mogą być deklarowane tylko na stosie.  Nie można zadeklarować wskaźnika wewnętrznego jako składowej klasy.

Ponieważ wskaźników wnętrza istnieje tylko na stosie, biorąc pod adres wskaźnika wewnętrznego daje niezarządzanym wskaźnikiem.

**pomocą interior_ptr** ma niejawną konwersję do **bool**, co pozwala na jej użycie w instrukcjach warunkowych.

Aby uzyskać informacje na temat sposobu deklarowania wnętrza wskaźnika, który wskazuje na obiekt, którego nie można przenieść na stercie zebranych elementów bezużytecznych, zobacz [pin_ptr](pin-ptr-cpp-cli.md).

**pomocą interior_ptr** znajduje się w przestrzeni nazw cli.  Zobacz [platformy, domyślna i cli przestrzenie nazw](platform-default-and-cli-namespaces-cpp-component-extensions.md) Aby uzyskać więcej informacji.

Aby uzyskać więcej informacji na wskaźnikach posługiwanie się nimi Zobacz

- [Instrukcje: deklarowanie wewnętrznych wskaźników i zarządzanych tablic oraz posługiwanie się nimi (C++/CLI)](how-to-declare-and-use-interior-pointers-and-managed-arrays-cpp-cli.md)

- [Instrukcje: deklarowanie typów wartości za pomocą słowa kluczowego interior_ptr (C++/CLI)](how-to-declare-value-types-with-the-interior-ptr-keyword-cpp-cli.md)

- [Instrukcje: funkcje przeładowania z wewnętrznymi i natywnymi wskaźnikami (C++/CLI)](how-to-overload-functions-with-interior-pointers-and-native-pointers-cpp-cli.md)

- [Instrukcje: deklarowanie wewnętrznych wskaźników za pomocą słowa kluczowego const (C++/CLI)](how-to-declare-interior-pointers-with-the-const-keyword-cpp-cli.md)

### <a name="requirements"></a>Wymagania

— Opcja kompilatora: `/clr`

### <a name="examples"></a>Przykłady

Poniższy przykład pokazuje sposób deklarowania i użyć wskaźnika wewnętrznego na typ odwołania.

```cpp
// interior_ptr.cpp
// compile with: /clr
using namespace System;

ref class MyClass {
public:
   int data;
};

int main() {
   MyClass ^ h_MyClass = gcnew MyClass;
   h_MyClass->data = 1;
   Console::WriteLine(h_MyClass->data);

   interior_ptr<int> p = &(h_MyClass->data);
   *p = 2;
   Console::WriteLine(h_MyClass->data);

   // alternatively
   interior_ptr<MyClass ^> p2 = &h_MyClass;
   (*p2)->data = 3;
   Console::WriteLine((*p2)->data);
}
```

```Output
1
2
3
```

## <a name="see-also"></a>Zobacz też

[Rozszerzenia składników dla platformy .NET i platformy uniwersalnej systemu Windows](component-extensions-for-runtime-platforms.md)