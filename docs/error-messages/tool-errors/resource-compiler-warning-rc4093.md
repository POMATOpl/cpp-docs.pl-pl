---
description: 'Dowiedz się więcej na temat: RC4093 ostrzeżenia kompilatora zasobów'
title: Ostrzeżenie RC4093 kompilatora zasobów
ms.date: 11/04/2016
f1_keywords:
- RC4093
helpviewer_keywords:
- RC4093
ms.assetid: 3c61b4a4-b418-465b-a4fd-cb1ff0adb8dd
ms.openlocfilehash: 40f4777bb62fc2a5e434a4a365cdd027a04ffafd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97237091"
---
# <a name="resource-compiler-warning-rc4093"></a>Ostrzeżenie RC4093 kompilatora zasobów

niezmieniony nowy wiersz w stałej znakowej w nieaktywnym kodzie

Wyrażenie stałe dla `#if` `#elif` dyrektywy preprocesora,, **#ifdef** lub **#ifndef** zostało ocenione jako zero, wykonując kod, który jest nieaktywny. W tym nieaktywnym kodzie, znak nowego wiersza pojawił się w obrębie zestawu pojedynczego lub podwójnego cudzysłowu.

Cały tekst do momentu następnego podwójnego cudzysłowu był traktowany jako jako znak stałej.
