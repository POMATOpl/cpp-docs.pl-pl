---
description: 'Dowiedz się więcej na temat: Klasa CDynamicStringAccessorA —'
title: CDynamicStringAccessorA — Klasa
ms.date: 11/04/2016
f1_keywords:
- CDynamicStringAccessorA
helpviewer_keywords:
- CDynamicStringAccessorA class
ms.assetid: ed0d9821-a655-41f1-a902-43c3042ac49c
ms.openlocfilehash: 45a4d10c8a50c4009151fa90e51172405047a21a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97170727"
---
# <a name="cdynamicstringaccessora-class"></a>CDynamicStringAccessorA — Klasa

Pozwala uzyskać dostęp do źródła danych, gdy nie ma informacji o schemacie bazy danych (struktura bazowa).

## <a name="syntax"></a>Składnia

```cpp
typedef CDynamicStringAccessorT<CHAR, DBTYPE_STR> CDynamicStringAccessorA;
```

## <a name="remarks"></a>Uwagi

Oba żądania umożliwiają pobranie przez dostawcę wszystkich danych, do których uzyskano dostęp z magazynu danych jako dane ciągu, ale `CDynamicStringAccessor` żądanie danych ciągu ANSI.

`CDynamicStringAccessorA` dziedziczy `GetString` i `SetString` od `CDynamicStringAccessor` . Użycie tych metod w `CDynamicStringAccessorA` obiekcie `BaseType` ma wartość **char**.

## <a name="requirements"></a>Wymagania

**Nagłówek**: atldbcli. h

## <a name="see-also"></a>Zobacz też

[OLE DB Szablony konsumentów](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Dokumentacja szablonów klientów OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[Klasa CAccessor](../../data/oledb/caccessor-class.md)<br/>
[Klasa CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)<br/>
[Klasa CManualAccessor](../../data/oledb/cmanualaccessor-class.md)<br/>
[Klasa CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)<br/>
[Klasa CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md)<br/>
