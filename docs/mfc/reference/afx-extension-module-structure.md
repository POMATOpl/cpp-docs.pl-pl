---
description: Dowiedz się więcej na temat struktury AFX_EXTENSION_MODULE
title: AFX_EXTENSION_MODULE — Struktura
ms.date: 11/04/2016
f1_keywords:
- AFX_EXTENSION_MODULE
helpviewer_keywords:
- AFX_EXTENSION_MODULE structure [MFC]
ms.assetid: b85a989c-d0c5-4b28-b53c-dad45b75704e
ms.openlocfilehash: d3a5abd449f13a06aa5d7388b2dd2926a6011973
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248232"
---
# <a name="afx_extension_module-structure"></a>AFX_EXTENSION_MODULE — Struktura

`AFX_EXTENSION_MODULE`Jest używany podczas inicjowania bibliotek DLL rozszerzenia MFC w celu przechowywania stanu modułu DLL rozszerzenia MFC.

## <a name="syntax"></a>Składnia

```
struct AFX_EXTENSION_MODULE
{
    BOOL bInitialized;
    HMODULE hModule;
    HMODULE hResource;
    CRuntimeClass* pFirstSharedClass;
    COleObjectFactory* pFirstSharedFactory;
};
```

#### <a name="parameters"></a>Parametry

*bInitialized*<br/>
Ma wartość TRUE, jeśli moduł DLL został zainicjowany przy użyciu `AfxInitExtensionModule` .

*hModule*<br/>
Określa uchwyt modułu DLL.

*hResource*<br/>
Określa uchwyt niestandardowego modułu zasobów DLL.

*pFirstSharedClass*<br/>
Wskaźnik do informacji ( `CRuntimeClass` struktury) dotyczących pierwszej klasy środowiska uruchomieniowego modułu dll. Służy do podania początku listy klas środowiska uruchomieniowego.

*pFirstSharedFactory*<br/>
Wskaźnik do pierwszej fabryki obiektów modułu DLL ( `COleObjectFactory` obiekt). Służy do podania początku listy fabryk klas.

## <a name="remarks"></a>Uwagi

Biblioteki DLL rozszerzenia MFC muszą wykonywać dwie rzeczy w `DllMain` funkcji:

- Wywołaj [AfxInitExtensionModule](extension-dll-macros.md#afxinitextensionmodule) i sprawdź wartość zwracaną.

- Utwórz `CDynLinkLibrary` obiekt, jeśli biblioteka DLL będzie eksportować obiekty [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) lub ma własne zasoby niestandardowe.

`AFX_EXTENSION_MODULE`Struktura służy do przechowywania kopii stanu modułu biblioteki DLL rozszerzenia MFC, łącznie z kopią obiektów klasy środowiska uruchomieniowego, która została zainicjowana przez bibliotekę DLL rozszerzenia MFC w ramach normalnej konstrukcji obiektu statycznego wykonanej przed `DllMain` wprowadzeniem. Na przykład:

[!code-cpp[NVC_MFC_DLL#2](../../atl-mfc-shared/codesnippet/cpp/afx-extension-module-structure_1.cpp)]

Informacje o modułach przechowywane w `AFX_EXTENSION_MODULE` strukturze można skopiować do `CDynLinkLibrary` obiektu. Na przykład:

[!code-cpp[NVC_MFC_DLL#5](../../atl-mfc-shared/codesnippet/cpp/afx-extension-module-structure_2.cpp)]

## <a name="requirements"></a>Wymagania

**Nagłówek:** AFX. h

## <a name="see-also"></a>Zobacz też

[Struktury, style, wywołania zwrotne i mapy komunikatów](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[AfxInitExtensionModule](extension-dll-macros.md#afxinitextensionmodule)<br/>
[AfxTermExtensionModule](extension-dll-macros.md#afxtermextensionmodule)
