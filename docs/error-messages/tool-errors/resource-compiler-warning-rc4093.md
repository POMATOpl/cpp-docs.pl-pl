---
title: "Ostrzeżenie RC4093 kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: RC4093
dev_langs: C++
helpviewer_keywords: RC4093
ms.assetid: 3c61b4a4-b418-465b-a4fd-cb1ff0adb8dd
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4d21cbba379e72675b8957be58dc712b83673947
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-warning-rc4093"></a>Ostrzeżenie RC4093 kompilatora zasobów
niezmienionym znaczeniu nowego wiersza w stałej znakowej w nieaktywnego kodu  
  
 Stałe wyrażenie `#if`, `#elif`, **#ifdef**, lub **#ifndef** dyrektywy preprocesora obliczoną wartością zero, co kod, który wykonuje nieaktywne. W tym nieaktywnego kodu znaku nowego wiersza znajdowały się w ramach zestawu jednej lub podwójny cudzysłów.  
  
 Cały tekst do czasu następnego podwójny cudzysłów został uznany za w stałej znakowej.