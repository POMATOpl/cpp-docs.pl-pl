---
description: 'Dowiedz się więcej o: &lt; Operatory systemu plików &gt;'
title: '&lt;Operatory systemu plików &gt;'
ms.date: 11/04/2016
f1_keywords:
- FILESYSTEM/std::experimental::filesystem::operator==
- FILESYSTEM/std::experimental::filesystem::operator!=
- FILESYSTEM/std::experimental::filesystem::operator<
- FILESYSTEM/std::experimental::filesystem::operator<=
- FILESYSTEM/std::experimental::filesystem::operator>
- FILESYSTEM/std::experimental::filesystem::operator>=
- FILESYSTEM/std::experimental::filesystem::operator/
- FILESYSTEM/std::experimental::filesystem::operator<<
- FILESYSTEM/std::experimental::filesystem::operator>>
ms.assetid: 102c4833-aa3b-41a8-8998-f5003c546bfd
ms.openlocfilehash: 140ef553cbfd17fe2b1cfc41bedba397506da817
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97232473"
---
# <a name="ltfilesystemgt-operators"></a>&lt;Operatory systemu plików &gt;

Operatory wykonują leksykalne porównanie dwóch ścieżek jako ciągi. Użyj `equivalent` funkcji, aby określić, czy dwie ścieżki (na przykład ścieżka względna i ścieżka bezwzględna) odnoszą się do tego samego pliku lub katalogu na dysku.

Aby uzyskać więcej informacji, zobacz [Nawigacja w systemie plików (C++)](../standard-library/file-system-navigation.md).

## <a name="operator"></a>operator==

```cpp
bool operator==(const path& left, const path& right) noexcept;
```

Funkcja zwraca wartość Left. Native () = = Right. Native ().

## <a name="operator"></a>operator!=

```cpp
bool operator!=(const path& left, const path& right) noexcept;
```

Funkcja zwraca! (Left = = Right).

## <a name="operator"></a>< operatora

```cpp
bool operator<(const path& left, const path& right) noexcept;
```

Funkcja zwraca wartość Left. Native () < Right. Native ().

## <a name="operator"></a><operatora =

```cpp
bool operator<=(const path& left, const path& right) noexcept;
```

Funkcja zwraca! ( \< po lewej stronie).

## <a name="operator"></a>> operatora

```cpp
bool operator>(const path& left, const path& right) noexcept;
```

Funkcja zwraca prawo \< .

## <a name="operator"></a>operator>=

```cpp
bool operator>=(const path& left, const path& right) noexcept;
```

Funkcja zwraca! (po lewej < w prawo).

## <a name="operator"></a>zakład

```cpp
path operator/(const path& left, const path& right);
```

Funkcja wykonuje:

```cpp
basic_string<Elem, Traits> str;
path ans = left;
return (ans /= right);
```

## <a name="operator"></a><< operatora

```cpp
template <class Elem, class Traits>
basic_ostream<Elem, Traits>& operator<<(basic_ostream<Elem, Traits>& os, const path& pval);
```

Funkcja zwraca system operacyjny << Pval. String \<Elem, Traits> ().

## <a name="operator"></a>>> operatora

```cpp
template <class Elem, class Traits>
basic_istream<Elem, Traits>& operator<<(basic_istream<Elem, Traits>& is, const path& pval);
```

Funkcja wykonuje:

```cpp
basic_string<Elem, Traits> str;
is>> str;
pval = str;
return (is);
```
