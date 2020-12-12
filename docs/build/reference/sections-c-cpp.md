---
description: 'Dowiedz się więcej o: SEKCJAch (C/C++)'
title: SEKCJE (C/C++)
ms.date: 11/04/2016
f1_keywords:
- SECTIONS
helpviewer_keywords:
- SECTIONS .def file statement
ms.assetid: 7b974366-9ef5-4e57-bbcc-73a1df6f8857
ms.openlocfilehash: aaebeb19c921dfb389c55209c7a371f49043cb56
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224767"
---
# <a name="sections-cc"></a>SEKCJE (C/C++)

Wprowadza część co najmniej jednego `definitions` , które są specyfikatorami dostępu w sekcjach pliku wyjściowego projektu.

```
SECTIONS
definitions
```

## <a name="remarks"></a>Uwagi

Każda definicja musi znajdować się w osobnym wierszu. `SECTIONS`Słowo kluczowe może znajdować się w tym samym wierszu co pierwsza definicja lub w poprzednim wierszu. Plik. def może zawierać jedną lub więcej `SECTIONS` instrukcji.

Ta `SECTIONS` instrukcja ustawia atrybuty dla co najmniej jednej sekcji w pliku obrazu i może służyć do przesłaniania atrybutów domyślnych dla każdego typu sekcji.

Format dla `definitions` :

`.section_name specifier`

gdzie `.section_name` jest nazwą sekcji w obrazie programu i `specifier` ma jeden lub więcej z następujących modyfikatorów dostępu:

|Modyfikator|Opis|
|--------------|-----------------|
|`EXECUTE`|Sekcja jest plikiem wykonywalnym|
|`READ`|Zezwala na operacje odczytu danych|
|`SHARED`|Udostępnia sekcję wśród wszystkich procesów, które ładują obraz|
|`WRITE`|Zezwala na operacje zapisu w danych|

Oddzielaj nazwy specyfikatora spacją. Na przykład:

```
SECTIONS
.rdata READ WRITE
```

`SECTIONS` oznacza początek listy sekcji `definitions` . Każdy `definition` z nich musi znajdować się w osobnym wierszu. `SECTIONS`Słowo kluczowe może znajdować się w tym samym wierszu co pierwszy `definition` lub w poprzednim wierszu. Plik. def może zawierać jedną lub więcej `SECTIONS` instrukcji. `SEGMENTS`Słowo kluczowe jest obsługiwane jako synonim dla `SECTIONS` .

Obsługiwane starsze wersje Visual C++:

```
section [CLASS 'classname'] specifier
```

`CLASS`Słowo kluczowe jest obsługiwane w celu zapewnienia zgodności, ale jest ignorowane.

Odpowiednikiem metody określania atrybutów sekcji jest opcja [/Section](section-specify-section-attributes.md) .

## <a name="see-also"></a>Zobacz też

[Reguły dla instrukcji Module-Definition](rules-for-module-definition-statements.md)
