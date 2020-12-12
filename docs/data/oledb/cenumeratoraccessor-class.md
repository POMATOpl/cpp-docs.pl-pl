---
description: 'Dowiedz się więcej na temat: Klasa CEnumeratorAccessor'
title: CEnumeratorAccessor — Klasa
ms.date: 11/04/2016
f1_keywords:
- ATL::CEnumeratorAccessor
- CEnumeratorAccessor
- ATL.CEnumeratorAccessor
- CEnumeratorAccessor.m_bIsParent
- ATL::CEnumeratorAccessor::m_bIsParent
- m_bIsParent
- ATL.CEnumeratorAccessor.m_bIsParent
- CEnumeratorAccessor::m_bIsParent
- ATL::CEnumeratorAccessor::m_nType
- CEnumeratorAccessor.m_nType
- CEnumeratorAccessor::m_nType
- ATL.CEnumeratorAccessor.m_nType
- ATL::CEnumeratorAccessor::m_szDescription
- CEnumeratorAccessor.m_szDescription
- CEnumeratorAccessor::m_szDescription
- ATL.CEnumeratorAccessor.m_szDescription
- CEnumeratorAccessor::m_szName
- ATL.CEnumeratorAccessor.m_szName
- ATL::CEnumeratorAccessor::m_szName
- CEnumeratorAccessor.m_szName
- CEnumeratorAccessor::m_szParseName
- ATL::CEnumeratorAccessor::m_szParseName
- m_szParseName
- CEnumeratorAccessor.m_szParseName
- ATL.CEnumeratorAccessor.m_szParseName
helpviewer_keywords:
- CEnumeratorAccessor class
- m_bIsParent
- m_nType
- m_szDescription
- m_szName
- m_szParseName
ms.assetid: 21e8e7ea-3511-4afe-b33f-d520f4ff82bb
ms.openlocfilehash: f37de34c508487f3ee54f47db1b0a64df8a97b25
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97170571"
---
# <a name="cenumeratoraccessor-class"></a>CEnumeratorAccessor — Klasa

Używane przez [CEnumerator](../../data/oledb/cenumerator-class.md) do uzyskiwania dostępu do danych z zestawu wierszy modułu wyliczającego.

## <a name="syntax"></a>Składnia

```cpp
class CEnumeratorAccessor
```

## <a name="requirements"></a>Wymagania

**Nagłówek:** atldbcli. h

## <a name="members"></a>Elementy członkowskie

### <a name="data-members"></a>Elementy członkowskie danych

| Nazwa | Opis |
|-|-|
|[m_bIsParent](#bisparent)|Zmienna wskazująca, czy moduł wyliczający jest nadrzędnym modułem wyliczania, jeśli wiersz jest modułem wyliczającym.|
|[m_nType](#ntype)|Zmienna wskazująca, czy w wierszu opisano źródło danych czy moduł wyliczający.|
|[m_szDescription](#szdescription)|Opis źródła danych lub modułu wyliczającego.|
|[m_szName](#szname)|Nazwa źródła danych lub modułu wyliczającego.|
|[m_szParseName](#szparsename)|Ciąg do przekazania do [IParseDisplayName](/windows/win32/api/oleidl/nn-oleidl-iparsedisplayname) w celu uzyskania monikera dla źródła danych lub modułu wyliczającego.|

## <a name="remarks"></a>Uwagi

Ten zestaw wierszy składa się ze źródeł danych i modułów wyliczających widocznych z bieżącego modułu wyliczającego.

## <a name="cenumeratoraccessorm_bisparent"></a><a name="bisparent"></a> CEnumeratorAccessor:: m_bIsParent

Zmienna wskazująca, czy moduł wyliczający jest nadrzędnym modułem wyliczania, jeśli wiersz jest modułem wyliczającym.

### <a name="syntax"></a>Składnia

```cpp
VARIANT_BOOL m_bIsParent;
```

### <a name="remarks"></a>Uwagi

Aby uzyskać więcej informacji, zobacz [ISourcesRowset:: GetSourcesRowset](/previous-versions/windows/desktop/ms711200(v=vs.85)) w *dokumentacji programisty OLE DB* .

## <a name="cenumeratoraccessorm_ntype"></a><a name="ntype"></a> CEnumeratorAccessor:: m_nType

Zmienna wskazująca, czy w wierszu opisano źródło danych czy moduł wyliczający.

### <a name="syntax"></a>Składnia

```cpp
USHORT m_nType;
```

### <a name="remarks"></a>Uwagi

Aby uzyskać więcej informacji, zobacz [ISourcesRowset:: GetSourcesRowset](/previous-versions/windows/desktop/ms711200(v=vs.85)) w *dokumentacji programisty OLE DB* .

## <a name="cenumeratoraccessorm_szdescription"></a><a name="szdescription"></a> CEnumeratorAccessor:: m_szDescription

Opis źródła danych lub modułu wyliczającego.

### <a name="syntax"></a>Składnia

```cpp
WCHAR m_szDescription[129];
```

### <a name="remarks"></a>Uwagi

Aby uzyskać więcej informacji, zobacz [ISourcesRowset:: GetSourcesRowset](/previous-versions/windows/desktop/ms711200(v=vs.85)) w *dokumentacji programisty OLE DB* .

## <a name="cenumeratoraccessorm_szname"></a><a name="szname"></a> CEnumeratorAccessor:: m_szName

Nazwa źródła danych lub modułu wyliczającego.

### <a name="syntax"></a>Składnia

```cpp
WCHAR m_szName[129];
```

### <a name="remarks"></a>Uwagi

Aby uzyskać więcej informacji, zobacz [ISourcesRowset:: GetSourcesRowset](/previous-versions/windows/desktop/ms711200(v=vs.85)) w *dokumentacji programisty OLE DB* .

## <a name="cenumeratoraccessorm_szparsename"></a><a name="szparsename"></a> CEnumeratorAccessor:: m_szParseName

Ciąg do przekazania do [IParseDisplayName](/windows/win32/api/oleidl/nn-oleidl-iparsedisplayname) w celu uzyskania monikera dla źródła danych lub modułu wyliczającego.

### <a name="syntax"></a>Składnia

```cpp
WCHAR m_szParseName[129];
```

### <a name="remarks"></a>Uwagi

Aby uzyskać więcej informacji, zobacz [ISourcesRowset:: GetSourcesRowset](/previous-versions/windows/desktop/ms711200(v=vs.85)) w *dokumentacji programisty OLE DB* .

## <a name="see-also"></a>Zobacz też

[OLE DB Szablony konsumentów](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Dokumentacja szablonów klientów OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)
