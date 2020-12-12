---
description: 'Dowiedz się więcej na temat: błąd krytyczny kompilatora zasobów kompilatora zasobów RW1025'
title: Błąd krytyczny kompilatora zasobów RW1025
ms.date: 11/04/2016
f1_keywords:
- RW1025
helpviewer_keywords:
- RW1025
ms.assetid: 561a02af-e7e0-442a-8ad3-a00b2ca1b62e
ms.openlocfilehash: 40404f8d6dc16b73f93255a18ce8c632cc1e014a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97237195"
---
# <a name="resource-compiler-fatal-error-rw1025"></a>Błąd krytyczny kompilatora zasobów RW1025

Za mało pamięci sterty

Sprawdź, czy jest używane oprogramowanie rezydentne pamięci, które może zużywać zbyt dużo miejsca. Użyj programu CHKDSK, aby dowiedzieć się, ile masz pamięci.

W przypadku tworzenia dużego pliku zasobów Podziel skrypt zasobu na dwa pliki. Po utworzeniu dwóch plików. res Użyj wiersza polecenia systemu MS-DOS, aby dołączyć je razem:

```
copy first.res /b + second.res /b full.res
```
