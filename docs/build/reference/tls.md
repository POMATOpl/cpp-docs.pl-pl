---
description: Dowiedz się więcej na temat:/TLS
title: /TLS
ms.date: 11/04/2016
f1_keywords:
- /TLS
helpviewer_keywords:
- /TLS dumpbin option
- -TLS dumpbin option
ms.assetid: 2b3f48f9-cac4-4351-b15c-2833b43bc709
ms.openlocfilehash: a21ef03210a65bb50899ba3907911272ac52b0db
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97229954"
---
# <a name="tls"></a>/TLS

Wyświetla strukturę IMAGE_TLS_DIRECTORY z pliku wykonywalnego.

## <a name="remarks"></a>Uwagi

/TLS wyświetla pola struktury TLS, a także adresy funkcji wywołania zwrotnego protokołu TLS.

Jeśli program nie używa lokalnego magazynu wątków, jego obraz nie będzie zawierał struktury TLS.  Aby uzyskać więcej informacji, zobacz [wątek](../../cpp/thread.md) .

IMAGE_TLS_DIRECTORY jest zdefiniowany w pliku Winnt. h.

## <a name="see-also"></a>Zobacz też

[Opcje polecenia DUMPBIN](dumpbin-options.md)
