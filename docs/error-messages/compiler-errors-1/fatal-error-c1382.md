---
description: 'Dowiedz się więcej na temat: błąd krytyczny C1382'
title: Błąd krytyczny C1382
ms.date: 11/04/2016
f1_keywords:
- C1382
helpviewer_keywords:
- C1382
ms.assetid: 7a100f8c-3179-4927-a2f1-98de4c753850
ms.openlocfilehash: fd2b9f48030d558a880a787114848dd0551b68ad
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97276520"
---
# <a name="fatal-error-c1382"></a>Błąd krytyczny C1382

plik PCH "File" został odbudowany od momentu wygenerowania "obj". Skompiluj ponownie ten obiekt

W przypadku korzystania z [/LTCG](../../build/reference/ltcg-link-time-code-generation.md)Kompilator wykrył plik. PCH, który jest NOWSZY niż CIL. obj wskazuje na to. Informacje w pliku CIL. obj są nieaktualne. Skompiluj ponownie obiekt.

C1382 może również wystąpić, Jeśli kompilujesz z **/YC**, ale również przekażesz wiele plików kodu źródłowego do kompilatora.  Aby rozwiązać ten problem, nie należy używać **/YC** podczas przekazywania wielu plików kodu źródłowego do kompilatora.  Aby uzyskać więcej informacji, zobacz [/YC (Create prekompilowany plik nagłówkowy)](../../build/reference/yc-create-precompiled-header-file.md).
