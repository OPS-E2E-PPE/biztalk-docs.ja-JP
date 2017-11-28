---
title: "メッセージのアクティビティの状態を確認する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- activities, verifying status
- PeopleSoft Integration Broker
- verifying message status in PeopleSoft
- messages, verifying status
ms.assetid: b8cee6f9-0f65-4228-a87a-3f3aca6182bf
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 872c1a1fcfcc905caf926c8299f56d49178a8448
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-verify-activity-status-of-a-message"></a><span data-ttu-id="b9d69-102">メッセージのアクティビティの状態を確認する方法</span><span class="sxs-lookup"><span data-stu-id="b9d69-102">How to Verify Activity Status of a Message</span></span>
<span data-ttu-id="b9d69-103">PeopleSoft HTTP ホストおよび PeopleSoft がイベントを送信ポートを作成するのにには、PeopleSoft Integration Broker を使用します。</span><span class="sxs-lookup"><span data-stu-id="b9d69-103">You use the PeopleSoft Integration Broker to create a PeopleSoft HTTP Host and Port where PeopleSoft sends events.</span></span> <span data-ttu-id="b9d69-104">メッセージがアクティブになっており、ルーティングされていることを確認するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="b9d69-104">You make sure that the message is active and routed by following these steps.</span></span>  
  
### <a name="to-verify-that-a-message-is-active-and-routed-correctly"></a><span data-ttu-id="b9d69-105">メッセージがアクティブで正しくルーティングされていることを確認するには</span><span class="sxs-lookup"><span data-stu-id="b9d69-105">To verify that a Message is active and routed correctly</span></span>  
  
1.  <span data-ttu-id="b9d69-106">をクリックして**開始**、 をポイント**プログラム**、 をポイント**PeopleSoft Application Name**、し、**アプリケーション デザイナー**です。</span><span class="sxs-lookup"><span data-stu-id="b9d69-106">Click **Start**, point to **Programs**, point to **PeopleSoft Application Name**, and then select **Application Designer**.</span></span>  
  
2.  <span data-ttu-id="b9d69-107">**PeopleSoft sign-on**画面で、入力、**ユーザー ID**と**パスワード**、クリックして**[ok]**です。</span><span class="sxs-lookup"><span data-stu-id="b9d69-107">On the **PeopleSoft Sign-on** screen, enter the **User ID** and **Password**, and then click **OK**.</span></span>  
  
     ![](../core/media/psadapter-24-task-userpass.gif "PSAdapter_24_Task_UserPass")  
  
     ![](../core/media/psadapter-25-task-emptydesigner.gif "PSAdapter_25_Task_EmptyDesigner")  
  
3.  <span data-ttu-id="b9d69-108">アプリケーション デザイナーでの**ファイル**] メニューのをポイント**開く**、し、[**メッセージ**です。</span><span class="sxs-lookup"><span data-stu-id="b9d69-108">In the Application Designer, on the **File** menu, point to **Open**, and then select **Message**.</span></span>  
  
     ![](../core/media/psadapter-26-task-filemessage.gif "PSAdapter_26_Task_FileMessage")  
  
4.  <span data-ttu-id="b9d69-109">**定義を開く**画面で、**名前**フィールドに「 `LOCATION_SYNC`、順にクリック**開く**です。</span><span class="sxs-lookup"><span data-stu-id="b9d69-109">In the **Open Definition** screen, in the **Name** field, enter `LOCATION_SYNC`, and then click **Open**.</span></span>  
  
     ![](../core/media/psadapter-27-task-locationsync.gif "PSAdapter_27_Task_LocationSync")  
  
5.  <span data-ttu-id="b9d69-110">**選択条件に一致する定義**セクションをダブルクリックして、 **LOCATION_SYNC**プロパティを表示するメッセージ。</span><span class="sxs-lookup"><span data-stu-id="b9d69-110">In the **Definitions matching selection criteria** section, double-click the **LOCATION_SYNC** message to view the properties.</span></span>  
  
     ![](../core/media/psadapter-28-task-locationproperties.gif "PSAdapter_28_Task_LocationProperties")  
  
6.  <span data-ttu-id="b9d69-111">アプリケーション デザイナーを右クリックして**[location_tbl]**を選択して**メッセージ プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="b9d69-111">In the Application Designer, right-click **LOCATION_TBL**, and select **Message Properties**.</span></span>  
  
     ![](../core/media/psadapter-29-task-loctionmenu.gif "PSAdapter_29_Task_LoctionMenu")  
  
7.  <span data-ttu-id="b9d69-112">**メッセージ プロパティ**画面で、をクリックして、**使用**タブです。</span><span class="sxs-lookup"><span data-stu-id="b9d69-112">On the **Message Properties** screen, click the **Use** tab.</span></span>  
  
     <span data-ttu-id="b9d69-113">次のようにを確認し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="b9d69-113">Verify the following, and then click **OK**.</span></span>  
  
    1.  <span data-ttu-id="b9d69-114">**メッセージ:** Active</span><span class="sxs-lookup"><span data-stu-id="b9d69-114">**Message:** Active</span></span>  
  
    2.  <span data-ttu-id="b9d69-115">**Message Channel:** ENTERPRISE_SETUP</span><span class="sxs-lookup"><span data-stu-id="b9d69-115">**Message Channel:** ENTERPRISE_SETUP</span></span>  
  
    3.  <span data-ttu-id="b9d69-116">**既定のバージョン:** VERSION_1</span><span class="sxs-lookup"><span data-stu-id="b9d69-116">**Default Version:** VERSION_1</span></span>  
  
     ![](../core/media/psadapter-30-task-messageuse.gif "PSAdapter_30_Task_MessageUse")  
  
8.  <span data-ttu-id="b9d69-117">アプリケーション デザイナーを終了します。</span><span class="sxs-lookup"><span data-stu-id="b9d69-117">Exit the Application Designer.</span></span>  
  
     <span data-ttu-id="b9d69-118">これにより、メッセージの状態がアクティブであること、VERSION_1 が使用されていること、および PeopleSoft の ENTERPRISE_SETUP チャネルにルーティングされていることが確認されました。</span><span class="sxs-lookup"><span data-stu-id="b9d69-118">This makes sure that the Message is in an active state, uses VERSION_1, and flows through the ENTERPRISE_SETUP channel in PeopleSoft.</span></span>  
  
9. <span data-ttu-id="b9d69-119">PeopleSoft アプリケーションと通信するように Integration.Gateway.properties ファイルを構成します。</span><span class="sxs-lookup"><span data-stu-id="b9d69-119">Configure the Integration.Gateway.properties file to communicate with the PeopleSoft application.</span></span>  
  
     <span data-ttu-id="b9d69-120">プロパティが次のように設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b9d69-120">Verify that the following properties are set:</span></span>  
  
    -   <span data-ttu-id="b9d69-121">**ig.isc.serverurl:** //server:9000</span><span class="sxs-lookup"><span data-stu-id="b9d69-121">**ig.isc.serverurl:** //server:9000</span></span>  
  
    -   <span data-ttu-id="b9d69-122">**ig.isc.userid::** PS の ID</span><span class="sxs-lookup"><span data-stu-id="b9d69-122">**ig.isc.userid:** ID for PS</span></span>  
  
    -   <span data-ttu-id="b9d69-123">**ig.isc.password::** PS のパスワード</span><span class="sxs-lookup"><span data-stu-id="b9d69-123">**ig.isc.password:** Password for PS</span></span>  
  
    -   <span data-ttu-id="b9d69-124">**ig.isc.toolsrel::**特定のリリース</span><span class="sxs-lookup"><span data-stu-id="b9d69-124">**ig.isc.toolsrel:** Specific Release</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9d69-125">参照</span><span class="sxs-lookup"><span data-stu-id="b9d69-125">See Also</span></span>  
 [<span data-ttu-id="b9d69-126">PeopleSoft HTTP ホストおよびポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="b9d69-126">Creating a PeopleSoft HTTP Host and Port</span></span>](../core/creating-a-peoplesoft-http-host-and-port.md)