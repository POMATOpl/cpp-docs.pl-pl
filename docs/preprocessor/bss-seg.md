---
description: 'Dowiedz się więcej na temat: bss_seg pragma'
title: bss_seg, pragma
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.bss_seg
- bss_seg_CPP
helpviewer_keywords:
- pragmas, bss_seg
- bss_seg pragma
ms.assetid: 755f0154-de51-4778-97d3-c9b24e445079
ms.openlocfilehash: e7a2cf73f8ab542755e5f6e0183896ce8e64be2a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97300882"
---
# <a name="bss_seg-pragma"></a>bss_seg, pragma

Określa sekcję (segment), w której Niezainicjowane zmienne są przechowywane w pliku obiektu (. obj).

## <a name="syntax"></a>Składnia

> **#pragma bss_seg (** ["*Nazwa sekcji*" [ **,** "*Klasa sekcji*"]] **)**\
> **#pragma bss_seg (** { **push**  |  **pop** } [ **,** *Identyfikator* ] [ **,** "*sekcja-Name*" [ **,** "*Section-Class*"]] **)**

### <a name="parameters"></a>Parametry

**wydajności**\
Obowiązkowe Umieszcza rekord na wewnętrznym stosie kompilatora. **Wypchnięcie** może mieć *Identyfikator* i *nazwę sekcji*.

**skakując**\
Obowiązkowe Usuwa rekord z góry wewnętrznego stosu kompilatora. **Punkt obecności** może mieć *Identyfikator* i *nazwę sekcji*. Można wyskakujące wiele rekordów przy użyciu tylko jednego polecenia **pop** przy użyciu *identyfikatora*. *Nazwa sekcji* zmieni się na nazwę aktywnej sekcji BSS po wyskakującym rogu.

*identyfikatora*\
Obowiązkowe W przypadku użycia z opcją **push** przypisuje nazwę rekordu na wewnętrznym stosie kompilatora. Gdy jest używany z **pop**, dyrektywa pop rejestruje wewnętrzny stos do momentu usunięcia *identyfikatora* . Jeśli na stosie wewnętrznym nie znaleziono *identyfikatora* , nic nie jest zdjęte.

*"Nazwa sekcji"*\
Obowiązkowe Nazwa sekcji. Gdy jest używany z **punktem pop**, stos jest zdjęte, a *sekcja Name* jest nazwą aktywnej sekcji BSS.

*"Klasa sekcji"*\
Obowiązkowe Ignorowany, ale dołączono do zgodności z wersjami Microsoft C++ wcześniejszymi niż wersja 2,0.

## <a name="remarks"></a>Uwagi

*Sekcja* w pliku obiektu to nazwany blok danych, który jest ładowany do pamięci jako jednostka. *Sekcja BSS* to Sekcja zawierająca niezainicjowane dane. W tym artykule, *segment* i *sekcja* terminów mają takie samo znaczenie.

Dyrektywa dyrektywy pragma **bss_seg** poleca kompilatorowi umieszczenie wszystkich niezainicjowanych elementów danych z jednostki tłumaczenia do sekcji BSS o nazwie *sekcja-Name*. W niektórych przypadkach użycie **bss_seg** może skrócić czas ładowania, grupując niezainicjowane dane w jedną sekcję. Domyślnie sekcja BSS używana dla niezainicjowanych danych w pliku obiektu ma nazwę `.bss` . Dyrektywa pragma **bss_seg** , bez parametru *Nazwa sekcji* resetuje nazwę sekcji BSS dla kolejnych niezainicjowanych elementów danych do `.bss` .

Dane przydzielono przy użyciu **bss_seg** pragma nie zachowuje żadnych informacji o lokalizacji.

Aby uzyskać listę nazw, które nie powinny być używane do tworzenia sekcji, zobacz [/Section](../build/reference/section-specify-section-attributes.md).

Można również określić sekcje dla zainicjowanych danych ([data_seg](../preprocessor/data-seg.md)), funkcje ([code_seg](../preprocessor/code-seg.md)) i zmienne const ([const_seg](../preprocessor/const-seg.md)).

Aplikacja [DUMPBIN.EXE](../build/reference/dumpbin-command-line.md) służy do wyświetlania plików obiektów. Wersje programu polecenia DUMPBIN dla każdej obsługiwanej architektury docelowej są dołączone do programu Visual Studio.

## <a name="example"></a>Przykład

```cpp
// pragma_directive_bss_seg.cpp
int i;                     // stored in .bss
#pragma bss_seg(".my_data1")
int j;                     // stored in .my_data1

#pragma bss_seg(push, stack1, ".my_data2")
int l;                     // stored in .my_data2

#pragma bss_seg(pop, stack1)   // pop stack1 from stack
int m;                     // stored in .my_data1

int main() {
}
```

## <a name="see-also"></a>Zobacz także

[Dyrektywy pragma i słowo kluczowe __pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
