---
description: 'Dowiedz się więcej na temat: _com_error:: _com_error'
title: _com_error::_com_error
ms.date: 11/04/2016
f1_keywords:
- _com_error::_com_error
helpviewer_keywords:
- _com_error method [C++]
ms.assetid: 0a69e46c-caab-49ef-b091-eee401253ce6
ms.openlocfilehash: 2c5b912f5d532e9aed5b8e84a3fe7e2fcd7d4100
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332571"
---
# <a name="_com_error_com_error"></a>_com_error::_com_error

**Specyficzne dla firmy Microsoft**

Konstruuje obiekt **_com_error** .

## <a name="syntax"></a>Składnia

```
_com_error(
   HRESULT hr,
   IErrorInfo* perrinfo = NULL,
   bool fAddRef=false) throw( );

_com_error( const _com_error& that ) throw( );
```

#### <a name="parameters"></a>Parametry

*godz.*<br/>
Informacje o HRESULT.

*perrinfo*<br/>
`IErrorInfo` Stream.

*fAddRef*<br/>
Wartość domyślna powoduje, że Konstruktor wywołuje AddRef na interfejsie innym niż null `IErrorInfo` . Zapewnia to poprawne zliczanie odwołań w typowym przypadku, gdy własność interfejsu jest przenoszona do obiektu **_com_error** , na przykład:

```cpp
throw _com_error(hr, perrinfo);
```

Jeśli nie chcesz, aby kod przeniesieł własność do obiektu **_com_error** i `AddRef` jest wymagany do przesunięcia `Release` w destruktorze **_com_error** , Utwórz obiekt w następujący sposób:

```cpp
_com_error err(hr, perrinfo, true);
```

*przez*<br/>
Istniejący obiekt **_com_error** .

## <a name="remarks"></a>Uwagi

Pierwszy Konstruktor tworzy nowy obiekt z uwzględnieniem obiektu HRESULT i Optional `IErrorInfo` . Druga tworzy kopię istniejącego obiektu **_com_error** .

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Klasa _com_error](../cpp/com-error-class.md)
