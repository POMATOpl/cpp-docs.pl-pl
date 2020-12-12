---
description: 'Dowiedz się więcej na temat: dostęp do biblioteki typów'
title: Dostęp do biblioteki typów
ms.date: 11/04/2016
helpviewer_keywords:
- type libraries [MFC], accessing
ms.assetid: a03fa7f0-86c2-4119-bf81-202916fb74b3
ms.openlocfilehash: c855f82914e540ab13f4bc20581c041633b5bc0d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218657"
---
# <a name="type-library-access"></a>Dostęp do biblioteki typów

Biblioteki typów uwidaczniają interfejsy kontrolki OLE innym aplikacjom obsługującym technologię OLE. Każdy formant OLE musi mieć bibliotekę typów, jeśli jeden lub więcej interfejsów ma być narażony.

Następujące makra pozwalają formantowi OLE zapewnić dostęp do własnej biblioteki typów:

### <a name="type-library-access"></a>Dostęp do biblioteki typów

|Nazwa|Opis|
|-|-|
|[DECLARE_OLETYPELIB](#declare_oletypelib)|Deklaruje `GetTypeLib` funkcję członkowską formantu OLE (musi być użyta w deklaracji klasy).|
|[IMPLEMENT_OLETYPELIB](#implement_oletypelib)|Implementuje `GetTypeLib` funkcję członkowską formantu OLE (musi być używana w implementacji klasy).|

## <a name="declare_oletypelib"></a><a name="declare_oletypelib"></a> DECLARE_OLETYPELIB

Deklaruje `GetTypeLib` funkcję członkowską klasy kontrolki.

```
DECLARE_OLETYPELIB(class_name)
```

### <a name="parameters"></a>Parametry

*class_name*<br/>
Nazwa klasy kontrolki powiązanej z biblioteką typów.

### <a name="remarks"></a>Uwagi

Użyj tego makra w pliku nagłówkowym klasy kontrolki.

### <a name="requirements"></a>Wymagania

**Nagłówek:** AFXDISP. h

## <a name="implement_oletypelib"></a><a name="implement_oletypelib"></a> IMPLEMENT_OLETYPELIB

Implementuje `GetTypeLib` funkcję składową formantu.

```
IMPLEMENT_OLETYPELIB(class_name, tlid, wVerMajor,  wVerMinor)
```

### <a name="parameters"></a>Parametry

*class_name*<br/>
Nazwa klasy kontrolki powiązanej z biblioteką typów.

*tlid*<br/>
Numer IDENTYFIKACYJNy biblioteki typów.

*wVerMajor*<br/>
Główny numer wersji biblioteki typów.

*wVerMinor*<br/>
Numer wersji pomocniczej biblioteki typów.

### <a name="remarks"></a>Uwagi

To makro musi pojawić się w pliku implementacji dla każdej klasy kontrolki, która używa makra DECLARE_OLETYPELIB.

### <a name="requirements"></a>Wymagania

**Nagłówek:** AFXDISP. h

## <a name="see-also"></a>Zobacz też

[Makra i Globals](../../mfc/reference/mfc-macros-and-globals.md)
