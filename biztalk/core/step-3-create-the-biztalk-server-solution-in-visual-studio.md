---
title: 手順 3:Visual Studio で BizTalk Server ソリューションの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a4da3333-e430-4caf-bc29-44a60ebac385
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35f5c2b16aa29613a3709b9b5ece6ae3bd815229
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392651"
---
# <a name="step-3-create-the-biztalk-server-solution-in-visual-studio"></a><span data-ttu-id="0fe1d-102">手順 3:Visual Studio で BizTalk Server ソリューションを作成します。</span><span class="sxs-lookup"><span data-stu-id="0fe1d-102">Step 3: Create the BizTalk Server Solution in Visual Studio</span></span>
<span data-ttu-id="0fe1d-103">このセクションで作成するのに注目、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Salesforce から営業案件通知の受信、Salesforce の営業案件に関する追加情報を取得するクエリを実行およびオンプレミス SQL にその情報を最後に挿入するためのソリューションサーバーのデータベースです。</span><span class="sxs-lookup"><span data-stu-id="0fe1d-103">In this section, we look at creating the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solution for receiving opportunity notifications from Salesforce, querying Salesforce to get additional information about the opportunity, and finally inserting that information into an on-premise SQL Server database.</span></span> <span data-ttu-id="0fe1d-104">このセクションでは、それぞれの広範な手順に従ってさらに分類されます。</span><span class="sxs-lookup"><span data-stu-id="0fe1d-104">This section is further categorized according to each of these broader steps.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0fe1d-105">Salesforce にメッセージを送信し、Salesforce からメッセージを受信できる[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、当社のソリューションにいくつかのカスタム コンポーネントを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fe1d-105">To be able to send messages to Salesforce and to receive messages from Salesforce into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], we need to include some custom components into our solution.</span></span> <span data-ttu-id="0fe1d-106">これらのカスタム コンポーネントを作成します[手順 3 d:Salesforce からのメッセージを送受信する BizTalk Server を有効にする](../core/step-3d-enabling-biztalk-server-to-send-and-receive-messages-from-salesforce.md)します。</span><span class="sxs-lookup"><span data-stu-id="0fe1d-106">We create those custom components in [Step 3d: Enabling BizTalk Server to Send and Receive Messages from Salesforce](../core/step-3d-enabling-biztalk-server-to-send-and-receive-messages-from-salesforce.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0fe1d-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="0fe1d-107">In This Section</span></span>  
  
-   [<span data-ttu-id="0fe1d-108">手順 3 a:BizTalk Server に Salesforce の営業案件通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="0fe1d-108">Step 3a: Receive Salesforce Opportunity Notification into BizTalk Server</span></span>](../core/step-3a-receive-salesforce-opportunity-notification-into-biztalk-server.md)  
  
-   [<span data-ttu-id="0fe1d-109">手順 3 b:Wcf-webhttp アダプターを使用して Salesforce から営業案件の詳細を取得します。</span><span class="sxs-lookup"><span data-stu-id="0fe1d-109">Step 3b: Retrieve Opportunity Details from Salesforce using the WCF-WebHttp Adapter</span></span>](../core/step-3b-retrieve-opportunities-from-salesforce-using-the-wcf-webhttp-adapter.md)  
  
-   [<span data-ttu-id="0fe1d-110">手順 3 c:SQL Server データベースに営業案件の詳細を挿入します。</span><span class="sxs-lookup"><span data-stu-id="0fe1d-110">Step 3c: Insert Opportunity Details into a SQL Server Database</span></span>](../core/step-3c-insert-opportunity-details-into-a-sql-server-database.md)  
  
-   [<span data-ttu-id="0fe1d-111">手順 3 d:Salesforce からのメッセージを送受信する BizTalk Server の有効化</span><span class="sxs-lookup"><span data-stu-id="0fe1d-111">Step 3d: Enabling BizTalk Server to Send and Receive Messages from Salesforce</span></span>](../core/step-3d-enabling-biztalk-server-to-send-and-receive-messages-from-salesforce.md)  
  
-   [<span data-ttu-id="0fe1d-112">手順 3 e:BizTalk Server ソリューション ビルドしてデプロイ</span><span class="sxs-lookup"><span data-stu-id="0fe1d-112">Step 3e: Build and Deploy the BizTalk Server Solution</span></span>](../core/step-3e-build-and-deploy-the-biztalk-server-solution.md)  
  
## <a name="see-also"></a><span data-ttu-id="0fe1d-113">参照</span><span class="sxs-lookup"><span data-stu-id="0fe1d-113">See Also</span></span>  
 [<span data-ttu-id="0fe1d-114">チュートリアル 6:BizTalk Server 2013 を Salesforce と統合します。</span><span class="sxs-lookup"><span data-stu-id="0fe1d-114">Tutorial 6: Integrating BizTalk Server 2013 with Salesforce</span></span>](Tutorial:%20Integrating%20BizTalk%20Server%202013%20with%20Salesforce.md)