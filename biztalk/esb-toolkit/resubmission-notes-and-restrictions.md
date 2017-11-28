---
title: "再送信の注意事項と制約事項 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 391064a9-1d61-4b10-97ab-d93b37d1ae23
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62313528ce406347b1a7f11abf9aa3db1dd5f8e6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="resubmission-notes-and-restrictions"></a><span data-ttu-id="810e4-102">再送信の注意事項と制約事項</span><span class="sxs-lookup"><span data-stu-id="810e4-102">Resubmission Notes and Restrictions</span></span>
<span data-ttu-id="810e4-103">再送信プロセスには、次の注意事項と制約事項が適用されます。</span><span class="sxs-lookup"><span data-stu-id="810e4-103">The following notes and restrictions apply to the resubmission process:</span></span>  
  
-   <span data-ttu-id="810e4-104">ESB WCF 入り口、SOAP (ASMX) 上のランプ、XML メッセージを再送信できますか、任意の HTTP 受信場所。</span><span class="sxs-lookup"><span data-stu-id="810e4-104">You can resubmit XML messages to the ESB WCF on-ramp, SOAP (ASMX) on-ramp, or any HTTP receive location.</span></span>  
  
-   <span data-ttu-id="810e4-105">WCF の上のランプの既定の URL は、http://localhost/ESB.ItineraryServices.WCF/ProcessItinerary.svc です。</span><span class="sxs-lookup"><span data-stu-id="810e4-105">The default URL for the WCF on-ramp is http://localhost/ESB.ItineraryServices.WCF/ProcessItinerary.svc.</span></span>  
  
-   <span data-ttu-id="810e4-106">ポータルの Web.config ファイルは、WCF 入り口内のエンドポイントの詳細を定義、 **\<クライアント >**のノード、  **\<System.ServiceModel >**セクションです。</span><span class="sxs-lookup"><span data-stu-id="810e4-106">The portal Web.config file defines the endpoint details for the WCF on-ramp in the **\<Client>** node of the **\<System.ServiceModel>** section.</span></span> <span data-ttu-id="810e4-107">既定値を次に示します。</span><span class="sxs-lookup"><span data-stu-id="810e4-107">The following is the default value.</span></span>  
  
    ```  
    <endpoint  
      address="http://localhost/ESB.ItineraryServices.WCF/ProcessItinerary.svc"  
      binding="wsHttpBinding"  
      bindingConfiguration="WSHttpBinding_ITwoWayAsyncVoid"  
      contract="ProcessRequest"   
      name="WSHttpBinding_ITwoWayAsyncVoid">                  
    </endpoint>  
    ```  
  
-   <span data-ttu-id="810e4-108">リモート サーバー上のランプで WCF が存在する場合、正しいサーバーをポイントするアドレスを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="810e4-108">If the WCF on-ramp resides on a remote server, you must update the address to point to the correct server.</span></span>  
  
-   <span data-ttu-id="810e4-109">ランプで SOAP (ASMX) の既定の URL は、http://localhost/ESB.ItineraryServices/ProcessItinerary.asmx です。</span><span class="sxs-lookup"><span data-stu-id="810e4-109">The default URL for the SOAP (ASMX) on-ramp is http://localhost/ESB.ItineraryServices/ProcessItinerary.asmx.</span></span>  
  
-   <span data-ttu-id="810e4-110">ポータルの Web.config ファイルでランプでに SOAP (ASMX) の構成を定義する、  **\<applicationSettings >**セクションです。</span><span class="sxs-lookup"><span data-stu-id="810e4-110">The portal Web.config file defines the configuration for the SOAP (ASMX) on-ramp in the **\<applicationSettings>** section.</span></span> <span data-ttu-id="810e4-111">既定値を次に示します。</span><span class="sxs-lookup"><span data-stu-id="810e4-111">The following is the default value.</span></span>  
  
    ```  
    <setting   
      name="Microsoft_Practices_ESB_Portal_ProcessItinerary_Process"  
      serializeAs="String">  
      <value>  
        http://localhost/ESB.ItineraryServices/ProcessItinerary.asmx  
      </value>  
    </setting>  
    ```  
  
-   <span data-ttu-id="810e4-112">ASMX 入り口がリモート サーバー上にある場合は、適切なサーバー アドレスを持つ URL を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="810e4-112">If the ASMX on-ramp resides on a remote server, you need to update the URL with the correct server address.</span></span>  
  
-   <span data-ttu-id="810e4-113">フラット ファイルを再送信することができます、HTTP のみに書式設定されたメッセージの受信場所。</span><span class="sxs-lookup"><span data-stu-id="810e4-113">You can resubmit flat file formatted messages only to an HTTP receive location.</span></span> <span data-ttu-id="810e4-114">WCF または SOAP 入り口に送信することはできません。</span><span class="sxs-lookup"><span data-stu-id="810e4-114">You cannot submit them to a WCF or SOAP on-ramp.</span></span> <span data-ttu-id="810e4-115">確認する必要がありますを消費したり、フラット ファイルを解析する適切なパイプライン、HTTP 受信場所であることができます。</span><span class="sxs-lookup"><span data-stu-id="810e4-115">You must ensure that the HTTP receive location has the appropriate pipeline that can consume and/or parse the flat file.</span></span>  
  
-   <span data-ttu-id="810e4-116">再送信されたメッセージは、元のメッセージのコンテキスト プロパティのいずれか。</span><span class="sxs-lookup"><span data-stu-id="810e4-116">The resubmitted message does not contain any of the context properties of the original message.</span></span>  
  
-   <span data-ttu-id="810e4-117">再送信がメッセージ本文のみに適用されます。メッセージ全体には適用されません。</span><span class="sxs-lookup"><span data-stu-id="810e4-117">Resubmission applies to only the message body; it does not apply to the entire message.</span></span>  
  
-   <span data-ttu-id="810e4-118">再送信プロセスでは、1 部構成のメッセージのみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="810e4-118">The resubmission process supports only single-part messages.</span></span> <span data-ttu-id="810e4-119">マルチパート メッセージを再送信プロセスを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="810e4-119">You cannot use the resubmission process with multi-part messages.</span></span>  
  
-   <span data-ttu-id="810e4-120">バイナリ形式のメッセージを再送信することはできません。</span><span class="sxs-lookup"><span data-stu-id="810e4-120">You cannot resubmit binary-formatted messages.</span></span>