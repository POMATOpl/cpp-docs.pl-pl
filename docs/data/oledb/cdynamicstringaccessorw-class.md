---
description: 'Dowiedz się więcej na temat: Klasa CDynamicStringAccessorW —'
title: CDynamicStringAccessorW — Klasa
ms.date: 11/04/2016
f1_keywords:
- CDynamicStringAccessorW
helpviewer_keywords:
- CDynamicStringAccessorW class
ms.assetid: 9b7fd5cc-3a9b-4b57-b907-f1e35de2c98f
ms.openlocfilehash: 360a9592cdce3a1046eecb360a8691b1d8480caf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97170675"
---
# <a name="cdynamicstringaccessorw-class"></a>CDynamicStringAccessorW — Klasa

Pozwala uzyskać dostęp do źródła danych, gdy nie ma informacji o schemacie bazy danych (struktura bazowa).

## <a name="syntax"></a>Składnia

```cpp
typedef CDynamicStringAccessorT<WCHAR, DBTYPE_WSTR> CDynamicStringAccessorW;
```

## <a name="remarks"></a>Uwagi

Oba żądania umożliwiają pobranie przez dostawcę wszystkich danych, do których uzyskano dostęp z magazynu danych jako dane ciągu, ale `CDynamicStringAccessor` żąda danych ciągu Unicode.

`CDynamicStringAccessorW` dziedziczy `GetString` i `SetString` od `CDynamicStringAccessor` . W przypadku używania tych metod w `CDynamicStringAccessorW` obiekcie `BaseType` jest **WCHAR**.

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
