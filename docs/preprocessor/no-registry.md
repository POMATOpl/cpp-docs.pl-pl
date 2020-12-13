---
description: 'Dowiedz się więcej na temat: no_registry Importowanie atrybutu'
title: no_registry atrybut importowania
ms.date: 08/29/2019
f1_keywords:
- no_registry
helpviewer_keywords:
- no_registry attribute
ms.assetid: d30de4e2-551c-428c-98fd-951330d578d3
ms.openlocfilehash: fa33bf8096a92ec248b0a9d56e39fcc82f433206
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333296"
---
# <a name="no_registry-import-attribute"></a>no_registry atrybut importowania

**no_registry** instruuje kompilator, aby nie przeszukać rejestru dla bibliotek typów importowanych z `#import` .

## <a name="syntax"></a>Składnia

> **#import** **no_registry** *biblioteki typów*

### <a name="parameters"></a>Parametry

*Biblioteka typów*\
Biblioteka typów.

## <a name="remarks"></a>Uwagi

Jeśli przywoływana biblioteka typów nie została znaleziona w katalogach dołączanych, kompilacja kończy się niepowodzeniem, nawet jeśli biblioteka typów znajduje się w rejestrze.  **no_registry** propaguje do innych bibliotek typów niejawnie zaimportowanych przy użyciu `auto_search` .

Kompilator nigdy nie przeszukuje rejestru dla bibliotek typów, które są określone przez nazwę pliku i są przesyłane bezpośrednio do `#import` .

Gdy `auto_search` jest określony, dodatkowe `#import` dyrektywy są generowane przy użyciu ustawienia **no_registry** początkowego `#import` . Jeśli wstępna `#import` dyrektywa została **no_registry**, `auto_search` generowana `#import` jest również **no_registry**.

**no_registry** jest przydatne, jeśli chcesz zaimportować biblioteki typów, do których istnieją odwołania. Uniemożliwia ona kompilatorowi znalezienie starszej wersji pliku w rejestrze. **no_registry** jest również przydatna, jeśli biblioteka typów nie jest zarejestrowana.

## <a name="see-also"></a>Zobacz też

[Atrybuty #import](../preprocessor/hash-import-attributes-cpp.md)\
[#import — dyrektywa](../preprocessor/hash-import-directive-cpp.md)
