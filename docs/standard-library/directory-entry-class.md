---
description: Dowiedz się więcej na temat klasy directory_entry
title: directory_entry — klasa
ms.date: 09/10/2018
f1_keywords:
- filesystem/std::experimental::filesystem::directory_entry
- filesystem/std::experimental::filesystem::directory_entry::operator const std::experimental::filesystem::path &
- filesystem/std::experimental::filesystem::directory_entry::directory_entry
- filesystem/std::experimental::filesystem::directory_entry::operator=
- filesystem/std::experimental::filesystem::directory_entry::assign
- filesystem/std::experimental::filesystem::directory_entry::replace_filename
- filesystem/std::experimental::filesystem::directory_entry::path
- filesystem/std::experimental::filesystem::directory_entry::status
- filesystem/std::experimental::filesystem::directory_entry::symlink_status
- filesystem/std::experimental::filesystem::directory_entry::operator&lt;
- filesystem/std::experimental::filesystem::directory_entry::operator==
- filesystem/std::experimental::filesystem::directory_entry::operator!=
- filesystem/std::experimental::filesystem::directory_entry::operator&lt;=
- filesystem/std::experimental::filesystem::directory_entry::operator&gt;
- filesystem/std::experimental::filesystem::directory_entry::operator&gt;=
ms.assetid: 1827c67b-4137-4548-adb0-f955f7acaf08
helpviewer_keywords:
- std::experimental::filesystem::directory_entry
- std::experimental::filesystem::directory_entry::operator const std::experimental::filesystem::path &
- std::experimental::filesystem::directory_entry::directory_entry
- std::experimental::filesystem::directory_entry::operator=
- std::experimental::filesystem::directory_entry::assign
- std::experimental::filesystem::directory_entry::replace_filename
- std::experimental::filesystem::directory_entry::path
- std::experimental::filesystem::directory_entry::status
- std::experimental::filesystem::directory_entry::symlink_status
- std::experimental::filesystem::directory_entry::operator&lt;
- std::experimental::filesystem::directory_entry::operator==
- std::experimental::filesystem::directory_entry::operator!=
- std::experimental::filesystem::directory_entry::operator&lt;=
- std::experimental::filesystem::directory_entry::operator&gt;
- std::experimental::filesystem::directory_entry::operator&gt;=
ms.openlocfilehash: a4a4b69e9f568c19eefae79554838fac5781f3f8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324551"
---
# <a name="directory_entry-class"></a>directory_entry — klasa

Opisuje obiekt, który jest zwracany przez `*X` , gdzie *X* jest [directory_iterator](../standard-library/directory-iterator-class.md) lub [recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md).

## <a name="syntax"></a>Składnia

```cpp
class directory_entry;
```

## <a name="remarks"></a>Uwagi

Klasa przechowuje obiekt typu [Path](../standard-library/path-class.md). Składowa `path` może być wystąpieniem [klasy Path](../standard-library/path-class.md) lub typu, który pochodzi od `path` . Przechowuje również dwie wartości [file_type](../standard-library/filesystem-enumerations.md#file_type) ; taki, który reprezentuje informacje o stanie przechowywanej nazwy pliku, oraz drugi, który reprezentuje informacje o stanie łącza symbolicznego nazwy pliku.

Aby uzyskać więcej informacji i przykładów kodu, zobacz [Nawigacja w systemie plików (C++)](../standard-library/file-system-navigation.md).

### <a name="constructors"></a>Konstruktory

|Konstruktor|Opis|
|-|-|
|[directory_entry](#directory_entry)|Konstruktory domyślne zachowują się zgodnie z oczekiwaniami. Czwarty Konstruktor inicjuje `mypath` do *Pval*, `mystat` do *stat_arg* i `mysymstat` *symstat_arg*.|

### <a name="member-functions"></a>Funkcje członkowskie

|Funkcja członkowska|Opis|
|-|-|
|[ponownie](#assign)|Funkcja członkowska przypisuje *Pval* do `mypath` , *stat* do `mystat` i *symstat* do `mysymstat` .|
|[ścieżka](#path)|Funkcja członkowska zwraca wartość `mypath` .|
|[replace_filename](#replace_filename)|Funkcja członkowska zastępuje `mypath` atrybutem `mypath.parent_path()`  /  *Pval*, `mystat` with *stat_arg* i `mysymstat` with *symstat_arg*|
|[Stany](#status)|Obie funkcje członkowskie zwracają `mystat` prawdopodobnie najpierw zmienione.|
|[symlink_status](#symlink_status)|Obie funkcje członkowskie zwracają `mysymstat` prawdopodobnie najpierw zmienione.|

### <a name="operators"></a>Operatory

|Operator|Opis|
|-|-|
|[operator! =](#op_neq)|Zamienia elementy listy na kopię innej listy.|
|[operator =](#op_as)|Operatory przypisywania domyślnego elementu członkowskiego zachowują się zgodnie z oczekiwaniami.|
|[operator = =](#op_eq)|Zwraca wartość `mypath == right.mypath`.|
|[<operatora ](#op_lt)|Zwraca wartość `mypath < right.mypath`.|
|[<operatora =](#op_lteq)|Zwraca wartość `!(right < *this)`.|
|[>operatora ](#op_gt)|Zwraca wartość `right < *this`.|
|[>operatora =](#op_gteq)|Zwraca wartość `!(*this < right)`.|
|[path_type operatora const&](#path_type)|Zwraca wartość `mypath`.|

## <a name="requirements"></a>Wymagania

**Nagłówek:** \< eksperymentalny/system plików&gt;

**Przestrzeń nazw:** std:: eksperymentalne:: filesystem

## <a name="assign"></a><a name="assign"></a> ponownie

Funkcja członkowska przypisuje *Pval* do `mypath` , *stat_arg* do `mystat` i *symstat_arg* do `mysymstat` .

```cpp
void assign(const std::experimental::filesystem::path& pval,
    file_status stat_arg = file_status(),
    file_status symstat_arg = file_status());
```

### <a name="parameters"></a>Parametry

*pval*\
Ścieżka nazwy przechowywanego pliku.

*stat_arg*\
Stan nazwy przechowywanego pliku.

*symstat_arg*\
Stan linku symbolicznego nazwy przechowywanego pliku.

## <a name="directory_entry"></a><a name="directory_entry"></a> directory_entry

Konstruktory domyślne zachowują się zgodnie z oczekiwaniami. Czwarty Konstruktor inicjuje `mypath` do *Pval*, `mystat` do *stat_arg* i `mysymstat` *symstat_arg*.

```cpp
directory_entry() = default;
directory_entry(const directory_entry&) = default;
directory_entry(directory_entry&&) noexcept = default;
explicit directory_entry(const std::experimental::filesystem::path& pval,
    file_status stat_arg = file_status(),
    file_status symstat_arg = file_status());
```

### <a name="parameters"></a>Parametry

*pval*\
Ścieżka nazwy przechowywanego pliku.

*stat_arg*\
Stan nazwy przechowywanego pliku.

*symstat_arg*\
Stan linku symbolicznego nazwy przechowywanego pliku.

## <a name="operator"></a><a name="op_neq"></a> operator! =

Funkcja członkowska zwraca wartość `!(*this == right)` .

```cpp
bool operator!=(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>Parametry

*Kliknij*\
[Directory_entry](../standard-library/directory-entry-class.md) jest porównywana z `directory_entry` .

## <a name="operator"></a><a name="op_as"></a> operator =

Operatory przypisywania domyślnego elementu członkowskiego zachowują się zgodnie z oczekiwaniami.

```cpp
directory_entry& operator=(const directory_entry&) = default;
directory_entry& operator=(directory_entry&&) noexcept = default;
```

### <a name="parameters"></a>Parametry

*Kliknij*\
[Directory_entry](../standard-library/directory-entry-class.md) kopiowana do programu `directory_entry` .

## <a name="operator"></a><a name="op_eq"></a> operator = =

Funkcja członkowska zwraca wartość `mypath == right.mypath` .

```cpp
bool operator==(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>Parametry

*Kliknij*\
[Directory_entry](../standard-library/directory-entry-class.md) jest porównywana z `directory_entry` .

## <a name="operatorlt"></a><a name="op_lt"></a> zakład&lt;

Funkcja członkowska zwraca wartość `mypath < right.mypath` .

```cpp
bool operator<(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>Parametry

*Kliknij*\
[Directory_entry](../standard-library/directory-entry-class.md) jest porównywana z `directory_entry` .

## <a name="operatorlt"></a><a name="op_lteq"></a> zakład&lt;=

Funkcja członkowska zwraca wartość `!(right < *this)` .

```cpp
bool operator&lt;=(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>Parametry

*Kliknij*\
[Directory_entry](../standard-library/directory-entry-class.md) jest porównywana z `directory_entry` .

## <a name="operatorgt"></a><a name="op_gt"></a> zakład&gt;

Funkcja członkowska zwraca wartość `right < *this` .

```cpp
bool operator&gt;(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>Parametry

*Kliknij*\
[Directory_entry](../standard-library/directory-entry-class.md) jest porównywana z `directory_entry` .

## <a name="operatorgt"></a><a name="op_gteq"></a> zakład&gt;=

Funkcja członkowska zwraca wartość `!(*this < right)` .

```cpp
bool operator&gt;=(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>Parametry

*Kliknij*\
[Directory_entry](../standard-library/directory-entry-class.md) jest porównywana z `directory_entry` .

## <a name="operator-const-path_type"></a><a name="path_type"></a> path_type operatora const&

Operator elementu członkowskiego zwraca `mypath` .

```cpp
operator const std::experimental::filesystem::path&() const;
```

## <a name="path"></a><a name="path"></a> ścieżka

Funkcja członkowska zwraca wartość `mypath` .

```cpp
const std::experimental::filesystem::path& path() const noexcept;
```

## <a name="replace_filename"></a><a name="replace_filename"></a> replace_filename

Funkcja członkowska zastępuje `mypath` atrybutem `mypath.parent_path()`  /  *Pval*, `mystat` with *stat_arg* i `mysymstat` with *symstat_arg*

```cpp
void replace_filename(
    const std::experimental::filesystem::path& pval,
    file_status stat_arg = file_status(),
    file_status symstat_arg = file_status());
```

### <a name="parameters"></a>Parametry

*pval*\
Ścieżka nazwy przechowywanego pliku.

*stat_arg*\
Stan nazwy przechowywanego pliku.

*symstat_arg*\
Stan linku symbolicznego nazwy przechowywanego pliku.

## <a name="status"></a><a name="status"></a> Stany

Obie funkcje członkowskie zwracają `mystat` prawdopodobnie najpierw zmienione w następujący sposób:

1. Jeśli `status_known(mystat)` nie, nic nie rób.

1. W przeciwnym razie `!status_known(mysymstat) && !is_symlink(mysymstat)` `mystat = mysymstat` .

```cpp
file_status status() const;
file_status status(error_code& ec) const noexcept;
```

### <a name="parameters"></a>Parametry

*udziela*\
Kod błędu stanu.

## <a name="symlink_status"></a><a name="symlink_status"></a> symlink_status

Obie funkcje członkowskie zwracają `mysymstat` prawdopodobnie najpierw zmienione w następujący sposób: Jeśli `status_known(mysymstat)` nie, nic nie rób. W przeciwnym razie wartość `mysymstat = symlink_status(mypval)`.

```cpp
file_status symlink_status() const;
file_status symlink_status(error_code& ec) const noexcept;
```

### <a name="parameters"></a>Parametry

*udziela*\
Kod błędu stanu.

## <a name="see-also"></a>Zobacz też

[Dokumentacja plików nagłówkowych](../standard-library/cpp-standard-library-header-files.md)\
[\<wymagany&gt;](../standard-library/filesystem.md)
