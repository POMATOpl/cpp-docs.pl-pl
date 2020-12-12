---
description: 'Dowiedz się więcej na temat: _crtDbgFlag'
title: _crtDbgFlag
ms.date: 11/04/2016
f1_keywords:
- _crtDbgFlag
- crtDbgFlag
helpviewer_keywords:
- memory allocation, tracking flag
- crtDbgFlag constant
- _crtDbgFlag constant
- debug heap, tracking memory on
- debug heap, control flags
- enable memory allocation tracking flag
- memory, tracking on the debug heap
ms.assetid: 9e7adb47-8ab9-4e19-81d5-e2f237979973
ms.openlocfilehash: ef3c72b89ea9e5e557a567af9a9c52c8e85370ce
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97246766"
---
# <a name="_crtdbgflag"></a>_crtDbgFlag

Flaga **_crtDbgFlag** składa się z pięciu pól bitowych, które kontrolują sposób, w jaki alokacje pamięci w debugowanej wersji sterty są śledzone, weryfikowane, raportowane i zrzucane. Pola bitowe flagi są ustawiane za pomocą funkcji [_CrtSetDbgFlag](../c-runtime-library/reference/crtsetdbgflag.md) . Ta flaga i jego pola bitowe są zadeklarowane w CRTDBG. h. Ta flaga jest dostępna tylko wtedy, gdy flaga [_DEBUG](../c-runtime-library/debug.md) została zdefiniowana w aplikacji.

Aby uzyskać więcej informacji na temat używania tej flagi w połączeniu z innymi funkcjami debugowania, zobacz [funkcje raportowania stanu sterty](/visualstudio/debugger/crt-debug-heap-details).

## <a name="see-also"></a>Zobacz też

[Flagi kontrolki](../c-runtime-library/control-flags.md)
