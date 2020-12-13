---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 3) C4192'
title: Ostrzeżenie kompilatora (poziom 3) C4192
ms.date: 11/04/2016
f1_keywords:
- C4192
helpviewer_keywords:
- C4192
ms.assetid: ea5f91fa-8c96-4f3f-ac42-0c8a86d4e5df
ms.openlocfilehash: 8cfebf1845c578723bab5622e18699c0282d4c4b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344227"
---
# <a name="compiler-warning-level-3-c4192"></a>Ostrzeżenie kompilatora (poziom 3) C4192

automatyczne wykluczanie "name" podczas importowania biblioteki typów "Library"

`#import`Biblioteka zawiera element, *nazwę*, która jest również zdefiniowana w nagłówkach systemu Win32. Ze względu na ograniczenia bibliotek typów, nazwy takie jak **IUnknown** lub GUID są często definiowane w bibliotece typów, duplikując definicję z nagłówków systemowych. `#import` wykrywa te elementy i odmawia ich dołączenia do plików nagłówkowych. tlh i. tli.

Aby zastąpić to zachowanie, użyj `#import` atrybutów [no_auto_exclude](../../preprocessor/no-auto-exclude.md) i [include ()](../../preprocessor/include-parens.md).
