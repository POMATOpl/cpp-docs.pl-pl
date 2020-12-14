---
description: Dowiedz się więcej na temat struktury HSE_VERSION_INFO
title: HSE_VERSION_INFO — Struktura
ms.date: 11/04/2016
f1_keywords:
- HSE_VERSION_INFO
helpviewer_keywords:
- HSE_VERSION_INFO structure [MFC]
ms.assetid: 4837312d-68c8-4d05-9afa-1934d7d49b20
ms.openlocfilehash: fe03f3c4e00f9af62398993838927ce75410f17b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97219632"
---
# <a name="hse_version_info-structure"></a>HSE_VERSION_INFO — Struktura

Ta struktura jest wskazywana przez parametr *pVer* w `CHttpServer::GetExtensionVersion` funkcji członkowskiej. Zawiera numer wersji programu ISA oraz opis tekstowy ISA.

## <a name="syntax"></a>Składnia

```
typedef struct _HSE_VERSION_INFO {
    DWORD dwExtensionVersion;
    CHAR lpszExtensionDesc[HSE_MAX_EXT_DLL_NAME_LEN];
} HSE_VERSION_INFO, *LPHSE_VERSION_INFO;
```

#### <a name="parameters"></a>Parametry

*dwExtensionVersion*<br/>
Numer wersji programu ISA.

*lpszExtensionDesc*<br/>
Opis tekstowy ISA. Domyślna implementacja zawiera tekst zastępczy; Przesłoń `CHttpServer::GetExtensionVersion` , aby podać własny opis.

## <a name="requirements"></a>Wymagania

**Nagłówek:** httpext. h

## <a name="see-also"></a>Zobacz też

[Struktury, style, wywołania zwrotne i mapy komunikatów](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)
