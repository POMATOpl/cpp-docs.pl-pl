---
description: 'Dowiedz się więcej na temat: błąd krytyczny C1047'
title: Błąd krytyczny C1047
ms.date: 11/04/2016
f1_keywords:
- C1047
helpviewer_keywords:
- C1047
ms.assetid: e1bbbc6b-a5bc-4c23-8203-488120a0ec78
ms.openlocfilehash: e3aa85fb777850ce6ee754ee89b9e351b5eba975
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341194"
---
# <a name="fatal-error-c1047"></a>Błąd krytyczny C1047

Obiekt lub plik biblioteki "File" został utworzony za pomocą starszego kompilatora niż inne obiekty; ponowne kompilowanie starych obiektów i bibliotek

C1047 jest spowodowany tym, że pliki obiektów lub biblioteki skompilowane za pomocą **/LTCG** są połączone ze sobą, ale gdzie te pliki lub biblioteki zostały skompilowane przy użyciu różnych wersji zestawu narzędzi Visual C++.

Taka sytuacja może wystąpić, jeśli zaczniesz korzystać z nowej wersji kompilatora, ale nie przeprowadzaj czystej odbudowy istniejących plików lub bibliotek obiektów.

Aby rozwiązać C1047, Skompiluj ponownie wszystkie pliki lub biblioteki obiektów.
