---
description: 'Dowiedz się więcej na temat: błąd krytyczny C1126'
title: Błąd krytyczny C1126
ms.date: 11/04/2016
f1_keywords:
- C1126
helpviewer_keywords:
- C1126
ms.assetid: f22b26a6-8ad7-47cf-a237-196c8ea60aca
ms.openlocfilehash: d6898b65bafa6862c77b10aa362ffc0a0df6e597
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97181010"
---
# <a name="fatal-error-c1126"></a>Błąd krytyczny C1126

"Identyfikator": Alokacja automatyczna przekracza rozmiar

Miejsce przydzielone na zmienne lokalne funkcji (oraz ograniczoną ilość miejsca używanej przez kompilator, takie jak dodatkowe 20 bajtów dla funkcji do zamiany) przekracza limit.

Aby naprawić ten błąd, użyj `malloc` lub, **`new`** Aby przydzielić duże ilości danych.
