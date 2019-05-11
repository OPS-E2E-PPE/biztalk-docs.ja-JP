---
title: 手順 7:サンプル LOB メッセージの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, LOB
- loopback tutorial, creating LOB message
- creating, LOB messages
- LOBs, creating messages
ms.assetid: 3023bbc0-5bc4-4e5a-a345-c3253874f0d3
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c39df356056e8f8f5f9bcf7d136eda302003096e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280617"
---
# <a name="step-7-create-a-sample-lob-message"></a><span data-ttu-id="c4b99-102">手順 7:サンプル LOB メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="c4b99-102">Step 7: Create a Sample LOB Message</span></span>
<span data-ttu-id="c4b99-103">この手順では、LOB アプリケーション ユーティリティを使用するサンプルの基幹業務 (LOB) メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="c4b99-103">In this step, you use the LOB Application utility to create a sample line-of-business (LOB) message.</span></span>  

### <a name="to-create-a-sample-message-using-the-lob-application-utility"></a><span data-ttu-id="c4b99-104">LOB アプリケーション ユーティリティを使用してサンプル メッセージを作成するには</span><span class="sxs-lookup"><span data-stu-id="c4b99-104">To create a sample message using the LOB Application utility</span></span>  

1. <span data-ttu-id="c4b99-105">[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーに移動\<*ドライブ*\>: \Program Files (x86) \Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk フォルダーをダブルクリックします**LOBApplication.exe**します。</span><span class="sxs-lookup"><span data-stu-id="c4b99-105">In [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, move to \<*drive*\>:\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK folder, and then double-click **LOBApplication.exe**.</span></span>  

2. <span data-ttu-id="c4b99-106">**LOB アプリケーション** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c4b99-106">In the **LOB Application** dialog box, do the following:</span></span>  


   |       <span data-ttu-id="c4b99-107">**これを使用して、**</span><span class="sxs-lookup"><span data-stu-id="c4b99-107">**Use this**</span></span>       |                                                                                                                       <span data-ttu-id="c4b99-108">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="c4b99-108">**To do this**</span></span>                                                                                                                       |
   |--------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |  <span data-ttu-id="c4b99-109">**Home Profile Name**</span><span class="sxs-lookup"><span data-stu-id="c4b99-109">**Home Profile Name**</span></span>   |                                                                                                                       <span data-ttu-id="c4b99-110">型**ホーム**します。</span><span class="sxs-lookup"><span data-stu-id="c4b99-110">Type **HOME**.</span></span>                                                                                                                       |
   | <span data-ttu-id="c4b99-111">**取引先名**</span><span class="sxs-lookup"><span data-stu-id="c4b99-111">**Trading Partner Name**</span></span> |                                                                                                                     <span data-ttu-id="c4b99-112">型**パートナー**します。</span><span class="sxs-lookup"><span data-stu-id="c4b99-112">Type **PARTNER**.</span></span>                                                                                                                      |
   |       <span data-ttu-id="c4b99-113">**PIP の名前**</span><span class="sxs-lookup"><span data-stu-id="c4b99-113">**PIP Name**</span></span>       |                                                                                                                       <span data-ttu-id="c4b99-114">型**0c1**します。</span><span class="sxs-lookup"><span data-stu-id="c4b99-114">Type **0C1**.</span></span>                                                                                                                        |
   |     <span data-ttu-id="c4b99-115">**[PIP Version]**</span><span class="sxs-lookup"><span data-stu-id="c4b99-115">**PIP Version**</span></span>      |                                                                                                                      <span data-ttu-id="c4b99-116">型**R01.02**します。</span><span class="sxs-lookup"><span data-stu-id="c4b99-116">Type **R01.02**.</span></span>                                                                                                                      |
   |      <span data-ttu-id="c4b99-117">**[ファイル名]**</span><span class="sxs-lookup"><span data-stu-id="c4b99-117">**File Name**</span></span>       | <span data-ttu-id="c4b99-118">省略記号ボタンをクリックします (**.**) に移動し、 \<*ドライブ*:\>\Program Files (x86) \Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\lobapplication\sampleinstances.</span><span class="sxs-lookup"><span data-stu-id="c4b99-118">Click the ellipsis button (**...**), and move to \<*drive*:\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances.</span></span> <span data-ttu-id="c4b99-119">選択 **[0c1 request.xml]** クリックして、ファイルの一覧から**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="c4b99-119">Select **0C1_Request.xml** from the list of files, and then click **Open**.</span></span> |
   |   <span data-ttu-id="c4b99-120">**メッセージのカテゴリ**</span><span class="sxs-lookup"><span data-stu-id="c4b99-120">**Message Category**</span></span>   |                                                                                                         <span data-ttu-id="c4b99-121">選択**アクション**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="c4b99-121">Select **Action** from the drop-down list.</span></span>                                                                                                         |


3. <span data-ttu-id="c4b99-122">**LOB アプリケーション**ダイアログ ボックスで、をクリックして**Submit Message**します。</span><span class="sxs-lookup"><span data-stu-id="c4b99-122">In the **LOB Application** dialog box, click **Submit Message**.</span></span>  

   <span data-ttu-id="c4b99-123">Microsoft LOB アプリケーションがメッセージを生成[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]LOB アプリケーションによって生成された元のメッセージをシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="c4b99-123">The LOB application generates a message for Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] simulating an original message generated by an LOB application.</span></span> <span data-ttu-id="c4b99-124">ステータス ウィンドウには、メッセージの状態を表示できます。</span><span class="sxs-lookup"><span data-stu-id="c4b99-124">You can view the status of the message in the Status window.</span></span>  

> [!NOTE]
>  <span data-ttu-id="c4b99-125">サンプル メッセージでは、"HOME"のグローバル ビジネス識別子 (GBI) と「パートナー」が 123456789 と 987654321、それぞれを前提としています。</span><span class="sxs-lookup"><span data-stu-id="c4b99-125">The sample messages assume that the Global Business Identifiers (GBI) for "HOME" and "PARTNER" are 123456789 and 987654321, respectively.</span></span> <span data-ttu-id="c4b99-126">別の GBI を使用するには、これらのファイルの内容を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4b99-126">To use a different GBI, you must modify the content of these files.</span></span>  

## <a name="see-also"></a><span data-ttu-id="c4b99-127">参照</span><span class="sxs-lookup"><span data-stu-id="c4b99-127">See Also</span></span>  
 [<span data-ttu-id="c4b99-128">手順 8:BTARN データベース内のメッセージの表示</span><span class="sxs-lookup"><span data-stu-id="c4b99-128">Step 8: View Messages in the BTARN Databases</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-8-view-messages-in-the-btarn-databases.md)
