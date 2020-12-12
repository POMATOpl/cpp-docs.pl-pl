---
description: Dowiedz się więcej na temat klasy file_status
title: file_status — Klasa
ms.date: 09/10/2018
f1_keywords:
- filesystem/std::experimental::filesystem::file_status
- filesystem/std::experimental::filesystem::file_status::operator=
- filesystem/std::experimental::filesystem::file_status::type
- filesystem/std::experimental::filesystem::file_status::permissions
ms.assetid: 9781840e-ad22-44dd-ad79-0fabaa94bac4
helpviewer_keywords:
- std::experimental::filesystem::file_status
- std::experimental::filesystem::file_status::operator=
- std::experimental::filesystem::file_status::type
- std::experimental::filesystem::file_status::permissions
ms.openlocfilehash: 8bc789d97f9b90b18214407fadab19e9644012a1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324368"
---
# <a name="file_status-class"></a>file_status — Klasa

Zawija [file_type](../standard-library/filesystem-enumerations.md#file_type) i [uprawnienia](../standard-library/filesystem-enumerations.md#perms)pliku.

## <a name="syntax"></a>Składnia

```cpp
class file_status;
```

### <a name="constructors"></a>Konstruktory

|Konstruktor|Opis|
|-|-|
|[file_status](#file_status)|Konstruuje otokę dla [file_type](../standard-library/filesystem-enumerations.md#file_type) i [uprawnienia](../standard-library/filesystem-enumerations.md#perms)pliku.|

### <a name="member-functions"></a>Funkcje członkowskie

|Funkcja członkowska|Opis|
|-|-|
|[Wprowadź](#type)|Pobiera lub ustawia `file_type` .|
|[uprawnienia](#permissions)|Pobiera lub ustawia uprawnienia do pliku.|

### <a name="operators"></a>Operatory

|Operator|Opis|
|-|-|
|[operator =](#op_as)|Operatory przypisywania domyślnego elementu członkowskiego zachowują się zgodnie z oczekiwaniami.|

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<filesystem>

**Przestrzeń nazw:** std:: eksperymentalne:: FileSystem, std:: eksperymentalne:: filesystem

## <a name="file_statusfile_status"></a><a name="file_status"></a> file_status:: file_status

Konstruuje otokę dla [file_type](../standard-library/filesystem-enumerations.md#file_type) i [uprawnienia](../standard-library/filesystem-enumerations.md#perms)pliku.

```cpp
explicit file_status(
   file_type ftype = file_type::none,
   perms mask = perms::unknown) noexcept;

file_status(const file_status&) noexcept = default;

file_status(file_status&&) noexcept = default;

~file_status() noexcept = default;
```

### <a name="parameters"></a>Parametry

*ftype*\
Określony `file_type` , domyślnie `file_type::none` .

*bitowa*\
Określony plik `perms` , domyślnie `perms::unknown` .

*file_status*\
Przechowywany obiekt.

## <a name="file_statusoperator"></a><a name="op_as"></a> file_status:: operator =

Operatory przypisywania domyślnego elementu członkowskiego zachowują się zgodnie z oczekiwaniami.

```cpp
file_status& operator=(const file_status&) noexcept = default;
file_status& operator=(file_status&&) nexcept = default;
```

### <a name="parameters"></a>Parametry

*file_status*\
[File_status](../standard-library/file-status-class.md) kopiowana do programu `file_status` .

## <a name="type"></a><a name="type"></a> Wprowadź

Pobiera lub ustawia `file_type` .

```cpp
file_type type() const noexcept
void type(file_type ftype) noexcept
```

### <a name="parameters"></a>Parametry

*ftype*\
Określony `file_type` .

## <a name="permissions"></a><a name="permissions"></a> uprawnienia

Pobiera lub ustawia uprawnienia do pliku.

Użyj metody ustawiającej, aby utworzyć plik `readonly` lub usunąć `readonly` atrybut.

```cpp
perms permissions() const noexcept
void permissions(perms mask) noexcept
```

### <a name="parameters"></a>Parametry

*bitowa*\
Określony `perms` .

## <a name="see-also"></a>Zobacz też

[Dokumentacja plików nagłówkowych](../standard-library/cpp-standard-library-header-files.md)\
[Path — Klasa](../standard-library/path-class.md)\
[\<filesystem>](../standard-library/filesystem.md)
