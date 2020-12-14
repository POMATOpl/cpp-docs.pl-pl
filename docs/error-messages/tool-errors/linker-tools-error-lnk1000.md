---
description: 'Dowiedz się więcej na temat: Błąd narzędzi konsolidatora LNK1000'
title: Błąd narzędzi konsolidatora LNK1000
ms.date: 06/18/2018
f1_keywords:
- LNK1000
helpviewer_keywords:
- LNK1000
ms.assetid: 86421b9a-460a-4285-8dce-9b8257d78122
ms.openlocfilehash: 54692b635b83756a26490779c0205ccc5f20d3bf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261609"
---
# <a name="linker-tools-error-lnk1000"></a>Błąd narzędzi konsolidatora LNK1000

> nieznany błąd; Zapoznaj się z dokumentacją dotyczącą opcji pomocy technicznej

Zanotuj sytuacje błędu, a następnie spróbuj wyizolować problem i utworzyć powtarzalny przypadek testowy. Aby uzyskać informacje o tym, jak zbadać i zgłosić te błędy, zobacz artykuł [Jak zgłosić problem z zestawem narzędzi Visual C++ lub dokumentacją](../../overview/how-to-report-a-problem-with-the-visual-cpp-toolset.md).

Ten błąd może wystąpić, jeśli Mieszasz standardowe pliki nagłówkowe (na przykład Windows. h) i własne pliki. Dołącz prekompilowany nagłówek (jeśli istnieje), a następnie nagłówki standardowe, a następnie własne pliki nagłówkowe.
