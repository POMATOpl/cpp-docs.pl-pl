---
description: 'Dowiedz się więcej na temat: konwertowanie danych nieobsługiwanych przez dostawcę'
title: Konwertowanie danych nieobsługiwanych przez dostawcę
ms.date: 10/29/2018
helpviewer_keywords:
- OLE DB provider templates, unsupported data types
ms.assetid: f495e50f-530a-4fab-ab54-e0c359785845
ms.openlocfilehash: 9fb449247ff40118e89dbebee5f43a1208a1f181
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323369"
---
# <a name="converting-data-not-supported-by-the-provider"></a>Konwertowanie danych nieobsługiwanych przez dostawcę

Gdy odbiorca zażąda typu danych, który nie jest obsługiwany przez dostawcę, OLE DB kod szablonu dostawcy dla `IRowsetImpl::GetData` wywołań Msdadc.dll do konwersji typu danych.

W przypadku zaimplementowania interfejsu `IRowsetChange` , który wymaga konwersji danych, można wywołać Msdaenum.dll, aby wykonać konwersję. Użycie `GetData` , zdefiniowane w ATLDB. h, jako przykład.

## <a name="see-also"></a>Zobacz też

[Praca z szablonami dostawców OLE DB](../../data/oledb/working-with-ole-db-provider-templates.md)
