---
description: 'Dowiedz się więcej na temat: błąd krytyczny C1854'
title: Błąd krytyczny C1854
ms.date: 11/04/2016
f1_keywords:
- C1854
helpviewer_keywords:
- C1854
ms.assetid: 8c21a9cc-1737-475c-9e57-8725cd8937c1
ms.openlocfilehash: 1c08db55089853545afa511213fc164c978bd4ff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97276208"
---
# <a name="fatal-error-c1854"></a>Błąd krytyczny C1854

> nie można zastąpić informacji utworzonych podczas tworzenia prekompilowanego nagłówka w pliku obiektu: "*filename*"

Określono opcję [/Yu (Użyj prekompilowanego pliku nagłówkowego)](../../build/reference/yu-use-precompiled-header-file.md) po określeniu opcji [/YC (Utwórz prekompilowany plik nagłówkowy)](../../build/reference/yc-create-precompiled-header-file.md) dla tego samego pliku.

Aby rozwiązać ten problem, na ogół Ustaw tylko jeden plik w projekcie do skompilowania przy użyciu opcji **/YC** i Ustaw wszystkie inne pliki do skompilowania przy użyciu opcji **/Yu** . Aby uzyskać szczegółowe informacje na temat używania opcji **/YC** i sposobu jej ustawiania w środowisku IDE programu Visual Studio, zobacz [/YC (Tworzenie prekompilowanego pliku nagłówkowego)](../../build/reference/yc-create-precompiled-header-file.md). Aby uzyskać więcej informacji na temat używania prekompilowanych nagłówków, zobacz [Tworzenie prekompilowanych plików nagłówkowych](../../build/creating-precompiled-header-files.md).
