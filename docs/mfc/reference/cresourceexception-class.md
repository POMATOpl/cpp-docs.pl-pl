---
description: 'Dowiedz się więcej na temat: Klasa CResourceException'
title: Klasa CResourceException
ms.date: 11/04/2016
f1_keywords:
- CResourceException
- AFXWIN/CResourceException
- AFXWIN/CResourceException::CResourceException
helpviewer_keywords:
- CResourceException [MFC], CResourceException
ms.assetid: af6ae043-d124-4bfd-b35e-7bb0db67d289
ms.openlocfilehash: c76635ae2cfa6c55bf54da7e73f6afbb44506fee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264872"
---
# <a name="cresourceexception-class"></a>Klasa CResourceException

Generowane, gdy system Windows nie może znaleźć lub przydzielić żądanego zasobu.

## <a name="syntax"></a>Składnia

```
class CResourceException : public CSimpleException
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CResourceException::CResourceException](#cresourceexception)|Konstruuje `CResourceException` obiekt.|

## <a name="remarks"></a>Uwagi

Dalsze kwalifikacje nie są wymagane ani możliwe.

Aby uzyskać więcej informacji na temat korzystania z programu `CResourceException` , zobacz [Obsługa wyjątków artykułów (MFC)](../../mfc/exception-handling-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

[CSimpleException](../../mfc/reference/csimpleexception-class.md)

`CResourceException`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxwin. h

## <a name="cresourceexceptioncresourceexception"></a><a name="cresourceexception"></a> CResourceException::CResourceException

Konstruuje `CResourceException` obiekt.

```
CResourceException();
```

### <a name="remarks"></a>Uwagi

Nie używaj tego konstruktora bezpośrednio, ale zamiast tego wywołaj funkcję globalną [AfxThrowResourceException](exception-processing.md#afxthrowresourceexception). Aby uzyskać więcej informacji o wyjątkach, zobacz [Obsługa wyjątków artykułów w MFC](../exception-handling-in-mfc.md).

## <a name="see-also"></a>Zobacz też

[Klasa CException](cexception-class.md)<br/>
[Wykres hierarchii](../hierarchy-chart.md)
