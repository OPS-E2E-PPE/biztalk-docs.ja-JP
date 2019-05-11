---
title: 再送信の注意事項と制約事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 391064a9-1d61-4b10-97ab-d93b37d1ae23
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f08f6a2740331518d6fc92fb0c12e6f89d1b79f0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401504"
---
# <a name="resubmission-notes-and-restrictions"></a><span data-ttu-id="ab6c6-102">再送信の注意事項と制約事項</span><span class="sxs-lookup"><span data-stu-id="ab6c6-102">Resubmission Notes and Restrictions</span></span>
<span data-ttu-id="ab6c6-103">再送信プロセスには、次の注意事項と制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="ab6c6-103">The following notes and restrictions apply to the resubmission process:</span></span>  
  
-   <span data-ttu-id="ab6c6-104">ESB WCF ランプで、SOAP (ASMX) 上のランプ、XML メッセージを再送信できますか、任意の HTTP 受信場所。</span><span class="sxs-lookup"><span data-stu-id="ab6c6-104">You can resubmit XML messages to the ESB WCF on-ramp, SOAP (ASMX) on-ramp, or any HTTP receive location.</span></span>  
  
-   <span data-ttu-id="ab6c6-105">ランプで WCF の既定の URL は http://localhost/ESB.ItineraryServices.WCF/ProcessItinerary.svcします。</span><span class="sxs-lookup"><span data-stu-id="ab6c6-105">The default URL for the WCF on-ramp is http://localhost/ESB.ItineraryServices.WCF/ProcessItinerary.svc.</span></span>  
  
-   <span data-ttu-id="ab6c6-106">ポータルの Web.config ファイルでランプでに WCF のエンドポイントの詳細を定義する、 **\<クライアント\>** のノード、 **\<System.ServiceModel\>** セクション。</span><span class="sxs-lookup"><span data-stu-id="ab6c6-106">The portal Web.config file defines the endpoint details for the WCF on-ramp in the **\<Client\>** node of the **\<System.ServiceModel\>** section.</span></span> <span data-ttu-id="ab6c6-107">既定値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ab6c6-107">The following is the default value.</span></span>  
  
    ```  
    <endpoint  
      address="http://localhost/ESB.ItineraryServices.WCF/ProcessItinerary.svc"  
      binding="wsHttpBinding"  
      bindingConfiguration="WSHttpBinding_ITwoWayAsyncVoid"  
      contract="ProcessRequest"   
      name="WSHttpBinding_ITwoWayAsyncVoid">                  
    </endpoint>  
    ```  
  
-   <span data-ttu-id="ab6c6-108">リモート サーバー上のランプで WCF が存在する場合は、正しいサーバーをポイントするアドレスを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab6c6-108">If the WCF on-ramp resides on a remote server, you must update the address to point to the correct server.</span></span>  
  
-   <span data-ttu-id="ab6c6-109">ランプで SOAP (ASMX) の既定の URL は http://localhost/ESB.ItineraryServices/ProcessItinerary.asmxします。</span><span class="sxs-lookup"><span data-stu-id="ab6c6-109">The default URL for the SOAP (ASMX) on-ramp is http://localhost/ESB.ItineraryServices/ProcessItinerary.asmx.</span></span>  
  
-   <span data-ttu-id="ab6c6-110">ポータルの Web.config ファイルでランプでに SOAP (ASMX) の構成を定義する、 **\<applicationSettings\>** セクション。</span><span class="sxs-lookup"><span data-stu-id="ab6c6-110">The portal Web.config file defines the configuration for the SOAP (ASMX) on-ramp in the **\<applicationSettings\>** section.</span></span> <span data-ttu-id="ab6c6-111">既定値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ab6c6-111">The following is the default value.</span></span>  
  
    ```  
    <setting   
      name="Microsoft_Practices_ESB_Portal_ProcessItinerary_Process"  
      serializeAs="String">  
      <value>  
        http://localhost/ESB.ItineraryServices/ProcessItinerary.asmx  
      </value>  
    </setting>  
    ```  
  
-   <span data-ttu-id="ab6c6-112">ASMX の上のランプがリモート サーバー上にある場合は、適切なサーバー アドレスの URL を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab6c6-112">If the ASMX on-ramp resides on a remote server, you need to update the URL with the correct server address.</span></span>  
  
-   <span data-ttu-id="ab6c6-113">フラット ファイルを再送信することができますのみ HTTP を書式設定されたメッセージの受信場所。</span><span class="sxs-lookup"><span data-stu-id="ab6c6-113">You can resubmit flat file formatted messages only to an HTTP receive location.</span></span> <span data-ttu-id="ab6c6-114">WCF または SOAP に着手するには、それらを送信できません。</span><span class="sxs-lookup"><span data-stu-id="ab6c6-114">You cannot submit them to a WCF or SOAP on-ramp.</span></span> <span data-ttu-id="ab6c6-115">確認する必要があります消費やフラット ファイルを解析できますを適切なパイプラインには、HTTP 受信場所であること。</span><span class="sxs-lookup"><span data-stu-id="ab6c6-115">You must ensure that the HTTP receive location has the appropriate pipeline that can consume and/or parse the flat file.</span></span>  
  
-   <span data-ttu-id="ab6c6-116">再送信されたメッセージは、元のメッセージのコンテキスト プロパティのいずれかありません。</span><span class="sxs-lookup"><span data-stu-id="ab6c6-116">The resubmitted message does not contain any of the context properties of the original message.</span></span>  
  
-   <span data-ttu-id="ab6c6-117">再送信がメッセージ本文のみに適用されます。メッセージ全体には適用されません。</span><span class="sxs-lookup"><span data-stu-id="ab6c6-117">Resubmission applies to only the message body; it does not apply to the entire message.</span></span>  
  
-   <span data-ttu-id="ab6c6-118">再送信プロセスでは、1 つの部分のメッセージのみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="ab6c6-118">The resubmission process supports only single-part messages.</span></span> <span data-ttu-id="ab6c6-119">マルチパート メッセージを再送信プロセスを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="ab6c6-119">You cannot use the resubmission process with multi-part messages.</span></span>  
  
-   <span data-ttu-id="ab6c6-120">バイナリ形式のメッセージを再送信することはできません。</span><span class="sxs-lookup"><span data-stu-id="ab6c6-120">You cannot resubmit binary-formatted messages.</span></span>