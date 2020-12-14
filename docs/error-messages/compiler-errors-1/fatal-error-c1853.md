---
description: 'Dowiedz się więcej na temat: błąd krytyczny C1853'
title: Błąd krytyczny C1853
ms.date: 11/04/2016
f1_keywords:
- C1853
helpviewer_keywords:
- C1853
ms.assetid: ceb9b4a5-92bf-4573-8a9f-3109cc7743ce
ms.openlocfilehash: 60c8e254e9bd36f52bddb4d6dce56c987b6c31e1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97276234"
---
# <a name="fatal-error-c1853"></a>Błąd krytyczny C1853

> prekompilowany plik nagłówkowy "*filename*" pochodzi z poprzedniej wersji kompilatora lub prekompilowany nagłówek to C++ i jest używany w języku C (lub odwrotnie)

Możliwe przyczyny:

- Prekompilowany nagłówek został skompilowany z poprzednią wersją kompilatora. Spróbuj ponownie skompilować nagłówek przy użyciu bieżącego kompilatora.

- Prekompilowany nagłówek to C++ i jest używany z dysku C. Spróbuj ponownie skompilować nagłówek do użycia z C, określając jedną z opcji kompilatora [/TC](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) lub zmieniając sufiks pliku źródłowego na "c". Aby uzyskać więcej informacji, zobacz [dwie opcje wstępnego kompilowania kodu](../../build/creating-precompiled-header-files.md#two-choices-for-precompiling-code).
