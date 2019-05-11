---
title: 手順 1:Service Bus の Namespace を作成する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ede1ac50-bbfb-4aeb-8217-1877ae218f89
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d8986f729d48fd25066bd166749d6bfb2b7ed3c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392829"
---
# <a name="step-1-create-a-service-bus-namespace"></a><span data-ttu-id="87dee-102">手順 1:Service Bus の Namespace を作成します。</span><span class="sxs-lookup"><span data-stu-id="87dee-102">Step 1: Create a Service Bus Namespace</span></span>
<span data-ttu-id="87dee-103">この手順で作成、 [!INCLUDE[winazure](../includes/winazure-md.md)] [!INCLUDE[sb](../includes/sb-md.md)]名前空間。</span><span class="sxs-lookup"><span data-stu-id="87dee-103">In this step, you create a [!INCLUDE[winazure](../includes/winazure-md.md)][!INCLUDE[sb](../includes/sb-md.md)] namespace.</span></span> <span data-ttu-id="87dee-104">この名前空間を使用して、Salesforce から営業案件通知を受信するためのリレー エンドポイントがホストされます。</span><span class="sxs-lookup"><span data-stu-id="87dee-104">You will use this namespace to host a relay endpoint for receiving opportunity notifications from Salesforce.</span></span> <span data-ttu-id="87dee-105">後でこのソリューションを作成するには、処理中に使用するこのリレー エンドポイントに通知メッセージが表示される、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]システム。</span><span class="sxs-lookup"><span data-stu-id="87dee-105">Later in the process of creating this solution, you will use this relay endpoint to receive the notification message into a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system.</span></span>  
  
### <a name="to-create-a-includesbincludessb-mdmd-namespace"></a><span data-ttu-id="87dee-106">作成する、[!INCLUDE[sb](../includes/sb-md.md)]名前空間</span><span class="sxs-lookup"><span data-stu-id="87dee-106">To create a [!INCLUDE[sb](../includes/sb-md.md)] namespace</span></span>  
  
1.  <span data-ttu-id="87dee-107">ログオン[ http://manage.windowsazure.com ](http://manage.windowsazure.com) Microsoft アカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="87dee-107">Log on to [http://manage.windowsazure.com](http://manage.windowsazure.com) using your Microsoft account.</span></span>  
  
2.  <span data-ttu-id="87dee-108">ページの下部には、次のようにクリックします。**新規**、 **App Services**、 **Service Bus Relay**、し**簡易作成**です。</span><span class="sxs-lookup"><span data-stu-id="87dee-108">At the bottom of the page, click **New**, **App Services**, **Service Bus Relay**, and then **Quick Create**.</span></span>  
  
3.  <span data-ttu-id="87dee-109">名前空間を入力します。 `BtsSalesforce` 、現在の所在地に最も近いリージョンを選択します。</span><span class="sxs-lookup"><span data-stu-id="87dee-109">Enter the namespace as `BtsSalesforce` and select a region closest to your current geographical location.</span></span> <span data-ttu-id="87dee-110">クリックして**リレーの作成**です。</span><span class="sxs-lookup"><span data-stu-id="87dee-110">Click **Create a Relay**.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="87dee-111">この名前空間はグローバルに一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="87dee-111">This namespace must be globally unique.</span></span> <span data-ttu-id="87dee-112">そのため、このチュートリアルで説明されている 1 つ以外の名前空間を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="87dee-112">So, you must use a namespace other than one mentioned in this tutorial.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="87dee-113">リレーは、操作の一部として作成されません、名前空間はことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="87dee-113">Note that the relay is not created as part of the operation, only the namespace is.</span></span> <span data-ttu-id="87dee-114">受信場所を構成するときに、このチュートリアルの後半でリレー エンドポイントを作成、 **Sb-messaging**アダプター。</span><span class="sxs-lookup"><span data-stu-id="87dee-114">The relay endpoint is created later in this tutorial when we configure a receive location for the **SB-Messaging** adapter.</span></span>  
  
4.  <span data-ttu-id="87dee-115">設定されて、名前空間が作成されると、 **Active**します。</span><span class="sxs-lookup"><span data-stu-id="87dee-115">After the namespace is created, the status is set to **Active**.</span></span> <span data-ttu-id="87dee-116">状態がアクティブにするとは、名前空間を選択およびクリックして**アクセス キー**に接続する方法の詳細を取得するには、ページの下部にある、 **BtsSalesforce** の値を含む、名前空間**既定のユーザー**と**既定のキー**します。</span><span class="sxs-lookup"><span data-stu-id="87dee-116">Once the status is active, you can select the namespace and click **Access Key** at the bottom of the page to get details on how to connect to the **BtsSalesforce** namespace, including the values for **Default User** and **Default Key**.</span></span> <span data-ttu-id="87dee-117">これらの詳細は、このチュートリアルで後ほど必要があります。</span><span class="sxs-lookup"><span data-stu-id="87dee-117">You will need these details later in the tutorial.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87dee-118">参照</span><span class="sxs-lookup"><span data-stu-id="87dee-118">See Also</span></span>  
 [<span data-ttu-id="87dee-119">チュートリアル 6:BizTalk Server 2013 を Salesforce と統合します。</span><span class="sxs-lookup"><span data-stu-id="87dee-119">Tutorial 6: Integrating BizTalk Server 2013 with Salesforce</span></span>](Tutorial:%20Integrating%20BizTalk%20Server%202013%20with%20Salesforce.md)