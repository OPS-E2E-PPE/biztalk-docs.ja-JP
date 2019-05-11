---
title: アダプターの GetSchema メソッド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4c83340c-a775-435c-9633-3a692611e99e
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7a06e6eedb57ea0cbca1c4572ddf755b9915ca7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361467"
---
# <a name="adapter-getschema-method"></a><span data-ttu-id="ac25c-102">アダプターの GetSchema メソッド</span><span class="sxs-lookup"><span data-stu-id="ac25c-102">Adapter GetSchema Method</span></span>
<span data-ttu-id="ac25c-103">参照先の WSDL ファイルは、スキーマ参照のみが含まれていて、埋め込みスキーマが含まれていないとします。</span><span class="sxs-lookup"><span data-stu-id="ac25c-103">Suppose the referenced WSDL file contains only schema references and does not contain embedded schemas.</span></span> <span data-ttu-id="ac25c-104">この場合、使用して、 **GetSchema**のメソッド、 **IAdapterConfig**インターフェイス WSDL ファイル内から参照されるスキーマを読み込めません。</span><span class="sxs-lookup"><span data-stu-id="ac25c-104">In this case, you use the **GetSchema** method of the **IAdapterConfig** interface to load a schema referenced from within a WSDL file.</span></span>  
  
 <span data-ttu-id="ac25c-105">ファイル アダプターのサンプル コードを変更、 **GetSchema** WSDL ファイルに含まれていない外部 XSD ファイルを返すには、AdapterManagement.cs のメソッド。</span><span class="sxs-lookup"><span data-stu-id="ac25c-105">In the file adapter sample, modify the code in the **GetSchema** method of AdapterManagement.cs to return any external XSD files that are not included with the WSDL files.</span></span>  
  
 <span data-ttu-id="ac25c-106">次のコードは、 **GetSchema** AdapterManagement.cs ファイルのメソッド。</span><span class="sxs-lookup"><span data-stu-id="ac25c-106">The following code is from the **GetSchema** method of the AdapterManagement.cs file.</span></span> <span data-ttu-id="ac25c-107">ここで、Service1.wsdl ファイルには、埋め込みスキーマが含まれているため null 返します。</span><span class="sxs-lookup"><span data-stu-id="ac25c-107">It returns null here because the Service1.wsdl file contains embedded schemas.</span></span> <span data-ttu-id="ac25c-108">ない場合は、ケース、XSD スキーマ ファイルに対応する文字列は、返される必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac25c-108">If that were not the case, a string corresponding to an XSD schema file would need to be returned.</span></span>  
  
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