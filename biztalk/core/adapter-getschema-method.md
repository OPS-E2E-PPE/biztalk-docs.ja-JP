---
title: "アダプターの GetSchema メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4c83340c-a775-435c-9633-3a692611e99e
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c40e698b3c373aa4e10a8de2362650a42e71a1c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="adapter-getschema-method"></a><span data-ttu-id="e4a32-102">アダプターの GetSchema メソッド</span><span class="sxs-lookup"><span data-stu-id="e4a32-102">Adapter GetSchema Method</span></span>
<span data-ttu-id="e4a32-103">参照されている WSDL ファイルが、スキーマ参照のみを含み、埋め込みスキーマを含まないものとします。</span><span class="sxs-lookup"><span data-stu-id="e4a32-103">Suppose the referenced WSDL file contains only schema references and does not contain embedded schemas.</span></span> <span data-ttu-id="e4a32-104">この場合、使用して、 **GetSchema**のメソッド、 **IAdapterConfig**インターフェイス WSDL ファイル内から参照されるスキーマを読み込めません。</span><span class="sxs-lookup"><span data-stu-id="e4a32-104">In this case, you use the **GetSchema** method of the **IAdapterConfig** interface to load a schema referenced from within a WSDL file.</span></span>  
  
 <span data-ttu-id="e4a32-105">ファイル アダプターのサンプルのコードを変更、 **GetSchema** WSDL ファイルに含まれていない外部 XSD ファイルを返すには、AdapterManagement.cs のメソッドです。</span><span class="sxs-lookup"><span data-stu-id="e4a32-105">In the file adapter sample, modify the code in the **GetSchema** method of AdapterManagement.cs to return any external XSD files that are not included with the WSDL files.</span></span>  
  
 <span data-ttu-id="e4a32-106">次のコードは、 **GetSchema** AdapterManagement.cs ファイルのメソッドです。</span><span class="sxs-lookup"><span data-stu-id="e4a32-106">The following code is from the **GetSchema** method of the AdapterManagement.cs file.</span></span> <span data-ttu-id="e4a32-107">Service1.wsdl ファイルには埋め込みスキーマが含まれるので、ここでは Null を返します。</span><span class="sxs-lookup"><span data-stu-id="e4a32-107">It returns null here because the Service1.wsdl file contains embedded schemas.</span></span> <span data-ttu-id="e4a32-108">そうでない場合は、XSD スキーマ ファイルに対応する文字列を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4a32-108">If that were not the case, a string corresponding to an XSD schema file would need to be returned.</span></span>  
  
```  
/// <summary>  
        /// Acquire externally referenced xsd's  
        /// </summary>  
        /// <param name="xsdLocation">Location of schema</param>  
        /// <param name="xsdNamespace">Namespace</param>  
        /// <param name="XSDFileName">Schmea file name (return)</param>  
        /// <returns>Outcome of acquisition</returns>  
        public Result GetSchema(string xsdLocation,  
                                string xsdNamespace,  
                        out string xsdSchema)   
      {  
            xsdSchema = null;  
            return Result.Continue;  
        }  
```