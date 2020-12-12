---
description: Dowiedz się więcej o strukturze DHtmlUrlEventMapEntry —
title: DHtmlUrlEventMapEntry — Struktura
ms.date: 11/04/2016
f1_keywords:
- DHtmlUrlEventMapEntry
helpviewer_keywords:
- DHtmlUrlEventMapEntry structure [MFC]
ms.assetid: 43117c1f-1a51-406c-aa2f-fea647080049
ms.openlocfilehash: c35e3ac70d8530042ca73397b0f7c6df13501497
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220061"
---
# <a name="dhtmlurleventmapentry-structure"></a>DHtmlUrlEventMapEntry — Struktura

`DHtmlUrlEventMapEntry`Struktura zapewnia obsługę map zdarzeń wieloadresowych adresów URL.

## <a name="syntax"></a>Składnia

```
struct DHtmlUrlEventMapEntry
{
LPCTSTR szUrl;
const DHtmlEventMapEntry *pEventMap;
};
```

#### <a name="parameters"></a>Parametry

*szUrl*<br/>
Adres URL.

*pEventMap*<br/>
Mapa zdarzeń skojarzona z adresem URL.

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxdhtml. h

## <a name="see-also"></a>Zobacz też

[Struktury, style, wywołania zwrotne i mapy komunikatów](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)
