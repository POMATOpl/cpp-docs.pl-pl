---
description: Dowiedz się więcej o strukturze CDaoRelationFieldInfo —
title: CDaoRelationFieldInfo — Struktura
ms.date: 11/04/2016
f1_keywords:
- CDaoRelationFieldInfo
helpviewer_keywords:
- DAO (Data Access Objects), Relations collection
- CDaoRelationFieldInfo structure [MFC]
ms.assetid: 47cb89ca-dc80-47ce-96fd-cc4b88512558
ms.openlocfilehash: eb470752a9e9da5f610dd59976f2716fa1c4e18a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248167"
---
# <a name="cdaorelationfieldinfo-structure"></a>CDaoRelationFieldInfo — Struktura

`CDaoRelationFieldInfo`Struktura zawiera informacje o polu w relacji zdefiniowanej dla obiektów dostępu do danych (DAO).

## <a name="syntax"></a>Składnia

```
struct CDaoRelationFieldInfo
{
    CString m_strName;           // Primary
    CString m_strForeignName;    // Primary
};
```

#### <a name="parameters"></a>Parametry

*m_strName*<br/>
Nazwa pola w podstawowej tabeli relacji.

*m_strForeignName*<br/>
Nazwa pola w tabeli obcej relacji.

## <a name="remarks"></a>Uwagi

Obiekt relacji DAO określa pola w tabeli głównej i pola w tabeli obcej, które definiują relację. Odwołania do podstawowego w definicji struktury powyżej wskazują, w jaki sposób informacje są zwracane w `m_pFieldInfos` elemencie członkowskim obiektu [CDaoRelationInfo —](../../mfc/reference/cdaorelationinfo-structure.md) uzyskane przez wywołanie funkcji składowej [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) klasy `CDaoDatabase` .

Obiekty relacji i obiekty pól relacji nie są reprezentowane przez klasę MFC. Zamiast tego obiekty DAO bazowe obiekty MFC klasy [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) zawierają kolekcję obiektów relacji o nazwie kolekcja relacji. Każdy obiekt relacji, z kolei, zawiera kolekcję obiektów pól relacji. Każdy obiekt pola relacji skorelowanie pola w tabeli podstawowej z polem w tabeli obcej. Razem obiekty pól relacji definiują grupę pól w każdej tabeli, które razem definiują relację. `CDaoDatabase` pozwala uzyskać dostęp do obiektów relacji z `CDaoRelationInfo` obiektem, wywołując `GetRelationInfo` funkcję członkowską. `CDaoRelationInfo`Obiekt,,, ma element członkowski danych, `m_pFieldInfos` , który wskazuje na tablicę `CDaoRelationFieldInfo` obiektów.

Wywołaj funkcję członkowską [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) zawierającego `CDaoDatabase` obiekt, w którym kolekcja relacji jest przechowywana obiektu relacji, który Cię interesuje. Następnie uzyskaj dostęp do `m_pFieldInfos` elementu członkowskiego obiektu [CDaoRelationInfo —](../../mfc/reference/cdaorelationinfo-structure.md) . `CDaoRelationFieldInfo` definiuje również `Dump` funkcję członkowską w kompilacjach debugowania. Możesz użyć, `Dump` aby zrzucić zawartość `CDaoRelationFieldInfo` obiektu.

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxdao. h

## <a name="see-also"></a>Zobacz też

[Struktury, style, wywołania zwrotne i mapy komunikatów](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoRelationInfo —, struktura](../../mfc/reference/cdaorelationinfo-structure.md)
