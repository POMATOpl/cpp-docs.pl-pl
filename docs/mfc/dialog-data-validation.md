---
description: 'Dowiedz się więcej na temat: sprawdzanie poprawności danych okna dialogowego'
title: Walidacja danych okna dialogowego
ms.date: 11/04/2016
helpviewer_keywords:
- validating data [MFC], message boxes
- data validation [MFC], dialog boxes
- dialog boxes [MFC], validating data
- validating data [MFC], dialog box data entry
- DDV (dialog data validation) [MFC]
- data validation [MFC], message boxes
ms.assetid: f070c309-2044-4ff2-8c92-1ec1ea84af58
ms.openlocfilehash: 0e90aa54130a59b48058928f56d9d36644d5142b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261362"
---
# <a name="dialog-data-validation"></a>Walidacja danych okna dialogowego

Możesz określić sprawdzanie poprawności oprócz wymiany danych przez wywołanie funkcji DDV, jak pokazano w przykładzie w [oknie dialogowym wymiany danych](dialog-data-exchange.md). `DDV_MaxChars`Wywołanie w przykładzie sprawdza, czy ciąg wprowadzony w kontrolce pola tekstowego nie jest dłuższy niż 20 znaków. Funkcja DDV zazwyczaj ostrzega użytkownika przy użyciu okna komunikatu, jeśli sprawdzanie poprawności zakończy się niepowodzeniem i umieści fokus na kontrolowanej kontroli, aby użytkownik mógł ponownie wprowadzić dane. Funkcja DDV dla danej kontrolki musi być wywoływana natychmiast po funkcji DDX dla tej samej kontrolki.

Można także definiować własne niestandardowe procedury DDX i DDV. Aby uzyskać szczegółowe informacje na temat tego i innych aspektów DDX i DDV, zobacz sekcję dotyczącą [MFC Technical uwagi 26](tn026-ddx-and-ddv-routines.md).

[Kreator dodawania zmiennej członkowskiej](../ide/adding-a-member-variable-visual-cpp.md#add-member-variable-wizard) będzie zapisywać wszystkie wywołania DDX i DDV na mapie danych.

## <a name="see-also"></a>Zobacz też

[Wymiana i walidacja danych w oknie dialogowym](dialog-data-exchange-and-validation.md)<br/>
[Praca z oknami dialogowymi w MFC](life-cycle-of-a-dialog-box.md)<br/>
[Wymiana danych w oknie dialogowym](dialog-data-exchange.md)
