---
title: "Błąd krytyczny kompilatora zasobów RC1019 | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: RC1019
dev_langs: C++
helpviewer_keywords: RC1019
ms.assetid: 432fff44-04a9-4e13-91c6-870df6f0b4e4
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b2daee250bd3a8900f1c2eea12d105dfb3fd1026
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="resource-compiler-fatal-error-rc1019"></a>Błąd krytyczny kompilatora zasobów RC1019
nieoczekiwany ' #else "  
  
 `#else` Dyrektywy nie pojawił się w obrębie `#if`, **#ifdef**, lub **#ifndef** utworzenia.  
  
 Upewnij się, że istnieje `#if`, **#ifdef**, lub **#ifndef** instrukcji obowiązywać przed tej instrukcji.