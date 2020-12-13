---
description: 'Dowiedz się więcej na temat: błąd krytyczny C1091'
title: Błąd krytyczny C1091
ms.date: 11/04/2016
f1_keywords:
- C1091
helpviewer_keywords:
- C1091
ms.assetid: 812d4201-9154-48b0-b9af-5959c082ca33
ms.openlocfilehash: 3863600e10dcfbef274424559e2cda0ca791406b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97145174"
---
# <a name="fatal-error-c1091"></a>Błąd krytyczny C1091

ograniczenie kompilatora: ciąg przekracza długość (w bajtach)

Stała ciągu przekracza bieżący limit długości ciągów.

Możesz chcieć podzielić ciąg statyczny na dwie zmienne (lub więcej) i użyć [strcpy_s](../../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md) , aby dołączyć wynik jako część deklaracji lub w czasie wykonywania.
