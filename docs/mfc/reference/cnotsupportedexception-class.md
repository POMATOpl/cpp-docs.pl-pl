---
description: 'Dowiedz się więcej na temat: Klasa CNotSupportedException'
title: Klasa CNotSupportedException
ms.date: 11/04/2016
f1_keywords:
- CNotSupportedException
- AFX/CNotSupportedException
- AFX/CNotSupportedException::CNotSupportedException
helpviewer_keywords:
- CNotSupportedException [MFC], CNotSupportedException
ms.assetid: e517391b-eb94-4c39-ae32-87b45bf7d624
ms.openlocfilehash: 61bf729753897e1d30c5a12bc371489ba6f2d64f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331473"
---
# <a name="cnotsupportedexception-class"></a>Klasa CNotSupportedException

Reprezentuje wyjątek, który jest wynikiem żądania nieobsługiwanej funkcji.

## <a name="syntax"></a>Składnia

```
class CNotSupportedException : public CSimpleException
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CNotSupportedException::CNotSupportedException](#cnotsupportedexception)|Konstruuje `CNotSupportedException` obiekt.|

## <a name="remarks"></a>Uwagi

Dalsze kwalifikacje nie są wymagane ani możliwe.

Aby uzyskać więcej informacji na temat korzystania z programu `CNotSupportedException` , zobacz [Obsługa wyjątków artykułów (MFC)](../../mfc/exception-handling-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

[CSimpleException](../../mfc/reference/csimpleexception-class.md)

`CNotSupportedException`

## <a name="requirements"></a>Wymagania

**Nagłówek:** AFX. h

## <a name="cnotsupportedexceptioncnotsupportedexception"></a><a name="cnotsupportedexception"></a> CNotSupportedException::CNotSupportedException

Konstruuje `CNotSupportedException` obiekt.

```
CNotSupportedException();
```

### <a name="remarks"></a>Uwagi

Nie używaj tego konstruktora bezpośrednio, ale zamiast tego wywołaj funkcję globalną [AfxThrowNotSupportedException](exception-processing.md#afxthrownotsupportedexception). Aby uzyskać więcej informacji na temat przetwarzania wyjątków, zobacz [Obsługa wyjątków artykułów w MFC](../exception-handling-in-mfc.md).

## <a name="see-also"></a>Zobacz też

[Klasa CException](cexception-class.md)<br/>
[Wykres hierarchii](../hierarchy-chart.md)
