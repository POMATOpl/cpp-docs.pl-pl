---
description: 'Dowiedz się więcej na temat: data_seg pragma'
title: data_seg, pragma
ms.date: 08/29/2019
f1_keywords:
- data_seg_CPP
- vc-pragma.data_seg
helpviewer_keywords:
- data_seg pragma
- pragmas, data_seg
ms.assetid: 65c66466-4c98-494f-93af-106beb4caf78
ms.openlocfilehash: f7caff65273b2fc0d51c6bfd1cede42cce7103d9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97300791"
---
# <a name="data_seg-pragma"></a>data_seg, pragma

Określa sekcję danych (segment), w której zmienne Initialize są przechowywane w pliku obiektu (. obj).

## <a name="syntax"></a>Składnia

> **#pragma data_seg (** ["*Nazwa sekcji*" [ **,** "*Klasa sekcji*"]] **)**\
> **#pragma data_seg (** { **push**  |  **pop** } [ **,** *Identyfikator* ] [ **,** "*sekcja-Name*" [ **,** "*Section-Class*"]] **)**

### <a name="parameters"></a>Parametry

**wydajności**\
Obowiązkowe Umieszcza rekord na wewnętrznym stosie kompilatora. **Wypchnięcie** może mieć *Identyfikator* i *nazwę sekcji*.

**skakując**\
Obowiązkowe Usuwa rekord z góry wewnętrznego stosu kompilatora. **Punkt obecności** może mieć *Identyfikator* i *nazwę sekcji*. Można wyskakujące wiele rekordów przy użyciu tylko jednego polecenia **pop** przy użyciu *identyfikatora*. *Nazwa sekcji* zmieni się na nazwę aktywnej sekcji danych po wyskakującym okienku.

*identyfikatora*\
Obowiązkowe W przypadku użycia z opcją **push** przypisuje nazwę rekordu na wewnętrznym stosie kompilatora. Gdy jest używany z **pop**, pop rejestruje wewnętrzny stos do momentu usunięcia *identyfikatora* . Jeśli na stosie wewnętrznym nie znaleziono *identyfikatora* , nic nie jest zdjęte.

*Identyfikator* umożliwia zdjęte wielu rekordów z pojedynczym poleceniem **pop** .

*"Nazwa sekcji"*\
Obowiązkowe Nazwa sekcji. Gdy jest używany z **punktem pop**, stos jest zdjęte, a *sekcja Name* to nazwa sekcji Aktywne dane.

*"Klasa sekcji"*\
Obowiązkowe Ignorowany, ale dołączono do zgodności z wersjami Microsoft C++ wcześniejszymi niż wersja 2,0.

## <a name="remarks"></a>Uwagi

*Sekcja* w pliku obiektu to nazwany blok danych, który jest ładowany do pamięci jako jednostka. *Sekcja danych* to Sekcja zawierająca zainicjowane dane. W tym artykule, *segment* i *sekcja* terminów mają takie samo znaczenie.

Sekcja domyślna w pliku. obj dla zainicjowanych zmiennych to `.data` . Zmienne, które są niezainicjowane, są uznawane za zainicjowane na zero i są przechowywane w `.bss` .

Dyrektywa dyrektywy pragma **data_seg** poleca kompilatorowi umieszczenie wszystkich zainicjowanych elementów danych z jednostki tłumaczenia do sekcji danych o nazwie *sekcja-Name*. Domyślnie sekcja danych używana dla zainicjowanych danych w pliku obiektu ma nazwę `.data` . Zmienne, które są niezainicjowane, są uznawane za zainicjowane na zero i są przechowywane w `.bss` . Dyrektywa pragma **data_seg** , bez parametru *Nazwa sekcji* resetuje nazwę sekcji danych dla kolejnych zainicjowanych elementów danych do `.data` .

Dane przydzielono przy użyciu **data_seg** nie zachowują żadnych informacji o lokalizacji.

Aby uzyskać listę nazw, które nie powinny być używane do tworzenia sekcji, zobacz [/Section](../build/reference/section-specify-section-attributes.md).

Możesz również określić sekcje dla zmiennych const ([const_seg](../preprocessor/const-seg.md)), niezainicjowanych danych ([bss_seg](../preprocessor/bss-seg.md)) i funkcji ([code_seg](../preprocessor/code-seg.md)).

Aplikacja [DUMPBIN.EXE](../build/reference/dumpbin-command-line.md) służy do wyświetlania plików obiektów. Wersje programu polecenia DUMPBIN dla każdej obsługiwanej architektury docelowej są dołączone do programu Visual Studio.

## <a name="example"></a>Przykład

```cpp
// pragma_directive_data_seg.cpp
int h = 1;                     // stored in .data
int i = 0;                     // stored in .bss
#pragma data_seg(".my_data1")
int j = 1;                     // stored in .my_data1

#pragma data_seg(push, stack1, ".my_data2")
int l = 2;                     // stored in .my_data2

#pragma data_seg(pop, stack1)   // pop stack1 off the stack
int m = 3;                     // stored in .my_data1

int main() {
}
```

## <a name="see-also"></a>Zobacz także

[Dyrektywy pragma i słowo kluczowe __pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
