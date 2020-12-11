---
description: 'Dowiedz się więcej na temat: &lt; &gt; funkcje IStream'
title: '&lt;&gt;funkcje IStream'
ms.date: 11/04/2016
f1_keywords:
- istream/std::swap
- istream/std::ws
ms.assetid: 0301ea0d-4ded-4841-83dd-4253b55b3188
ms.openlocfilehash: c71770d8c6e86829eb4e0153abc924d612d3eff6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154178"
---
# <a name="ltistreamgt-functions"></a>&lt;&gt;funkcje IStream

[wymiany](#istream_swap)\
[ws](#ws)

## <a name="swap"></a><a name="istream_swap"></a> wymiany

Wymienia elementy dwóch obiektów strumienia.

```cpp
template <class Elem, class Tr>
void swap(
    basic_istream<Elem, Tr>& left,
    basic_istream<Elem, Tr>& right);

template <class Elem, class Tr>
void swap(
    basic_iostream<Elem, Tr>& left,
    basic_iostream<Elem, Tr>& right);
```

### <a name="parameters"></a>Parametry

*lewym*\
Strumień.

*Kliknij*\
Strumień.

## <a name="ws"></a><a name="ws"></a> WS

Pomija biały znak w strumieniu.

```cpp
template class<Elem, Tr> basic_istream<Elem, Tr>& ws(basic_istream<Elem, Tr>& _Istr);
```

### <a name="parameters"></a>Parametry

*_Istr*\
Strumień.

### <a name="return-value"></a>Wartość zwracana

Strumień.

### <a name="remarks"></a>Uwagi

Manipulator wyodrębnia i odrzuca wszystkie elementy, `ch` dla których [use_facet](../standard-library/basic-filebuf-class.md#open) <  **CType** \< **Elem**> > ( [getloc](../standard-library/ios-base-class.md#getloc)). **is**( **CType** \< **Elem**> :: **Space**, **ch**) ma wartość true.

Funkcja wywołuje metodę [setstate](../standard-library/basic-ios-class.md#setstate)( **eofbit**), jeśli napotka koniec pliku podczas wyodrębniania elementów. Zwraca *_Istr*.

### <a name="example"></a>Przykład

Zobacz [>>operatora ](../standard-library/istream-operators.md#op_gt_gt) , aby zapoznać się z przykładem użycia `ws` .

## <a name="see-also"></a>Zobacz też

[\<istream>](../standard-library/istream.md)
