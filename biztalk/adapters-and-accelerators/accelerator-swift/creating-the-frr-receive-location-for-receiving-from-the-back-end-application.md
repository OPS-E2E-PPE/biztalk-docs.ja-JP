---
title: バックエンド アプリケーションから受信するための受信場所の作成、FRR |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive locations, creating
- creating, receive locations
- FRR, creating receive locations
ms.assetid: 78bd8084-ddec-4066-a474-ab5b1a0a849f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26ac72c9d122b626411e67cfc6e18f76de226415
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002859"
---
# <a name="creating-the-frr-receive-location-for-receiving-from-the-back-end-application"></a><span data-ttu-id="0cdf8-102">バックエンド アプリケーションから受信するための受信場所の FRR を作成します。</span><span class="sxs-lookup"><span data-stu-id="0cdf8-102">Creating the FRR Receive Location for Receiving from the Back-End Application</span></span>
<span data-ttu-id="0cdf8-103">FIN Response Reconciliation を実行するバック エンド アプリケーションからメッセージを受信する受信場所を作成する必要があります。[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="0cdf8-103">To perform FIN Response Reconciliation, you need to create a receive location that receives a message from the back-end application into [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span></span>  

 <span data-ttu-id="0cdf8-104">**概要**</span><span class="sxs-lookup"><span data-stu-id="0cdf8-104">**Summary**</span></span>  

 <span data-ttu-id="0cdf8-105">次のプロパティおよびコンポーネントで受信場所を作成します。</span><span class="sxs-lookup"><span data-stu-id="0cdf8-105">Create a receive location with the following properties and components:</span></span>  


| <span data-ttu-id="0cdf8-106">プロパティ/コンポーネント</span><span class="sxs-lookup"><span data-stu-id="0cdf8-106">Property/Component</span></span> |                                                                 <span data-ttu-id="0cdf8-107">設定</span><span class="sxs-lookup"><span data-stu-id="0cdf8-107">Setting</span></span>                                                                 |
|--------------------|-----------------------------------------------------------------------------------------------------------------------------------------|
|    <span data-ttu-id="0cdf8-108">受信ポート</span><span class="sxs-lookup"><span data-stu-id="0cdf8-108">Receive port</span></span>    |                                                              <span data-ttu-id="0cdf8-109">一方向のポート</span><span class="sxs-lookup"><span data-stu-id="0cdf8-109">One-way port</span></span>                                                               |
|   <span data-ttu-id="0cdf8-110">トランスポートの種類</span><span class="sxs-lookup"><span data-stu-id="0cdf8-110">Transport type</span></span>   |                                           <span data-ttu-id="0cdf8-111">バックエンド アプリケーションで使用されるトランスポートの種類</span><span class="sxs-lookup"><span data-stu-id="0cdf8-111">The transport type used by the back-end application</span></span>                                           |
|    <span data-ttu-id="0cdf8-112">アドレスの URI</span><span class="sxs-lookup"><span data-stu-id="0cdf8-112">Address URI</span></span>     |                                                   <span data-ttu-id="0cdf8-113">トランスポートの種類の必要に応じて</span><span class="sxs-lookup"><span data-stu-id="0cdf8-113">As required for the transport type</span></span>                                                    |
|  <span data-ttu-id="0cdf8-114">[受信ハンドラー]</span><span class="sxs-lookup"><span data-stu-id="0cdf8-114">Receive handler</span></span>   |                                                        <span data-ttu-id="0cdf8-115">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="0cdf8-115">BizTalkServerApplication</span></span>                                                         |
|  <span data-ttu-id="0cdf8-116">受信パイプライン。</span><span class="sxs-lookup"><span data-stu-id="0cdf8-116">Receive pipeline</span></span>  | <span data-ttu-id="0cdf8-117">[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] FRR 用に作成したパイプラインの受信</span><span class="sxs-lookup"><span data-stu-id="0cdf8-117">The [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] receive pipeline that you created for FRR</span></span> |

### <a name="to-add-an-frr-receive-location-for-receiving-from-the-back-end-application"></a><span data-ttu-id="0cdf8-118">バックエンド アプリケーションから、FRR 受信場所の受信を追加</span><span class="sxs-lookup"><span data-stu-id="0cdf8-118">To add an FRR receive location for receiving from the back-end application</span></span>  

1. <span data-ttu-id="0cdf8-119">BizTalk Server 管理コンソールで  **BizTalk Server 管理**、 **BizTalk グループ**、**アプリケーション**、および**BizTalk アプリケーション1**ノード。</span><span class="sxs-lookup"><span data-stu-id="0cdf8-119">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, **BizTalk Group**, **Applications**, and **BizTalk Application 1** nodes.</span></span>  

2. <span data-ttu-id="0cdf8-120">右クリック**パイプライン**、 をクリックし、**更新**します。</span><span class="sxs-lookup"><span data-stu-id="0cdf8-120">Right-click **Pipelines**, and then click **Refresh**.</span></span>  

3. <span data-ttu-id="0cdf8-121">右クリック**受信ポート**、 をポイント**新規**、 をクリックし、**一方向の受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="0cdf8-121">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  

4. <span data-ttu-id="0cdf8-122">受信ポートのプロパティ ダイアログ ボックスでの**名前**ボックスに、FRRBackEndReceivePort など、受信ポートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="0cdf8-122">In the Receive Port Properties dialog box, in the **Name** box, type a name for the receive port, such as FRRBackEndReceivePort.</span></span>  

5. <span data-ttu-id="0cdf8-123">をクリックして**適用**をクリックして、ポートのバインド**OK**します。</span><span class="sxs-lookup"><span data-stu-id="0cdf8-123">Click **Apply** to bind the port, and then click **OK**.</span></span>  

6. <span data-ttu-id="0cdf8-124">管理コンソールで、右クリック**受信場所**、 をポイント**新規**、 をクリックし、**一方向の受信場所**します。</span><span class="sxs-lookup"><span data-stu-id="0cdf8-124">In the Administration Console, right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location**.</span></span>  

7. <span data-ttu-id="0cdf8-125">受信ポートのダイアログ ボックスの 選択した受信ポートを作成し、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="0cdf8-125">In the Select a Receive Port dialog box, select the receive port that you just created, and then click **OK**.</span></span>  

8. <span data-ttu-id="0cdf8-126">受信場所のプロパティ ダイアログ ボックスでの**名前**ボックスに、受信場所の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="0cdf8-126">In the Receive Location Properties dialog box, in the **Name** box, type a name for the receive location.</span></span>  

9. <span data-ttu-id="0cdf8-127">**トランスポート**セクションの**型**テキスト ボックスで、バックエンド アプリケーションで使用されるトランスポートの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="0cdf8-127">In the **Transport** section, for the **Type** text box, select the transport type used by the back-end application.</span></span>  

10. <span data-ttu-id="0cdf8-128">クリックして**構成**します。</span><span class="sxs-lookup"><span data-stu-id="0cdf8-128">Click **Configure**.</span></span>  

11. <span data-ttu-id="0cdf8-129">クリックして、FILE トランスポートのプロパティ ダイアログ ボックスで、トランスポートの種類に必要なプロパティを入力**OK**します。</span><span class="sxs-lookup"><span data-stu-id="0cdf8-129">In the FILE Transport Properties dialog box, fill in the properties required for the transport type, and then click **OK**.</span></span>  

12. <span data-ttu-id="0cdf8-130">受信場所のプロパティ ダイアログ ボックスでの**受信ハンドラー**、 **BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="0cdf8-130">In the Receive Location Properties dialog box, for **Receive Handler**, select **BizTalkServerApplication**.</span></span>  

13. <span data-ttu-id="0cdf8-131">受信場所のプロパティ ダイアログ ボックスでの**受信パイプライン**を選択、 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] FRR 用に作成したパイプラインを受信します。</span><span class="sxs-lookup"><span data-stu-id="0cdf8-131">In the Receive Location Properties dialog box, for **Receive Pipeline**, select the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] receive pipeline that you created for FRR.</span></span>  

14. <span data-ttu-id="0cdf8-132">をクリックして**適用**、順にクリックします**OK**を閉じる、**受信場所のプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="0cdf8-132">Click **Apply**, and then click **OK** to close the **Receive Location Properties** dialog box.</span></span>  

15. <span data-ttu-id="0cdf8-133">BizTalk エクスプ ローラーで右クリックした受信場所を作成し、**を有効にする**します。</span><span class="sxs-lookup"><span data-stu-id="0cdf8-133">In BizTalk Explorer, right-click the receive location that you just created, and then click **Enable**.</span></span>
