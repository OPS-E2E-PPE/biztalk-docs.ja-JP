---
title: "手順 7: サンプル LOB メッセージの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, LOB
- loopback tutorial, creating LOB message
- creating, LOB messages
- LOBs, creating messages
ms.assetid: 3023bbc0-5bc4-4e5a-a345-c3253874f0d3
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: acc6b57a78d51d9c132115f387296c48c2e924c9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-7-create-a-sample-lob-message"></a><span data-ttu-id="b2dc1-102">手順 7: サンプル LOB メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="b2dc1-102">Step 7: Create a Sample LOB Message</span></span>
<span data-ttu-id="b2dc1-103">ここでは、LOB アプリケーション ユーティリティを使用して、サンプルの基幹業務 (LOB) メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="b2dc1-103">In this step, you use the LOB Application utility to create a sample line-of-business (LOB) message.</span></span>  
  
### <a name="to-create-a-sample-message-using-the-lob-application-utility"></a><span data-ttu-id="b2dc1-104">LOB アプリケーション ユーティリティを使用してサンプル メッセージを作成するには</span><span class="sxs-lookup"><span data-stu-id="b2dc1-104">To create a sample message using the LOB Application utility</span></span>  
  
1.  <span data-ttu-id="b2dc1-105">[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーに移動\<*ドライブ*>: \Program Files\Microsoft BizTalk\<バージョン > Accelerator for rosettanet \sdk フォルダーをダブルクリック**LOBApplication.exe**です。</span><span class="sxs-lookup"><span data-stu-id="b2dc1-105">In [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, move to \<*drive*>:\Program Files\Microsoft BizTalk \<version> Accelerator for RosettaNet\SDK folder, and then double-click **LOBApplication.exe**.</span></span>  
  
2.  <span data-ttu-id="b2dc1-106">**LOB Application**  ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="b2dc1-106">In the **LOB Application** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="b2dc1-107">**これを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="b2dc1-107">**Use this**</span></span>|<span data-ttu-id="b2dc1-108">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="b2dc1-108">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="b2dc1-109">**Home Profile Name**</span><span class="sxs-lookup"><span data-stu-id="b2dc1-109">**Home Profile Name**</span></span>|<span data-ttu-id="b2dc1-110">型**ホーム**です。</span><span class="sxs-lookup"><span data-stu-id="b2dc1-110">Type **HOME**.</span></span>|  
    |<span data-ttu-id="b2dc1-111">**取引先名**</span><span class="sxs-lookup"><span data-stu-id="b2dc1-111">**Trading Partner Name**</span></span>|<span data-ttu-id="b2dc1-112">型**パートナー**です。</span><span class="sxs-lookup"><span data-stu-id="b2dc1-112">Type **PARTNER**.</span></span>|  
    |<span data-ttu-id="b2dc1-113">**PIP の名前**</span><span class="sxs-lookup"><span data-stu-id="b2dc1-113">**PIP Name**</span></span>|<span data-ttu-id="b2dc1-114">型**0c1**です。</span><span class="sxs-lookup"><span data-stu-id="b2dc1-114">Type **0C1**.</span></span>|  
    |<span data-ttu-id="b2dc1-115">**[PIP Version]**</span><span class="sxs-lookup"><span data-stu-id="b2dc1-115">**PIP Version**</span></span>|<span data-ttu-id="b2dc1-116">型**R01.02**です。</span><span class="sxs-lookup"><span data-stu-id="b2dc1-116">Type **R01.02**.</span></span>|  
    |<span data-ttu-id="b2dc1-117">**[ファイル名]**</span><span class="sxs-lookup"><span data-stu-id="b2dc1-117">**File Name**</span></span>|<span data-ttu-id="b2dc1-118">省略記号ボタン (**.**) に移動する\<*ドライブ*: > \Program Files\Microsoft BizTalk\<バージョン > Accelerator for rosettanet \sdk\lobapplication\sampleinstances です。</span><span class="sxs-lookup"><span data-stu-id="b2dc1-118">Click the ellipsis button (**...**), and move to \<*drive*:>\Program Files\Microsoft BizTalk \<version> Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances.</span></span> <span data-ttu-id="b2dc1-119">選択**[0c1 request.xml]**クリックして、ファイルの一覧から**開く**です。</span><span class="sxs-lookup"><span data-stu-id="b2dc1-119">Select **0C1_Request.xml** from the list of files, and then click **Open**.</span></span>|  
    |<span data-ttu-id="b2dc1-120">**メッセージのカテゴリ**</span><span class="sxs-lookup"><span data-stu-id="b2dc1-120">**Message Category**</span></span>|<span data-ttu-id="b2dc1-121">選択**アクション**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="b2dc1-121">Select **Action** from the drop-down list.</span></span>|  
  
3.  <span data-ttu-id="b2dc1-122">**LOB Application**ダイアログ ボックスで、をクリックして**Submit Message**です。</span><span class="sxs-lookup"><span data-stu-id="b2dc1-122">In the **LOB Application** dialog box, click **Submit Message**.</span></span>  
  
 <span data-ttu-id="b2dc1-123">LOB アプリケーションは、LOB アプリケーションが生成した元のメッセージをシミュレートして Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] のメッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="b2dc1-123">The LOB application generates a message for Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] simulating an original message generated by an LOB application.</span></span> <span data-ttu-id="b2dc1-124">メッセージの状態は [Status] ウィンドウで確認できます。</span><span class="sxs-lookup"><span data-stu-id="b2dc1-124">You can view the status of the message in the Status window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b2dc1-125">サンプル メッセージでは、"HOME" と "PARTNER" のグローバル ビジネス識別子 (GBI) は、それぞれ 123456789 と 987654321 です。</span><span class="sxs-lookup"><span data-stu-id="b2dc1-125">The sample messages assume that the Global Business Identifiers (GBI) for "HOME" and "PARTNER" are 123456789 and 987654321, respectively.</span></span> <span data-ttu-id="b2dc1-126">別の GBI を使用する場合は、これらのファイルの内容を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2dc1-126">To use a different GBI, you must modify the content of these files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2dc1-127">参照</span><span class="sxs-lookup"><span data-stu-id="b2dc1-127">See Also</span></span>  
 [<span data-ttu-id="b2dc1-128">手順 8: BTARN データベース内のメッセージの表示</span><span class="sxs-lookup"><span data-stu-id="b2dc1-128">Step 8: View Messages in the BTARN Databases</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-8-view-messages-in-the-btarn-databases.md)