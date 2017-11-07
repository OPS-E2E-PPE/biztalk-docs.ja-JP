---
title: "SSO Projects1 を実行している |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SSO projects
- running SSO projects
- samples, SSO projects
ms.assetid: f8da1874-7495-47cd-a3a3-881f722c80a2
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea316e8f2c78ff718d6821b3f5d063bd86621dd1
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="running-sso-projects"></a><span data-ttu-id="92d68-102">SSO プロジェクトの実行</span><span class="sxs-lookup"><span data-stu-id="92d68-102">Running SSO Projects</span></span>
<span data-ttu-id="92d68-103">このサンプルは、インターネット エクスプローラーから実行できます。</span><span class="sxs-lookup"><span data-stu-id="92d68-103">You can run the sample  from Internet Explorer.</span></span>  
  
## <a name="running-a-sample-from-internet-explorer"></a><span data-ttu-id="92d68-104">Internet Explorer からサンプルを実行する</span><span class="sxs-lookup"><span data-stu-id="92d68-104">Running a Sample from Internet Explorer</span></span>  
  
#### <a name="to-run-the-sample-from-the-internet-explorer"></a><span data-ttu-id="92d68-105">Internet Explorer からサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="92d68-105">To run the sample from the Internet Explorer</span></span>  
  
1.  <span data-ttu-id="92d68-106">ブラウザーを開きます。</span><span class="sxs-lookup"><span data-stu-id="92d68-106">Open your browser.</span></span>  
  
2.  <span data-ttu-id="92d68-107">次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="92d68-107">Use the following syntax:</span></span>  
  
    ```  
    http://localhost/SSODemo/BTSHTTPReceive.dll?[Insert XML Instance body]   
    ```  
  
     <span data-ttu-id="92d68-108">例:</span><span class="sxs-lookup"><span data-stu-id="92d68-108">For example:</span></span>  
  
     <span data-ttu-id="92d68-109">http://localhost/SSODemo/BTSHTTPReceive.dll?\<ns0:method_list_method %20xmlns: ns0 ="http://microsoft.com/exposed/object/object1">\<ns0:method_list_method >\<ns1:method_list %20xmlns: ns1 ="http://microsoft.com/exposed/object">\<ns1:comp_code >\</ns1:comp_code >\<ns1:comp_name >\</ns1:comp_name >\< /ns1:object_1 >\</ns0:method_list >\</ns0:method_list_method ></span><span class="sxs-lookup"><span data-stu-id="92d68-109">http://localhost/SSODemo/BTSHTTPReceive.dll?\<ns0:method_list_method%20xmlns:ns0="http://microsoft.com/exposed/object/object1">\<ns0:method_list_method>\<ns1:method_list%20xmlns:ns1="http://microsoft.com/exposed/object">\<ns1:comp_code>\</ns1:comp_code>\<ns1:comp_name>\</ns1:comp_name>\< /ns1:object_1>\</ns0:method_list>\</ns0:method_list_method></span></span>  
  
     <span data-ttu-id="92d68-110">この場合は、資格情報を提供する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="92d68-110">In this case you do not have to provide the credentials.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92d68-111">参照</span><span class="sxs-lookup"><span data-stu-id="92d68-111">See Also</span></span>  
 [<span data-ttu-id="92d68-112">アダプターをセキュリティで保護します。</span><span class="sxs-lookup"><span data-stu-id="92d68-112">Secure the adapter</span></span>](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)