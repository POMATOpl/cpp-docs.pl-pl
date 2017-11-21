---
title: PTR::GetInterface | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ptr::GetInterface
- msclr::com::ptr::GetInterface
- GetInterface
- msclr.com.ptr.GetInterface
- ptr.GetInterface
dev_langs: C++
helpviewer_keywords: GetInterface method
ms.assetid: d85553ec-fb88-4fd6-9df2-ddcaa8b2dc70
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a86741e9047694dda61e306afb164dc2cc2bbf98
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="ptrgetinterface"></a>ptr::GetInterface
Zwraca wskaźnik do obiektu COM, należące do firmy.  
  
## <a name="syntax"></a>Składnia  
  
```  
_interface_type * GetInterface();  
```  
  
## <a name="return-value"></a>Wartość zwracana  
 Wskaźnik do obiektu COM, należące do firmy.  
  
## <a name="exceptions"></a>Wyjątki  
 Wewnętrznie `QueryInterface` wywołano należących do obiektu COM i wszelkich błędów `HRESULT` jest konwertowana na wyjątek przez <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>.  
  
## <a name="remarks"></a>Uwagi  
 `com::ptr` Dodaje odwołanie do obiektu modelu COM w imieniu wywołującego oraz zachowanie własne odwołanie do obiektu COM. Obiekt wywołujący musi ostatecznie zwolnienia odwołania na zwracanym obiekcie lub nigdy nie zostaną usunięte.  
  
## <a name="example"></a>Przykład  
 W tym przykładzie implementuje klasy CLR, która używa `com::ptr` opakowywać jego prywatnego elementu członkowskiego `IXMLDOMDocument` obiektu. `GetDocument` Korzysta z funkcji członkowskiej `GetInterface` do zwraca wskaźnik do obiektu COM.  
  
```  
// comptr_getinterface.cpp  
// compile with: /clr /link msxml2.lib  
#include <msxml2.h>  
#include <msclr\com\ptr.h>  
  
#import <msxml3.dll> raw_interfaces_only  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
using namespace msclr;  
  
// a ref class that uses a com::ptr to contain an   
// IXMLDOMDocument object  
ref class XmlDocument {  
public:  
   // construct the internal com::ptr with a null interface  
   // and use CreateInstance to fill it  
   XmlDocument(String^ progid) {  
      m_ptrDoc.CreateInstance(progid);     
   }  
  
   // add a reference to and return the COM object  
   // but keep an internal reference to the object  
   IXMLDOMDocument* GetDocument() {  
      return m_ptrDoc.GetInterface();  
   }  
  
   // simplified function that only writes the first node  
   void WriteDocument() {  
      IXMLDOMNode* pNode = NULL;  
      BSTR bstr = NULL;  
  
      try {  
         // use operator -> to call XML Doc member  
         Marshal::ThrowExceptionForHR(m_ptrDoc->get_firstChild(&pNode));  
         if (NULL != pNode) {  
            // write out the xml  
            Marshal::ThrowExceptionForHR(pNode->get_nodeName(&bstr));  
            String^ strName = gcnew String(bstr);  
            Console::Write("<{0}>", strName);  
            ::SysFreeString(bstr);  
            bstr = NULL;  
  
            Marshal::ThrowExceptionForHR(pNode->get_text(&bstr));  
            Console::Write(gcnew String(bstr));  
            ::SysFreeString(bstr);  
            bstr = NULL;  
  
            Console::WriteLine("</{0}>", strName);  
         }  
      }  
      finally {  
         if (NULL != pNode) {  
            pNode->Release();  
         }  
         ::SysFreeString(bstr);  
      }  
   }  
  
   // note that the destructor will call the com::ptr destructor  
   // and automatically release the reference to the COM object  
  
private:  
   com::ptr<IXMLDOMDocument> m_ptrDoc;  
};  
  
// unmanaged function that loads XML into a raw XML DOM Document object  
HRESULT LoadXml(IXMLDOMDocument* pDoc, BSTR bstrXml) {  
   HRESULT hr = S_OK;  
   VARIANT_BOOL bSuccess;  
   hr = pDoc->loadXML(bstrXml, &bSuccess);  
   if (S_OK == hr && !bSuccess) {  
      hr = E_FAIL;  
   }  
   return hr;  
}  
  
// use the ref class to handle an XML DOM Document object  
int main() {  
   IXMLDOMDocument* pDoc = NULL;  
   BSTR bstrXml = NULL;  
  
   try {  
      // create the class from a progid string  
      XmlDocument doc("Msxml2.DOMDocument.3.0");  
  
      bstrXml = ::SysAllocString(L"<word>persnickety</word>");  
      if (NULL == bstrXml) {  
         throw gcnew OutOfMemoryException("bstrXml");  
      }  
      // detach the document object from the ref class  
      pDoc = doc.GetDocument();  
      // use unmanaged function and raw object to load xml  
      Marshal::ThrowExceptionForHR(LoadXml(pDoc, bstrXml));  
      // release reference to document object (but ref class still references it)  
      pDoc->Release();  
      pDoc = NULL;  
  
      // call another function on the ref class  
      doc.WriteDocument();  
   }  
   catch (Exception^ e) {  
      Console::WriteLine(e);     
   }  
   finally {  
      if (NULL != pDoc) {  
         pDoc->Release();  
      }  
  
   }  
}  
```  
  
```Output  
<word>persnickety</word>  
```  
  
## <a name="requirements"></a>Wymagania  
 **Plik nagłówka** \<msclr\com\ptr.h >  
  
 **Namespace** msclr::com  
  
## <a name="see-also"></a>Zobacz też  
 [elementy członkowskie PTR](../dotnet/ptr-members.md)   
 [PTR::QueryInterface](../dotnet/ptr-queryinterface.md)