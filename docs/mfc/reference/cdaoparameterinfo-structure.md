---
description: Dowiedz się więcej o strukturze CDaoParameterInfo —
title: CDaoParameterInfo — Struktura
ms.date: 09/17/2019
f1_keywords:
- CDaoParameterInfo
helpviewer_keywords:
- CDaoParameterInfo structure [MFC]
- DAO (Data Access Objects), Parameters collection
ms.assetid: 45fd53cd-cb84-4e12-b48d-7f2979f898ad
ms.openlocfilehash: b4cd1916bb30c3b646e9b0892e2bdcdf5ade30b4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97250725"
---
# <a name="cdaoparameterinfo-structure"></a>CDaoParameterInfo — Struktura

`CDaoParameterInfo`Struktura zawiera informacje o obiekcie parametru zdefiniowanym dla obiektów dostępu do danych (DAO). Element DAO 3,6 jest wersją ostateczną i jest uznawany za przestarzały.

## <a name="syntax"></a>Składnia

```
struct CDaoParameterInfo
{
    CString m_strName;       // Primary
    short m_nType;           // Primary
    ColeVariant m_varValue;  // Secondary
};
```

#### <a name="parameters"></a>Parametry

*m_strName*<br/>
Unikatowa nazwa obiektu parametru. Aby uzyskać więcej informacji, zobacz temat "Nazwa właściwości" w pomocy DAO.

*m_nType*<br/>
Wartość, która wskazuje typ danych obiektu parametru. Listę możliwych wartości można znaleźć w *m_nType* składowej struktury [CDaoFieldInfo —](../../mfc/reference/cdaofieldinfo-structure.md) . Aby uzyskać więcej informacji, zobacz temat "Type Property" w pomocy DAO.

*m_varValue*<br/>
Wartość parametru przechowywana w obiekcie [COleVariant](../../mfc/reference/colevariant-class.md) .

## <a name="remarks"></a>Uwagi

Odwołania do podstawowych i pomocniczych powyżej wskazują, jak informacje są zwracane przez funkcję elementu członkowskiego [GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo) w klasie `CDaoQueryDef` .

MFC nie hermetyzuje obiektów parametrów DAO w klasie. Obiekty DAO querydef powiązane `CDaoQueryDef` z obiektami MFC są przechowywane parametry w kolekcjach parametrów. Aby uzyskać dostęp do obiektów parametrów w obiekcie [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) , wywołaj `GetParameterInfo` funkcję członkowską obiektu querydef dla określonej nazwy parametru lub indeks w kolekcji Parameters. Można użyć funkcji składowej [CDaoQueryDef:: GetParameterCount](../../mfc/reference/cdaoquerydef-class.md#getparametercount) w połączeniu z `GetParameterInfo` pętlą for za pomocą kolekcji Parameters.

Informacje pobierane przez funkcję członkowską [CDaoQueryDef:: GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo) są przechowywane w `CDaoParameterInfo` strukturze. Wywołanie `GetParameterInfo` obiektu querydef w kolekcji Parameters, w której jest przechowywany obiekt Parameter.

> [!NOTE]
> Jeśli chcesz uzyskać lub ustawić tylko wartość parametru, użyj funkcji składowych [GetParamValue](../../mfc/reference/cdaorecordset-class.md#getparamvalue) i [SetParamValue](../../mfc/reference/cdaorecordset-class.md#setparamvalue) klasy `CDaoRecordset` .

`CDaoParameterInfo` definiuje również `Dump` funkcję członkowską w kompilacjach debugowania. Możesz użyć, `Dump` aby zrzucić zawartość `CDaoParameterInfo` obiektu.

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxdao. h

## <a name="see-also"></a>Zobacz też

[Struktury, style, wywołania zwrotne i mapy komunikatów](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[Klasa CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)
