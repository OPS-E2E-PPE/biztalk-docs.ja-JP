---
title: "手順 1: サービス バスの Namespace を作成する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ede1ac50-bbfb-4aeb-8217-1877ae218f89
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4d7630316f72fd63bac5ce7127b5451683e2f97
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-create-a-service-bus-namespace"></a><span data-ttu-id="69604-102">手順 1: サービス バスの Namespace を作成します。</span><span class="sxs-lookup"><span data-stu-id="69604-102">Step 1: Create a Service Bus Namespace</span></span>
<span data-ttu-id="69604-103">この手順で作成、 [!INCLUDE[winazure](../includes/winazure-md.md)] [!INCLUDE[sb](../includes/sb-md.md)]名前空間。</span><span class="sxs-lookup"><span data-stu-id="69604-103">In this step, you create a [!INCLUDE[winazure](../includes/winazure-md.md)][!INCLUDE[sb](../includes/sb-md.md)] namespace.</span></span> <span data-ttu-id="69604-104">この名前空間を使用して、Salesforce からの営業案件通知を受信するリレー エンドポイントをホストします。</span><span class="sxs-lookup"><span data-stu-id="69604-104">You will use this namespace to host a relay endpoint for receiving opportunity notifications from Salesforce.</span></span> <span data-ttu-id="69604-105">このソリューションを作成するプロセスの後半で、このリレー エンドポイントを使用して [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] システムで通知メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="69604-105">Later in the process of creating this solution, you will use this relay endpoint to receive the notification message into a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system.</span></span>  
  
### <a name="to-create-a-includesbincludessb-mdmd-namespace"></a><span data-ttu-id="69604-106">[!INCLUDE[sb](../includes/sb-md.md)] 名前空間を作成するには</span><span class="sxs-lookup"><span data-stu-id="69604-106">To create a [!INCLUDE[sb](../includes/sb-md.md)] namespace</span></span>  
  
1.  <span data-ttu-id="69604-107">ログオン[http://manage.windowsazure.com](http://manage.windowsazure.com) Microsoft アカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="69604-107">Log on to [http://manage.windowsazure.com](http://manage.windowsazure.com) using your Microsoft account.</span></span>  
  
2.  <span data-ttu-id="69604-108">ページの下部で、をクリックして**新規**、 **App Services**、 **Service Bus リレー**、し**簡易作成**です。</span><span class="sxs-lookup"><span data-stu-id="69604-108">At the bottom of the page, click **New**, **App Services**, **Service Bus Relay**, and then **Quick Create**.</span></span>  
  
3.  <span data-ttu-id="69604-109">名前空間を入力`BtsSalesforce`し、現在の地理的な場所に最も近い地域を選択します。</span><span class="sxs-lookup"><span data-stu-id="69604-109">Enter the namespace as `BtsSalesforce` and select a region closest to your current geographical location.</span></span> <span data-ttu-id="69604-110">をクリックして**リレーの作成**です。</span><span class="sxs-lookup"><span data-stu-id="69604-110">Click **Create a Relay**.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="69604-111">この名前空間はグローバルで一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="69604-111">This namespace must be globally unique.</span></span> <span data-ttu-id="69604-112">したがって、このチュートリアルで使用している以外の名前空間を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69604-112">So, you must use a namespace other than one mentioned in this tutorial.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="69604-113">この操作で作成されるのは名前空間だけであり、リレーは作成されませんのでご注意ください。</span><span class="sxs-lookup"><span data-stu-id="69604-113">Note that the relay is not created as part of the operation, only the namespace is.</span></span> <span data-ttu-id="69604-114">受信場所を構成するとき、このチュートリアルで後ほど、リレー エンドポイントが作成された、 **Sb-messaging**アダプター。</span><span class="sxs-lookup"><span data-stu-id="69604-114">The relay endpoint is created later in this tutorial when we configure a receive location for the **SB-Messaging** adapter.</span></span>  
  
4.  <span data-ttu-id="69604-115">状態が に設定されている名前空間の作成後、 **Active**です。</span><span class="sxs-lookup"><span data-stu-id="69604-115">After the namespace is created, the status is set to **Active**.</span></span> <span data-ttu-id="69604-116">名前空間を選択し、をクリックできますステータスがアクティブ、**アクセス キー**に接続する方法の詳細を取得するには、ページの下部にある、 **BtsSalesforce** の値を含む、名前空間**既定のユーザー**と**既定のキー**です。</span><span class="sxs-lookup"><span data-stu-id="69604-116">Once the status is active, you can select the namespace and click **Access Key** at the bottom of the page to get details on how to connect to the **BtsSalesforce** namespace, including the values for **Default User** and **Default Key**.</span></span> <span data-ttu-id="69604-117">これらの詳細は、チュートリアルの後半で必要になります。</span><span class="sxs-lookup"><span data-stu-id="69604-117">You will need these details later in the tutorial.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69604-118">参照</span><span class="sxs-lookup"><span data-stu-id="69604-118">See Also</span></span>  
 [<span data-ttu-id="69604-119">チュートリアル 6: Salesforce との BizTalk Server 2013 の統合</span><span class="sxs-lookup"><span data-stu-id="69604-119">Tutorial 6: Integrating BizTalk Server 2013 with Salesforce</span></span>](Tutorial:%20Integrating%20BizTalk%20Server%202013%20with%20Salesforce.md)