---
description: Dowiedz się więcej o strukturze CDaoIndexFieldInfo —
title: CDaoIndexFieldInfo — Struktura
ms.date: 09/17/2019
f1_keywords:
- CDaoIndexFieldInfo
helpviewer_keywords:
- CDaoIndexFieldInfo structure [MFC]
- DAO (Data Access Objects), Index Fields collection
ms.assetid: 097ee8a6-83b1-4db7-8f05-d62a2deefe19
ms.openlocfilehash: fe2d6bef3ce44e7418474b7f2c004942935968c8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97250793"
---
# <a name="cdaoindexfieldinfo-structure"></a>CDaoIndexFieldInfo — Struktura

`CDaoIndexFieldInfo`Struktura zawiera informacje o obiekcie pola indeksu zdefiniowanego dla obiektów dostępu do danych (DAO).

Obiekty DAO są obsługiwane przez pakiet Office 2013. Element DAO 3,6 jest wersją ostateczną i jest uznawany za przestarzały.

## <a name="syntax"></a>Składnia

```
struct CDaoIndexFieldInfo
{
    CString m_strName;          // Primary
    BOOL m_bDescending;         // Primary
};
```

#### <a name="parameters"></a>Parametry

*m_strName*<br/>
Unikatowa nazwa obiektu pola indeksu. Aby uzyskać szczegółowe informacje, zobacz temat "Nazwa właściwości" w pomocy DAO.

*m_bDescending*<br/>
Wskazuje kolejność indeksowania zdefiniowaną przez obiekt index. Ma wartość TRUE, jeśli kolejność jest malejąca.

## <a name="remarks"></a>Uwagi

Obiekt indeksu może mieć liczbę pól wskazującą, które pola tabledef (lub zestaw rekordów na podstawie tabeli) są indeksowane. Odwołania do podstawowego powyżej wskazują, jak informacje są zwracane w `m_pFieldInfos` elemencie członkowskim obiektu [CDaoIndexInfo —](../../mfc/reference/cdaoindexinfo-structure.md) uzyskanym przez wywołanie `GetIndexInfo` funkcji składowej klasy [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getindexinfo) lub [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getindexinfo).

Obiekty indeksu i obiekty pól indeksów nie są reprezentowane przez klasę MFC. Zamiast tego obiekty DAO powiązane z obiektami MFC klasy [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) lub [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) zawierają kolekcję obiektów indeksu o nazwie kolekcja indeksów. Każdy obiekt indeksu z kolei zawiera kolekcję obiektów pól. Te klasy dostarczają funkcje członkowskie, aby uzyskać dostęp do poszczególnych elementów informacji o indeksie, lub można uzyskać do nich dostęp jednocześnie przy użyciu `CDaoIndexInfo` obiektu, wywołując `GetIndexInfo` funkcję członkowską obiektu zawierającego. `CDaoIndexInfo`Obiekt,,, ma element członkowski danych, `m_pFieldInfos` , który wskazuje na tablicę `CDaoIndexFieldInfo` obiektów.

Wywołaj `GetIndexInfo` funkcję członkowską zawierającego obiekt tabledef lub Recordset, w której kolekcja indeksów jest przechowywana obiektu indeksu, który Cię interesuje. Następnie uzyskaj dostęp do `m_pFieldInfos` elementu członkowskiego obiektu [CDaoIndexInfo —](../../mfc/reference/cdaoindexinfo-structure.md) . Długość `m_pFieldInfos` tablicy jest przechowywana w `m_nFields` . `CDaoIndexFieldInfo` definiuje również `Dump` funkcję członkowską w kompilacjach debugowania. Możesz użyć, `Dump` aby zrzucić zawartość `CDaoIndexFieldInfo` obiektu.

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxdao. h

## <a name="see-also"></a>Zobacz też

[Struktury, style, wywołania zwrotne i mapy komunikatów](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoTableDef::GetIndexInfo](../../mfc/reference/cdaotabledef-class.md#getindexinfo)<br/>
[CDaoRecordset:: GetIndexInfo](../../mfc/reference/cdaorecordset-class.md#getindexinfo)
