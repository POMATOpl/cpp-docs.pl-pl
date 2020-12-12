---
description: 'Dowiedz się więcej o: Izolacja biblioteki formantów wspólnych MFC'
title: Izolacja biblioteki formantów wspólnych MFC
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, Common Controls library
ms.assetid: 7471e6f0-49b0-47f7-86e7-8d6bc3541694
ms.openlocfilehash: f3e0f6ad981a690f6212455b8af891eaa97f2642
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335822"
---
# <a name="isolation-of-the-mfc-common-controls-library"></a>Izolacja biblioteki formantów wspólnych MFC

Biblioteka wspólnych kontrolek jest teraz izolowana w ramach MFC, co pozwala różnym modułom (takim jak biblioteki DLL użytkownika) używać różnych wersji biblioteki wspólnych formantów, określając wersję w ich manifestach.

Aplikacja MFC (lub kod użytkownika wywoływany przez MFC) wywołuje wywołania do interfejsów API biblioteki wspólnych kontrolek za pomocą funkcji otoki o nazwie `Afx` *FunctionName*, gdzie *FUNCTIONNAME* jest nazwą interfejsu API wspólnych kontrolek. Te funkcje otoki są zdefiniowane w afxcomctl32. h i afxcomctl32. inl.

Można użyć makr [AFX_COMCTL32_IF_EXISTS](reference/run-time-object-model-services.md#afx_comctl32_if_exists) i [AFX_COMCTL32_IF_EXISTS2](reference/run-time-object-model-services.md#afx_comctl32_if_exists2) (zdefiniowanych w afxcomctl32. h), aby określić, czy Biblioteka formantów wspólnych implementuje określony interfejs API zamiast wywoływania [GetProcAddress](../build/getprocaddress.md).

Technicznie, wywołania interfejsów API biblioteki wspólnych formantów są nawiązywane za pomocą klasy otoki `CComCtlWrapper` (zdefiniowanej w afxcomctl32. h). `CComCtlWrapper` jest również odpowiedzialny za ładowanie i wyładowywanie comctl32.dll. Stan modułu MFC zawiera wskaźnik do wystąpienia `CComCtlWrapper` . Możesz uzyskać dostęp do klasy otoki przy użyciu `afxComCtlWrapper` makra.

Należy zauważyć, że wywołanie interfejsu API wspólnych formantów (nieużywające funkcji otoki MFC) z aplikacji MFC lub biblioteki DLL użytkownika będzie działać w większości przypadków, ponieważ aplikacja MFC lub biblioteka DLL użytkownika jest powiązana z biblioteką wspólnych kontrolek, której żądał w manifeście. Jednak kod MFC musi używać otok, ponieważ kod MFC może być wywoływany z bibliotek DLL użytkownika z różnymi wersjami bibliotek wspólnych formantów.
