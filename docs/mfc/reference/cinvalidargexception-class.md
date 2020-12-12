---
description: 'Dowiedz się więcej na temat: Klasa CInvalidArgException'
title: Klasa CInvalidArgException
ms.date: 11/04/2016
f1_keywords:
- CInvalidArgException
- AFX/CInvalidArgException
- AFX/CInvalidArgException::CInvalidArgException
helpviewer_keywords:
- CInvalidArgException [MFC], CInvalidArgException
ms.assetid: e43d7c67-1157-47f8-817a-804083e8186e
ms.openlocfilehash: f68642747a81d1c45a8246f4f25abfb8b79c81d8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202798"
---
# <a name="cinvalidargexception-class"></a>Klasa CInvalidArgException

Ta klasa reprezentuje warunek wyjątku dla nieprawidłowego argumentu.

## <a name="syntax"></a>Składnia

```
class CInvalidArgException : public CSimpleException
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CInvalidArgException::CInvalidArgException](#cinvalidargexception)|Konstruktor.|

## <a name="remarks"></a>Uwagi

`CInvalidArgException`Obiekt reprezentuje warunek wyjątku dla nieprawidłowego argumentu.

Aby uzyskać więcej informacji na temat obsługi wyjątków, zobacz temat [Klasa CException](../../mfc/reference/cexception-class.md) i [Obsługa wyjątków (MFC)](../../mfc/exception-handling-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

[CSimpleException](../../mfc/reference/csimpleexception-class.md)

`CInvalidArgException`

## <a name="requirements"></a>Wymagania

**Nagłówek:** AFX. h

## <a name="cinvalidargexceptioncinvalidargexception"></a><a name="cinvalidargexception"></a> CInvalidArgException::CInvalidArgException

Konstruktor.

```
CInvalidArgException();
```

### <a name="remarks"></a>Uwagi

Nie używaj tego konstruktora bezpośrednio; wywołaj funkcję globalną **AfxThrowInvalidArgException**.

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasa CSimpleException](../../mfc/reference/csimpleexception-class.md)
