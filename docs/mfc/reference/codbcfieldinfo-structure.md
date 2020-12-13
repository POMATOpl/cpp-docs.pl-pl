---
description: Dowiedz się więcej o strukturze CODBCFieldInfo —
title: CODBCFieldInfo — Struktura
ms.date: 11/04/2016
f1_keywords:
- CODBCFieldInfo
helpviewer_keywords:
- ODBC [MFC], data source information
- CODBCFieldInfo structure [MFC]
ms.assetid: 92598b4f-facc-4108-b282-63a179ff79ab
ms.openlocfilehash: 7cd7072719bec46cfbfaeb02c5c86d714c4de13c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331416"
---
# <a name="codbcfieldinfo-structure"></a>CODBCFieldInfo — Struktura

`CODBCFieldInfo`Struktura zawiera informacje o polach w źródle danych ODBC.

## <a name="syntax"></a>Składnia

```
struct CODBCFieldInfo
{
    CString m_strName;
    SWORD m_nSQLType;
    UDWORD m_nPrecision;
    SWORD m_nScale;
    SWORD m_nNullability;
};
```

#### <a name="parameters"></a>Parametry

*m_strName*<br/>
Nazwa pola.

*m_nSQLType*<br/>
Typ danych SQL pola. Może to być typ danych ODBC SQL lub specyficzny dla sterownika typ danych SQL. Aby uzyskać listę prawidłowych typów danych ODBC SQL, zobacz "typy danych SQL" w Windows SDK. Aby uzyskać informacje na temat typów danych SQL specyficznych dla sterownika, zobacz dokumentację sterownika.

*m_nPrecision*<br/>
Maksymalna precyzja pola. Aby uzyskać szczegółowe informacje, zobacz "dokładność, skala, długość i rozmiar wyświetlania" w Windows SDK.

*m_nScale*<br/>
Skala pola. Aby uzyskać szczegółowe informacje, zobacz "dokładność, skala, długość i rozmiar wyświetlania" w Windows SDK.

*m_nNullability*<br/>
Czy pole akceptuje wartość null. Może to być jedna z dwóch wartości: SQL_NULLABLE, jeśli pole przyjmuje wartości null lub SQL_NO_NULLS, jeśli pole nie akceptuje wartości null.

## <a name="remarks"></a>Uwagi

Aby pobrać te informacje, wywołaj [CRecordset:: GetODBCFieldInfo](../../mfc/reference/crecordset-class.md#getodbcfieldinfo).

## <a name="requirements"></a>Wymagania

**Nagłówek:** AFXDB. h

## <a name="see-also"></a>Zobacz też

[Struktury, style, wywołania zwrotne i mapy komunikatów](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CRecordset::GetODBCFieldInfo](../../mfc/reference/crecordset-class.md#getodbcfieldinfo)<br/>
[CRecordset:: GetFieldValue —](../../mfc/reference/crecordset-class.md#getfieldvalue)
