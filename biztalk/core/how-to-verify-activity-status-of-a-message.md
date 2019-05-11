---
title: メッセージのアクティビティの状態を確認する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- activities, verifying status
- PeopleSoft Integration Broker
- verifying message status in PeopleSoft
- messages, verifying status
ms.assetid: b8cee6f9-0f65-4228-a87a-3f3aca6182bf
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9267de92dcefc9decc5932bee6b531e300be029b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333102"
---
# <a name="how-to-verify-activity-status-of-a-message"></a><span data-ttu-id="8e1f2-102">メッセージのアクティビティの状態を確認する方法</span><span class="sxs-lookup"><span data-stu-id="8e1f2-102">How to Verify Activity Status of a Message</span></span>
<span data-ttu-id="8e1f2-103">PeopleSoft Integration Broker を使用して、PeopleSoft HTTP ホストおよび PeopleSoft がイベントを送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="8e1f2-103">You use the PeopleSoft Integration Broker to create a PeopleSoft HTTP Host and Port where PeopleSoft sends events.</span></span> <span data-ttu-id="8e1f2-104">次の手順に従ってが、アクティブで、ルーティングにメッセージを確認します。</span><span class="sxs-lookup"><span data-stu-id="8e1f2-104">You make sure that the message is active and routed by following these steps.</span></span>  
  
### <a name="to-verify-that-a-message-is-active-and-routed-correctly"></a><span data-ttu-id="8e1f2-105">メッセージがアクティブでルーティング正しくことを確認するには</span><span class="sxs-lookup"><span data-stu-id="8e1f2-105">To verify that a Message is active and routed correctly</span></span>  
  
1. <span data-ttu-id="8e1f2-106">をクリックして**開始**、 をポイント**プログラム**、 をポイント**PeopleSoft Application Name**、し、**アプリケーション デザイナー**します。</span><span class="sxs-lookup"><span data-stu-id="8e1f2-106">Click **Start**, point to **Programs**, point to **PeopleSoft Application Name**, and then select **Application Designer**.</span></span>  
  
2. <span data-ttu-id="8e1f2-107">**PeopleSoft sign-on**画面で、入力、**ユーザー ID**と**パスワード**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="8e1f2-107">On the **PeopleSoft Sign-on** screen, enter the **User ID** and **Password**, and then click **OK**.</span></span>  
  
    <span data-ttu-id="8e1f2-108">![](../core/media/psadapter-24-task-userpass.gif "PSAdapter_24_Task_UserPass")</span><span class="sxs-lookup"><span data-stu-id="8e1f2-108">![](../core/media/psadapter-24-task-userpass.gif "PSAdapter_24_Task_UserPass")</span></span>  
  
    <span data-ttu-id="8e1f2-109">![](../core/media/psadapter-25-task-emptydesigner.gif "PSAdapter_25_Task_EmptyDesigner")</span><span class="sxs-lookup"><span data-stu-id="8e1f2-109">![](../core/media/psadapter-25-task-emptydesigner.gif "PSAdapter_25_Task_EmptyDesigner")</span></span>  
  
3. <span data-ttu-id="8e1f2-110">アプリケーション デザイナーでの**ファイル**メニューで、**オープン**、し、**メッセージ**します。</span><span class="sxs-lookup"><span data-stu-id="8e1f2-110">In the Application Designer, on the **File** menu, point to **Open**, and then select **Message**.</span></span>  
  
    <span data-ttu-id="8e1f2-111">![](../core/media/psadapter-26-task-filemessage.gif "PSAdapter_26_Task_FileMessage")</span><span class="sxs-lookup"><span data-stu-id="8e1f2-111">![](../core/media/psadapter-26-task-filemessage.gif "PSAdapter_26_Task_FileMessage")</span></span>  
  
4. <span data-ttu-id="8e1f2-112">**定義を開く**画面で、**名**フィールドに、入力`LOCATION_SYNC`、順にクリックします**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="8e1f2-112">In the **Open Definition** screen, in the **Name** field, enter `LOCATION_SYNC`, and then click **Open**.</span></span>  
  
    <span data-ttu-id="8e1f2-113">![](../core/media/psadapter-27-task-locationsync.gif "PSAdapter_27_Task_LocationSync")</span><span class="sxs-lookup"><span data-stu-id="8e1f2-113">![](../core/media/psadapter-27-task-locationsync.gif "PSAdapter_27_Task_LocationSync")</span></span>  
  
5. <span data-ttu-id="8e1f2-114">**定義の選択条件に一致する**セクションで、ダブルクリックして、 **LOCATION_SYNC**プロパティを表示するメッセージ。</span><span class="sxs-lookup"><span data-stu-id="8e1f2-114">In the **Definitions matching selection criteria** section, double-click the **LOCATION_SYNC** message to view the properties.</span></span>  
  
    <span data-ttu-id="8e1f2-115">![](../core/media/psadapter-28-task-locationproperties.gif "PSAdapter_28_Task_LocationProperties")</span><span class="sxs-lookup"><span data-stu-id="8e1f2-115">![](../core/media/psadapter-28-task-locationproperties.gif "PSAdapter_28_Task_LocationProperties")</span></span>  
  
6. <span data-ttu-id="8e1f2-116">アプリケーション デザイナーで右クリックして **[location_tbl]**、選択と**メッセージ プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="8e1f2-116">In the Application Designer, right-click **LOCATION_TBL**, and select **Message Properties**.</span></span>  
  
    <span data-ttu-id="8e1f2-117">![](../core/media/psadapter-29-task-loctionmenu.gif "PSAdapter_29_Task_LoctionMenu")</span><span class="sxs-lookup"><span data-stu-id="8e1f2-117">![](../core/media/psadapter-29-task-loctionmenu.gif "PSAdapter_29_Task_LoctionMenu")</span></span>  
  
7. <span data-ttu-id="8e1f2-118">**メッセージ プロパティ**画面で、、**使用**タブ。</span><span class="sxs-lookup"><span data-stu-id="8e1f2-118">On the **Message Properties** screen, click the **Use** tab.</span></span>  
  
    <span data-ttu-id="8e1f2-119">クリックして、次のことを確認**OK**します。</span><span class="sxs-lookup"><span data-stu-id="8e1f2-119">Verify the following, and then click **OK**.</span></span>  
  
   1. <span data-ttu-id="8e1f2-120">**メッセージ：** Active</span><span class="sxs-lookup"><span data-stu-id="8e1f2-120">**Message:** Active</span></span>  
  
   2. <span data-ttu-id="8e1f2-121">**Message Channel:** ENTERPRISE_SETUP</span><span class="sxs-lookup"><span data-stu-id="8e1f2-121">**Message Channel:** ENTERPRISE_SETUP</span></span>  
  
   3. <span data-ttu-id="8e1f2-122">**既定のバージョン:** VERSION_1</span><span class="sxs-lookup"><span data-stu-id="8e1f2-122">**Default Version:** VERSION_1</span></span>  
  
      <span data-ttu-id="8e1f2-123">![](../core/media/psadapter-30-task-messageuse.gif "PSAdapter_30_Task_MessageUse")</span><span class="sxs-lookup"><span data-stu-id="8e1f2-123">![](../core/media/psadapter-30-task-messageuse.gif "PSAdapter_30_Task_MessageUse")</span></span>  
  
8. <span data-ttu-id="8e1f2-124">アプリケーション デザイナーを終了します。</span><span class="sxs-lookup"><span data-stu-id="8e1f2-124">Exit the Application Designer.</span></span>  
  
    <span data-ttu-id="8e1f2-125">こうことで、メッセージについて、アクティブな状態では、VERSION_1 が使用および PeopleSoft の ENTERPRISE_SETUP チャネル経由でことです。</span><span class="sxs-lookup"><span data-stu-id="8e1f2-125">This makes sure that the Message is in an active state, uses VERSION_1, and flows through the ENTERPRISE_SETUP channel in PeopleSoft.</span></span>  
  
9. <span data-ttu-id="8e1f2-126">PeopleSoft アプリケーションと通信するように Integration.Gateway.properties ファイルを構成します。</span><span class="sxs-lookup"><span data-stu-id="8e1f2-126">Configure the Integration.Gateway.properties file to communicate with the PeopleSoft application.</span></span>  
  
     <span data-ttu-id="8e1f2-127">次のプロパティを設定することを確認します。</span><span class="sxs-lookup"><span data-stu-id="8e1f2-127">Verify that the following properties are set:</span></span>  
  
    -   <span data-ttu-id="8e1f2-128">**ig.isc.serverurl:** //server:9000</span><span class="sxs-lookup"><span data-stu-id="8e1f2-128">**ig.isc.serverurl:** //server:9000</span></span>  
  
    -   <span data-ttu-id="8e1f2-129">**ig.isc.userid:** PS の ID</span><span class="sxs-lookup"><span data-stu-id="8e1f2-129">**ig.isc.userid:** ID for PS</span></span>  
  
    -   <span data-ttu-id="8e1f2-130">**ig.isc.password:** PS のパスワード</span><span class="sxs-lookup"><span data-stu-id="8e1f2-130">**ig.isc.password:** Password for PS</span></span>  
  
    -   <span data-ttu-id="8e1f2-131">**ig.isc.toolsrel::** 特定のリリース</span><span class="sxs-lookup"><span data-stu-id="8e1f2-131">**ig.isc.toolsrel:** Specific Release</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e1f2-132">参照</span><span class="sxs-lookup"><span data-stu-id="8e1f2-132">See Also</span></span>  
 [<span data-ttu-id="8e1f2-133">PeopleSoft の HTTP ホストとポートを作成する</span><span class="sxs-lookup"><span data-stu-id="8e1f2-133">Creating a PeopleSoft HTTP Host and Port</span></span>](../core/creating-a-peoplesoft-http-host-and-port.md)