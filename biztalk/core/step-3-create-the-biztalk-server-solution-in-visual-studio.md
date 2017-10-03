---
title: "手順 3: Visual Studio での BizTalk Server ソリューションの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a4da3333-e430-4caf-bc29-44a60ebac385
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 402434ec74327b55f243fecd9d1c347ce4ff0390
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-create-the-biztalk-server-solution-in-visual-studio"></a><span data-ttu-id="09ba8-102">手順 3: Visual Studio での BizTalk Server ソリューションを作成します。</span><span class="sxs-lookup"><span data-stu-id="09ba8-102">Step 3: Create the BizTalk Server Solution in Visual Studio</span></span>
<span data-ttu-id="09ba8-103">このセクションでは、Salesforce からの営業案件通知を受信、Salesforce への営業案件に関する追加情報を問い合わせ、またその情報を社内の SQL Server データベースへの追加を可能にする [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ソリューションの作成について見ていきます。</span><span class="sxs-lookup"><span data-stu-id="09ba8-103">In this section, we look at creating the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solution for receiving opportunity notifications from Salesforce, querying Salesforce to get additional information about the opportunity, and finally inserting that information into an on-premise SQL Server database.</span></span> <span data-ttu-id="09ba8-104">このセクションは、さらにステップごとのカテゴリに分けられています。</span><span class="sxs-lookup"><span data-stu-id="09ba8-104">This section is further categorized according to each of these broader steps.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="09ba8-105">Salesforce へのメッセージの送信や、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で Salesforce からのメッセージを受信を可能にするには、ソリューションにいくつかのカスタム コンポーネントを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="09ba8-105">To be able to send messages to Salesforce and to receive messages from Salesforce into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], we need to include some custom components into our solution.</span></span> <span data-ttu-id="09ba8-106">これらのカスタム コンポーネントを作成[ステップ 3 d: を有効にする BizTalk Server 送信し、Salesforce からのメッセージを受信する](../core/step-3d-enabling-biztalk-server-to-send-and-receive-messages-from-salesforce.md)です。</span><span class="sxs-lookup"><span data-stu-id="09ba8-106">We create those custom components in [Step 3d: Enabling BizTalk Server to Send and Receive Messages from Salesforce](../core/step-3d-enabling-biztalk-server-to-send-and-receive-messages-from-salesforce.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="09ba8-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="09ba8-107">In This Section</span></span>  
  
-   [<span data-ttu-id="09ba8-108">手順 3: BizTalk Server に Salesforce の営業案件通知を受信</span><span class="sxs-lookup"><span data-stu-id="09ba8-108">Step 3a: Receive Salesforce Opportunity Notification into BizTalk Server</span></span>](../core/step-3a-receive-salesforce-opportunity-notification-into-biztalk-server.md)  
  
-   [<span data-ttu-id="09ba8-109">手順 3 b: Wcf-webhttp アダプターを使用して Salesforce から営業案件の詳細を取得</span><span class="sxs-lookup"><span data-stu-id="09ba8-109">Step 3b: Retrieve Opportunity Details from Salesforce using the WCF-WebHttp Adapter</span></span>](../core/step-3b-retrieve-opportunities-from-salesforce-using-the-wcf-webhttp-adapter.md)  
  
-   [<span data-ttu-id="09ba8-110">手順 3 c: SQL Server データベースに営業案件の詳細を挿入</span><span class="sxs-lookup"><span data-stu-id="09ba8-110">Step 3c: Insert Opportunity Details into a SQL Server Database</span></span>](../core/step-3c-insert-opportunity-details-into-a-sql-server-database.md)  
  
-   [<span data-ttu-id="09ba8-111">BizTalk Server で Salesforce からのメッセージの送受信を有効にする手順 3 d:</span><span class="sxs-lookup"><span data-stu-id="09ba8-111">Step 3d: Enabling BizTalk Server to Send and Receive Messages from Salesforce</span></span>](../core/step-3d-enabling-biztalk-server-to-send-and-receive-messages-from-salesforce.md)  
  
-   [<span data-ttu-id="09ba8-112">ステップ 3 e: ビルドし、BizTalk Server ソリューションの配置</span><span class="sxs-lookup"><span data-stu-id="09ba8-112">Step 3e: Build and Deploy the BizTalk Server Solution</span></span>](../core/step-3e-build-and-deploy-the-biztalk-server-solution.md)  
  
## <a name="see-also"></a><span data-ttu-id="09ba8-113">参照</span><span class="sxs-lookup"><span data-stu-id="09ba8-113">See Also</span></span>  
 [<span data-ttu-id="09ba8-114">チュートリアル 6: Salesforce との BizTalk Server 2013 の統合</span><span class="sxs-lookup"><span data-stu-id="09ba8-114">Tutorial 6: Integrating BizTalk Server 2013 with Salesforce</span></span>](Tutorial:%20Integrating%20BizTalk%20Server%202013%20with%20Salesforce.md)