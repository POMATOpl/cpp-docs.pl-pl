---
description: 'Dowiedz się więcej o: flagi kontrolek'
title: Flagi kontrolne
ms.date: 11/04/2016
f1_keywords:
- c.flags
helpviewer_keywords:
- flags, control
- heap allocation, control flags
- debug heap, control flags
ms.assetid: 8dbd24a5-0633-42d1-9771-776db338465f
ms.openlocfilehash: 6b49bfa49e2e231a64af8d88739778964ce8ed21
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195739"
---
# <a name="control-flags"></a>Flagi kontrolne

Wersja do debugowania biblioteki wykonawczej Microsoft C używa następujących flag do sterowania procesem alokacji sterty i raportowania. Aby uzyskać więcej informacji, zobacz [techniki debugowania CRT](/visualstudio/debugger/crt-debugging-techniques).

|Flaga|Opis|
|----------|-----------------|
|[_CRTDBG_MAP_ALLOC](../c-runtime-library/crtdbg-map-alloc.md)|Mapuje funkcje sterty bazowej na ich odpowiedniki wersji debugowania|
|[_DEBUG](../c-runtime-library/debug.md)|Umożliwia korzystanie z wersji debugowania funkcji czasu wykonywania|
|[_crtDbgFlag](../c-runtime-library/crtdbgflag.md)|Kontroluje, jak Menedżer sterty debugowania śledzi alokacje|

Flagi te można zdefiniować za pomocą/D opcji wiersza polecenia lub `#define` dyrektywy. Gdy flaga jest zdefiniowana za pomocą `#define` , dyrektywa musi występować przed instrukcją include pliku nagłówkowego dla deklaracji rutynowych.

## <a name="see-also"></a>Zobacz też

[Zmienne globalne i typy standardowe](../c-runtime-library/global-variables-and-standard-types.md)
