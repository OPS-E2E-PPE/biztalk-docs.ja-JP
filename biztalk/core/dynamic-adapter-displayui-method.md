---
title: 動的アダプターの DisplayUI メソッド |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9183d2ee-4265-4fee-9d1d-7e2462d8ff37
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd26bc5e5e344f53537e16135bf0a30b8b1443c8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238674"
---
# <a name="dynamic-adapter-displayui-method"></a><span data-ttu-id="3a8ce-102">動的アダプターの DisplayUI メソッド</span><span class="sxs-lookup"><span data-stu-id="3a8ce-102">Dynamic Adapter DisplayUI Method</span></span>
<span data-ttu-id="3a8ce-103">このメソッドを**IDynamicAdapterConfig**インターフェイスには、カスタム アダプターのカスタム ユーザー インターフェイスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3a8ce-103">This method on the **IDynamicAdapterConfig** interface displays the custom user interface for the custom adapter.</span></span> <span data-ttu-id="3a8ce-104">これにより、ユーザーは、選択したサービスに基づいて関連のサポート ファイルを表示、選択し、BizTalk プロジェクトにインポートできます。</span><span class="sxs-lookup"><span data-stu-id="3a8ce-104">This enables the user to view, select, and import the related supporting files based upon the selected services into their BizTalk project.</span></span>  
  
 <span data-ttu-id="3a8ce-105">ファイル アダプター内のコードを変更、 **displayUI**を受け入れるようにスキーマの種類を選択するためのカスタム ユーザー インターフェイス (UI) を作成する AdapterManagement.cs ファイルのメソッドです。</span><span class="sxs-lookup"><span data-stu-id="3a8ce-105">In the file adapter, modify the code within the **displayUI** method of the AdapterManagement.cs file to create a custom user interface (UI) for selecting the type of schema to accept.</span></span> <span data-ttu-id="3a8ce-106">スキーマが選択された後に、適切な WSDL ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="3a8ce-106">After a schema is selected, choose the appropriate WSDL file.</span></span>  
  
 <span data-ttu-id="3a8ce-107">次のコードは、 **displayUI** AdapterManagement.cs ファイルのメソッドです。</span><span class="sxs-lookup"><span data-stu-id="3a8ce-107">The following code is from the **displayUI** method of the AdapterManagement.cs file.</span></span>  
  
```  
/// <summary>  
        /// Acquire wsdl(s) from which to build the user interface  
        /// </summary>  
        /// <param name="endPointConfiguration"></param>  
        /// <param name="owner"></param>  
        /// <param name="WSDLList">Array of custom UI's WSDL (returned)</param>  
        /// <returns></returns>  
        public Result DisplayUI(IPropertyBag endPointConfiguration,   
            IWin32Window owner,  
            out string [] WSDLList)   
      {  
            WSDLList = new string[1];  
            WSDLList[0] = GetResource("AdapterManagement.service1.wsdl");  
            return Result.Continue;  
        }  
```