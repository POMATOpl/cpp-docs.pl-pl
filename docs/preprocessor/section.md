---
description: 'Dowiedz się więcej na temat: sekcja pragma'
title: section, pragma
ms.date: 08/29/2019
f1_keywords:
- section_CPP
- vc-pragma.section
helpviewer_keywords:
- pragmas, section
- section pragma
ms.assetid: c67215e9-2c4a-4b0f-b691-2414d2e2d96f
ms.openlocfilehash: f4a719c60fd5bdf4f8e8841aab88f82c30b92a95
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342286"
---
# <a name="section-pragma"></a>section, pragma

Tworzy sekcję w pliku. obj.

## <a name="syntax"></a>Składnia

> **sekcja #pragma (** "*sekcja-Name*" [ **,** *Attributes* ] **)**

## <a name="remarks"></a>Uwagi

*Segment* terminów i *sekcja* mają takie samo znaczenie w tym artykule.

Po zdefiniowaniu sekcji pozostaje ona ważna dla pozostałej części kompilacji. Należy jednak użyć [__declspec (Przydziel)](../cpp/allocate.md)lub nic nie jest umieszczane w sekcji.

*Nazwa sekcji* jest wymaganym parametrem, który zmienia nazwę sekcji. Nazwa nie może powodować konfliktu z nazwami sekcji standardowych. Zobacz [/Section](../build/reference/section-specify-section-attributes.md) , aby uzyskać listę nazw, których nie należy używać podczas tworzenia sekcji.

*atrybuty* to opcjonalny parametr składający się z co najmniej jednego atrybutu rozdzielanego przecinkami do przypisania do sekcji. Możliwe *atrybuty* :

|Atrybut|Opis|
|-|-|
|**Przeczytaj**|Zezwala na operacje odczytu danych.|
|**write (zapis)**|Zezwala na operacje zapisu w danych.|
|**wykonana**|Zezwala na wykonanie kodu.|
|**udostępniać**|Udostępnia sekcję wśród wszystkich procesów, które ładują obraz.|
|**nopage**|Oznacza sekcję jako niestronicowaną. Przydatne w przypadku sterowników urządzeń Win32.|
|**nocache**|Oznacza sekcję jako niebędącą w pamięci podręcznej. Przydatne w przypadku sterowników urządzeń Win32.|
|**odrzucone**|Oznacza sekcję jako odrzucony. Przydatne w przypadku sterowników urządzeń Win32.|
|**usuwa**|Oznacza sekcję jako niebędącą rezydentem pamięci. Dotyczy tylko sterowników urządzeń wirtualnych (V *x* D).|

Jeśli nie określisz żadnych atrybutów, sekcja ma atrybuty **Odczyt** i **zapis** .

## <a name="example"></a>Przykład

W tym przykładzie pierwsza sekcja pragma identyfikuje sekcję i jej atrybuty. Liczba całkowita `j` nie jest umieszczana, `mysec` ponieważ nie została zadeklarowana przy użyciu `__declspec(allocate)` . Zamiast tego `j` przechodzą do sekcji dane. Liczba całkowita jest `i` w `mysec` wyniku `__declspec(allocate)` atrybutu klasy magazynu.

```cpp
// pragma_section.cpp
#pragma section("mysec",read,write)
int j = 0;

__declspec(allocate("mysec"))
int i = 0;

int main(){}
```

## <a name="see-also"></a>Zobacz też

[Dyrektywy pragma i słowo kluczowe __pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
