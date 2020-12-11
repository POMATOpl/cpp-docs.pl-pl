---
description: 'Dowiedz się więcej o: eksportowania i importowania przy użyciu AFX_EXT_CLASS'
title: Eksportowanie i importowanie przy użyciu makra AFX_EXT_CLASS
ms.date: 11/04/2016
f1_keywords:
- afx_ext_class
helpviewer_keywords:
- AFX_EXT_CLASS macro
- exporting classes [C++]
- importing DLLs [C++]
- extension DLLs [C++], exporting classes
- executable files [C++], importing classes
- exporting DLLs [C++], AFX_EXT_CLASS macro
ms.assetid: 6b72cb2b-e92e-4ecd-bcab-c335e1d1cfde
ms.openlocfilehash: 9c82874b1e5e8791f2825cf6874399fab0e10eaa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97156687"
---
# <a name="exporting-and-importing-using-afx_ext_class"></a>Eksportowanie i importowanie przy użyciu makra AFX_EXT_CLASS

[Biblioteki DLL rozszerzenia MFC](extension-dlls-overview.md) używają **AFX_EXT_CLASS** makro do eksportowania klas; Pliki wykonywalne łączące się z biblioteką DLL rozszerzenia MFC używają makra do importowania klas. Za pomocą makra **AFX_EXT_CLASS** te same pliki nagłówkowe, które są używane do KOMPILOWANIA biblioteki DLL rozszerzenia MFC mogą być używane z plikami wykonywalnymi, które łączą się z biblioteką DLL.

W pliku nagłówkowym biblioteki DLL Dodaj słowo kluczowe **AFX_EXT_CLASS** do deklaracji klasy w następujący sposób:

```cpp
class AFX_EXT_CLASS CMyClass : public CDocument
{
// <body of class>
};
```

To makro jest definiowane przez MFC jako, `__declspec(dllexport)` gdy są zdefiniowane symbole preprocesora `_AFXDLL` i `_AFXEXT` . Ale makro jest zdefiniowane, `__declspec(dllimport)` gdy `_AFXDLL` jest zdefiniowane i `_AFXEXT` nie jest zdefiniowane. Po zdefiniowaniu, symbol preprocesora `_AFXDLL` wskazuje, że udostępniona wersja MFC jest używana przez docelowy plik wykonywalny (plik DLL lub aplikacja). Gdy obie `_AFXDLL` i `_AFXEXT` są zdefiniowane, oznacza to, że docelowy plik wykonywalny jest biblioteką DLL rozszerzenia MFC.

Ponieważ `AFX_EXT_CLASS` jest zdefiniowany jako `__declspec(dllexport)` podczas eksportowania z biblioteki DLL rozszerzenia MFC, można wyeksportować całe klasy bez umieszczania dekoracyjnych nazw dla wszystkich symboli tej klasy w pliku. def.

Chociaż można uniknąć tworzenia pliku. def i wszystkich nazw dekoracyjnych dla klasy przy użyciu tej metody, tworzenie pliku. def jest bardziej wydajne, ponieważ nazwy można eksportować według liczby porządkowej. Aby użyć metody eksportowania pliku. def, umieść następujący kod na początku i na końcu pliku nagłówka:

```cpp
#undef AFX_DATA
#define AFX_DATA AFX_EXT_DATA
// <body of your header file>
#undef AFX_DATA
#define AFX_DATA
```

> [!CAUTION]
> Należy zachować ostrożność podczas eksportowania funkcji wbudowanych, ponieważ mogą one spowodować konflikty wersji. Wbudowana funkcja zostanie rozwinięta w kodzie aplikacji; w związku z tym, jeśli później ponownie napiszesz funkcję, nie zostanie ona zaktualizowana, chyba że sama aplikacja zostanie ponowna skompilowana. Zwykle funkcje DLL można aktualizować bez konieczności ponownego kompilowania aplikacji, które z nich korzystają.

## <a name="exporting-individual-members-in-a-class"></a>Eksportowanie poszczególnych członków w klasie

Czasami warto wyeksportować poszczególnych członków klasy. Na przykład, Jeśli eksportujesz `CDialog` klasę pochodną, może być konieczne tylko wyeksportowanie konstruktora i `DoModal` wywołania. Można korzystać z `AFX_EXT_CLASS` poszczególnych członków, którzy chcą wyeksportować.

Na przykład:

```cpp
class CExampleDialog : public CDialog
{
public:
   AFX_EXT_CLASS CExampleDialog();
   AFX_EXT_CLASS int DoModal();
   ...
   // rest of class definition
   ...
};
```

Ponieważ nie można już eksportować wszystkich elementów członkowskich klasy, może się okazać, że wystąpił dodatkowy problem ze względu na sposób działania makr MFC. Niektóre makra pomocnika MFC w rzeczywistości deklarują lub definiują elementy członkowskie danych. W związku z tym te składowe danych również muszą zostać wyeksportowane z biblioteki DLL.

Na przykład `DECLARE_DYNAMIC` makro jest zdefiniowane w następujący sposób podczas kompilowania biblioteki DLL rozszerzenia MFC:

```cpp
#define DECLARE_DYNAMIC(class_name) \
protected: \
   static CRuntimeClass* PASCAL _GetBaseClass(); \
public: \
   static AFX_DATA CRuntimeClass class##class_name; \
   virtual CRuntimeClass* GetRuntimeClass() const; \
```

Wiersz zaczynający się od static `AFX_DATA` jest deklarujący obiekt statyczny wewnątrz klasy. Aby poprawnie wyeksportować tę klasę i uzyskać dostęp do informacji w czasie wykonywania z pliku wykonywalnego klienta, należy wyeksportować ten obiekt statyczny. Ponieważ obiekt statyczny jest zadeklarowany za pomocą modyfikatora `AFX_DATA` , wystarczy zdefiniować tylko `AFX_DATA` `__declspec(dllexport)` podczas kompilowania biblioteki DLL i zdefiniować go jako `__declspec(dllimport)` podczas kompilowania pliku wykonywalnego klienta. Ponieważ `AFX_EXT_CLASS` jest już zdefiniowany w ten sposób, wystarczy zmienić definicję, `AFX_DATA` aby była taka sama jak `AFX_EXT_CLASS` wokół definicji klasy.

Na przykład:

```cpp
#undef  AFX_DATA
#define AFX_DATA AFX_EXT_CLASS

class CExampleView : public CView
{
   DECLARE_DYNAMIC()
   // ... class definition ...
};

#undef  AFX_DATA
#define AFX_DATA
```

Ponieważ MFC zawsze używa `AFX_DATA` symbolu na elementach danych, który definiuje w jego makrach, ta technika działa w przypadku wszystkich takich scenariuszy. Na przykład działa w przypadku programu `DECLARE_MESSAGE_MAP` .

> [!NOTE]
> W przypadku eksportowania całej klasy, a nie wybranych elementów członkowskich klasy, statyczne elementy członkowskie danych są automatycznie eksportowane.

### <a name="what-do-you-want-to-do"></a>Co chcesz zrobić?

- [Eksportowanie z biblioteki DLL za pomocą plików. def](exporting-from-a-dll-using-def-files.md)

- [Eksportowanie z biblioteki DLL przy użyciu __declspec (dllexport)](exporting-from-a-dll-using-declspec-dllexport.md)

- [Eksportowanie funkcji języka C++ do użycia w plikach wykonywalnych języka C](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [Eksportowanie funkcji C do użycia w plikach wykonywalnych języka C lub C++](exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [Wybieranie metody eksportowania do użycia](determining-which-exporting-method-to-use.md)

- [Importowanie do aplikacji przy użyciu atrybutu __declspec(dllimport)](importing-into-an-application-using-declspec-dllimport.md)

- [Inicjowanie biblioteki DLL](run-time-library-behavior.md#initializing-a-dll)

### <a name="what-do-you-want-to-know-more-about"></a>Jak chcesz dowiedzieć się więcej?

- [Nazwy ozdobione](reference/decorated-names.md)

- [Importowanie i eksportowanie funkcji śródwierszowych](importing-and-exporting-inline-functions.md)

- [Importy wzajemne](mutual-imports.md)

## <a name="see-also"></a>Zobacz też

[Eksportowanie z biblioteki DLL](exporting-from-a-dll.md)
