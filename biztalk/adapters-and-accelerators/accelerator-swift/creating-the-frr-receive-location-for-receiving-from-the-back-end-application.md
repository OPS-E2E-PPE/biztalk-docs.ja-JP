---
title: バックエンド アプリケーションから受信するための受信場所の作成、FRR |Microsoft ドキュメント
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
ms.openlocfilehash: 46895ff64e6585c8b80979c09874dffb510cf049
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210082"
---
# <a name="creating-the-frr-receive-location-for-receiving-from-the-back-end-application"></a><span data-ttu-id="a5b96-102">バックエンド アプリケーションから受信するための受信場所の FRR を作成します。</span><span class="sxs-lookup"><span data-stu-id="a5b96-102">Creating the FRR Receive Location for Receiving from the Back-End Application</span></span>
<span data-ttu-id="a5b96-103">FIN 対応調整を実行するバックエンド アプリケーションからメッセージを受信する受信場所を作成する必要があります。[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="a5b96-103">To perform FIN Response Reconciliation, you need to create a receive location that receives a message from the back-end application into [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span></span>  
  
 <span data-ttu-id="a5b96-104">**概要**</span><span class="sxs-lookup"><span data-stu-id="a5b96-104">**Summary**</span></span>  
  
 <span data-ttu-id="a5b96-105">次のプロパティおよびコンポーネントで受信場所を作成します。</span><span class="sxs-lookup"><span data-stu-id="a5b96-105">Create a receive location with the following properties and components:</span></span>  
  
|<span data-ttu-id="a5b96-106">プロパティ/コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a5b96-106">Property/Component</span></span>|<span data-ttu-id="a5b96-107">設定</span><span class="sxs-lookup"><span data-stu-id="a5b96-107">Setting</span></span>|  
|-------------------------|-------------|  
|<span data-ttu-id="a5b96-108">受信ポート</span><span class="sxs-lookup"><span data-stu-id="a5b96-108">Receive port</span></span>|<span data-ttu-id="a5b96-109">一方向のポート</span><span class="sxs-lookup"><span data-stu-id="a5b96-109">One-way port</span></span>|  
|<span data-ttu-id="a5b96-110">トランスポートの種類</span><span class="sxs-lookup"><span data-stu-id="a5b96-110">Transport type</span></span>|<span data-ttu-id="a5b96-111">バックエンド アプリケーションで使用されるトランスポートの種類</span><span class="sxs-lookup"><span data-stu-id="a5b96-111">The transport type used by the back-end application</span></span>|  
|<span data-ttu-id="a5b96-112">アドレスの URI</span><span class="sxs-lookup"><span data-stu-id="a5b96-112">Address URI</span></span>|<span data-ttu-id="a5b96-113">必要に応じて、トランスポートの種類</span><span class="sxs-lookup"><span data-stu-id="a5b96-113">As required for the transport type</span></span>|  
|<span data-ttu-id="a5b96-114">[受信ハンドラー]</span><span class="sxs-lookup"><span data-stu-id="a5b96-114">Receive handler</span></span>|<span data-ttu-id="a5b96-115">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="a5b96-115">BizTalkServerApplication</span></span>|  
|<span data-ttu-id="a5b96-116">受信パイプライン。</span><span class="sxs-lookup"><span data-stu-id="a5b96-116">Receive pipeline</span></span>|<span data-ttu-id="a5b96-117">[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]受信 FRR 用に作成したパイプライン</span><span class="sxs-lookup"><span data-stu-id="a5b96-117">The [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] receive pipeline that you created for FRR</span></span>|  
  
### <a name="to-add-an-frr-receive-location-for-receiving-from-the-back-end-application"></a><span data-ttu-id="a5b96-118">バックエンド アプリケーションから、FRR 受信受信するための場所を追加</span><span class="sxs-lookup"><span data-stu-id="a5b96-118">To add an FRR receive location for receiving from the back-end application</span></span>  
  
1.  <span data-ttu-id="a5b96-119">BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、 **BizTalk グループ**、**アプリケーション**、および**BizTalk アプリケーション1**ノード。</span><span class="sxs-lookup"><span data-stu-id="a5b96-119">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, **BizTalk Group**, **Applications**, and **BizTalk Application 1** nodes.</span></span>  
  
2.  <span data-ttu-id="a5b96-120">右クリック**パイプライン**、クリックして**更新**です。</span><span class="sxs-lookup"><span data-stu-id="a5b96-120">Right-click **Pipelines**, and then click **Refresh**.</span></span>  
  
3.  <span data-ttu-id="a5b96-121">右クリック**受信ポート**、 をポイント**新規**、クリックして**一方向の受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="a5b96-121">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
4.  <span data-ttu-id="a5b96-122">受信ポートのプロパティ ダイアログ ボックスで、**名前**ボックス FRRBackEndReceivePort など、受信ポートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="a5b96-122">In the Receive Port Properties dialog box, in the **Name** box, type a name for the receive port, such as FRRBackEndReceivePort.</span></span>  
  
5.  <span data-ttu-id="a5b96-123">をクリックして**適用**をクリックして、ポートのバインド**OK**です。</span><span class="sxs-lookup"><span data-stu-id="a5b96-123">Click **Apply** to bind the port, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="a5b96-124">管理コンソールで、右クリック**受信場所**、 をポイント**新規**、クリックして**一方向の受信場所**です。</span><span class="sxs-lookup"><span data-stu-id="a5b96-124">In the Administration Console, right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location**.</span></span>  
  
7.  <span data-ttu-id="a5b96-125">受信ポート ダイアログ ボックスの 選択した受信ポートを作成し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="a5b96-125">In the Select a Receive Port dialog box, select the receive port that you just created, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="a5b96-126">受信場所のプロパティ ダイアログ ボックスで、**名前**ボックスで、受信場所の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="a5b96-126">In the Receive Location Properties dialog box, in the **Name** box, type a name for the receive location.</span></span>  
  
9. <span data-ttu-id="a5b96-127">**トランスポート** セクションの**型**テキスト ボックスで、バックエンド アプリケーションで使用されるトランスポートの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5b96-127">In the **Transport** section, for the **Type** text box, select the transport type used by the back-end application.</span></span>  
  
10. <span data-ttu-id="a5b96-128">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="a5b96-128">Click **Configure**.</span></span>  
  
11. <span data-ttu-id="a5b96-129">ファイル トランスポートのプロパティ ダイアログ ボックスで、トランスポートの種類に必要なプロパティを入力し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="a5b96-129">In the FILE Transport Properties dialog box, fill in the properties required for the transport type, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="a5b96-130">受信場所のプロパティ] ダイアログ ボックスの**受信ハンドラー**[ **BizTalkServerApplication**です。</span><span class="sxs-lookup"><span data-stu-id="a5b96-130">In the Receive Location Properties dialog box, for **Receive Handler**, select **BizTalkServerApplication**.</span></span>  
  
13. <span data-ttu-id="a5b96-131">受信場所のプロパティ ダイアログ ボックスの**受信パイプライン**を選択、 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] FRR 用に作成したパイプラインを受信します。</span><span class="sxs-lookup"><span data-stu-id="a5b96-131">In the Receive Location Properties dialog box, for **Receive Pipeline**, select the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] receive pipeline that you created for FRR.</span></span>  
  
14. <span data-ttu-id="a5b96-132">をクリックして**適用**、順にクリック**OK**を閉じる、**受信場所のプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="a5b96-132">Click **Apply**, and then click **OK** to close the **Receive Location Properties** dialog box.</span></span>  
  
15. <span data-ttu-id="a5b96-133">BizTalk エクスプローラを右クリックした受信場所を作成し、をクリックして**を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="a5b96-133">In BizTalk Explorer, right-click the receive location that you just created, and then click **Enable**.</span></span>