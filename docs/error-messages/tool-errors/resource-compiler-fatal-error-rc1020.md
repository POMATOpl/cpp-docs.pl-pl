---
description: 'Dowiedz się więcej na temat: błąd krytyczny kompilatora zasobów kompilatora zasobów RC1020'
title: Błąd krytyczny kompilatora zasobów RC1020
ms.date: 11/04/2016
f1_keywords:
- RC1020
helpviewer_keywords:
- RC1020
ms.assetid: 3e073ebf-9136-4bf8-ac6a-3c642ed64594
ms.openlocfilehash: a3ee2bd319cce9663c27030b523dd9e389158e45
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341090"
---
# <a name="resource-compiler-fatal-error-rc1020"></a>Błąd krytyczny kompilatora zasobów RC1020

Nieoczekiwany element "#endif"

`#endif`Dyrektywa pojawiła się bez pasującej `#if` dyrektywy, **#ifdef** lub **#ifndef** .

Upewnij się, że istnieje dopasowanie `#endif` dla każdej `#if` instrukcji, **#ifdef** i **#ifndef** .
