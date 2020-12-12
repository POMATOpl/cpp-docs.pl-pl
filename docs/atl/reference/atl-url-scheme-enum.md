---
description: 'Dowiedz się więcej na temat: ATL_URL_SCHEME'
title: Wyliczenie ATL_URL_SCHEME
ms.date: 11/04/2016
helpviewer_keywords:
- ATLUTIL/ATL::ATL_URL_SCHEME
ms.assetid: f4131046-8ba0-4ec1-8209-84203f05d20e
ms.openlocfilehash: 72c149345a0e1edd41bfc9b32d1e94ab6477d488
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165137"
---
# <a name="atl_url_scheme"></a>ATL_URL_SCHEME

Elementy członkowskie tego wyliczenia zapewniają stałe dla programów zrozumiałych przez [zwinięcie](curl-class.md).

## <a name="syntax"></a>Składnia

```cpp
enum ATL_URL_SCHEME{
   ATL_URL_SCHEME_UNKNOWN = -1,
   ATL_URL_SCHEME_FTP     = 0,
   ATL_URL_SCHEME_GOPHER  = 1,
   ATL_URL_SCHEME_HTTP    = 2,
   ATL_URL_SCHEME_HTTPS   = 3,
   ATL_URL_SCHEME_FILE    = 4,
   ATL_URL_SCHEME_NEWS    = 5,
   ATL_URL_SCHEME_MAILTO  = 6,
   ATL_URL_SCHEME_SOCKS   = 7
};
```

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlutil. h

## <a name="see-also"></a>Zobacz też

[Pojęcia](../active-template-library-atl-concepts.md)<br/>
[Zwinięcie:: setschema](curl-class.md#setscheme)<br/>
[Zwinięcie:: GetSchema](curl-class.md#getscheme)
