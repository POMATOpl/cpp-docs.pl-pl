---
description: Dowiedz się więcej o strukturze CDaoWorkspaceInfo —
title: CDaoWorkspaceInfo — Struktura
ms.date: 11/04/2016
f1_keywords:
- CDaoWorkspaceInfo
helpviewer_keywords:
- CDaoWorkspaceInfo structure [MFC]
- DAO (Data Access Objects), Workspaces collection
ms.assetid: a1f4b25e-f9c6-4196-b075-d1df99c54124
ms.openlocfilehash: b89e8787c2103244535e9458650f1f104478b748
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222206"
---
# <a name="cdaoworkspaceinfo-structure"></a>CDaoWorkspaceInfo — Struktura

`CDaoWorkspaceInfo`Struktura zawiera informacje dotyczące obszaru roboczego zdefiniowanego dla dostępu do bazy danych DAO (Data Access Objects).

## <a name="syntax"></a>Składnia

```
struct CDaoWorkspaceInfo
{
    CString m_strName;           // Primary
    CString m_strUserName;       // Secondary
    BOOL m_bIsolateODBCTrans;    // All
};
```

#### <a name="parameters"></a>Parametry

*m_strName*<br/>
Unikatowa nazwa obiektu obszaru roboczego. Aby bezpośrednio pobrać wartość tej właściwości, wywołaj funkcję elementu członkowskiego [GetName](../../mfc/reference/cdaoquerydef-class.md#getname) obiektu querydef. Aby uzyskać więcej informacji, zobacz temat "Nazwa właściwości" w pomocy DAO.

*m_strUserName*<br/>
Wartość, która reprezentuje właściciela obiektu obszaru roboczego. Aby uzyskać powiązane informacje, zobacz temat "UserName Property" w pomocy DAO.

*m_bIsolateODBCTrans*<br/>
Wartość wskazująca, czy wiele transakcji obejmujących tę samą bazę danych ODBC jest izolowanych. Aby uzyskać więcej informacji, zobacz [CDaoWorkspace:: SetIsolateODBCTrans](../../mfc/reference/cdaoworkspace-class.md#setisolateodbctrans). Aby uzyskać powiązane informacje, zobacz temat "Właściwość IsolateODBCTrans" w pomocy DAO.

## <a name="remarks"></a>Uwagi

Obszar roboczy jest obiektem klasy [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md). Odwołania do elementów podstawowych, pomocniczych i wszystkie powyżej wskazują, jak informacje są zwracane przez funkcję składową [GetWorkspaceInfo](../../mfc/reference/cdaoworkspace-class.md#getworkspaceinfo) w klasie `CDaoWorkspace` .

Informacje pobierane przez funkcję członkowską [CDaoWorkspace:: GetWorkspaceInfo](../../mfc/reference/cdaoworkspace-class.md#getworkspaceinfo) są przechowywane w `CDaoWorkspaceInfo` strukturze. `CDaoWorkspaceInfo` definiuje również `Dump` funkcję członkowską w kompilacjach debugowania. Możesz użyć, `Dump` aby zrzucić zawartość `CDaoWorkspaceInfo` obiektu.

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxdao. h

## <a name="see-also"></a>Zobacz też

[Struktury, style, wywołania zwrotne i mapy komunikatów](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[Klasa CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)
