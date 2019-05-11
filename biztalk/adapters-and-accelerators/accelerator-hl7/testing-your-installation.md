---
title: インストールのテスト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- testing installation
- installing, testing installation
ms.assetid: db27a75c-db7f-46ff-b8ef-2624ff18dcc8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3780ca8555efdac3d3c46e96080bb43d8226e339
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65286539"
---
# <a name="testing-your-installation"></a><span data-ttu-id="bde7a-102">インストールのテスト</span><span class="sxs-lookup"><span data-stu-id="bde7a-102">Testing Your Installation</span></span>
<span data-ttu-id="bde7a-103">設定することができます、[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]のエンド ツー エンド チュートリアルを手動で実行されているか、エンド ツー エンド チュートリアル プログラムを実行することによってテスト用インストールします。</span><span class="sxs-lookup"><span data-stu-id="bde7a-103">You can set up your [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] installation for testing either by manually running through the end-to-end tutorial or by executing the end-to-end tutorial program.</span></span> <span data-ttu-id="bde7a-104">プログラムを実行するをクリックするか、 **Launch Tutorial**セットアップ中にボタンまたは C:\Program files \microsoft biztalk EndToEndTutorial.exe を実行\<バージョン\>HL7\SDK\ のアクセラレータ(後のインストールと構成を実行している) エンド ツー エンド チュートリアル フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="bde7a-104">To exercise the program, either click the **Launch Tutorial** button during setup or execute EndToEndTutorial.exe in the C:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial folder (after running installation and configuration).</span></span> <span data-ttu-id="bde7a-105">これらの自動化されたアクションのいずれかは、チュートリアルを実行して手動で実行する同じセットアップ手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bde7a-105">Either of these automated actions will perform the same setup steps that you would manually perform by running through the tutorial.</span></span> <span data-ttu-id="bde7a-106">エンド ツー エンド チュートリアル プログラムは、次を行います。</span><span class="sxs-lookup"><span data-stu-id="bde7a-106">The end-to-end tutorial program does the following:</span></span>  
  
- <span data-ttu-id="bde7a-107">MSH と確認のスキーマをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="bde7a-107">Deploys MSH and ACK schemas</span></span>  
  
- <span data-ttu-id="bde7a-108">Version 2.3.1 の一般的なスキーマをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="bde7a-108">Deploys Version 2.3.1 common schemas</span></span>  
  
- <span data-ttu-id="bde7a-109">ADT スキーマをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="bde7a-109">Deploys ADT schemas</span></span>  
  
- <span data-ttu-id="bde7a-110">作成、Tutorial_1WayReceive 受信ポート</span><span class="sxs-lookup"><span data-stu-id="bde7a-110">Creates the Tutorial_1WayReceive receive port</span></span>  
  
- <span data-ttu-id="bde7a-111">作成、Tutorial_MLLPReceive 受信場所</span><span class="sxs-lookup"><span data-stu-id="bde7a-111">Creates the Tutorial_MLLPReceive receive location</span></span>  
  
- <span data-ttu-id="bde7a-112">作成、Tutorial_BTAHL7PickUp 受信ポート</span><span class="sxs-lookup"><span data-stu-id="bde7a-112">Creates the Tutorial_BTAHL7PickUp receive port</span></span>  
  
- <span data-ttu-id="bde7a-113">作成、Tutorial_FileReceiveLoc 受信場所</span><span class="sxs-lookup"><span data-stu-id="bde7a-113">Creates the Tutorial_FileReceiveLoc receive location</span></span>  
  
- <span data-ttu-id="bde7a-114">Tutorial_sendAck_ADT 送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="bde7a-114">Creates the Tutorial_sendAck_ADT send port</span></span>  
  
- <span data-ttu-id="bde7a-115">Tutorial_sendMsg_RX 送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="bde7a-115">Creates the Tutorial_sendMsg_RX send port</span></span>  
  
- <span data-ttu-id="bde7a-116">Tutorial_BTAHL7Drop 送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="bde7a-116">Creates the Tutorial_BTAHL7Drop send port</span></span>  
  
- <span data-ttu-id="bde7a-117">Tutorial_MLLPSend 送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="bde7a-117">Creates the Tutorial_MLLPSend send port</span></span>  
  
- <span data-ttu-id="bde7a-118">Tutorial_ADTSystem パーティを作成します。</span><span class="sxs-lookup"><span data-stu-id="bde7a-118">Creates the Tutorial_ADTSystem party</span></span>  
  
- <span data-ttu-id="bde7a-119">Tutorial_RXSystem パーティを作成します。</span><span class="sxs-lookup"><span data-stu-id="bde7a-119">Creates the Tutorial_RXSystem party</span></span>  
  
- <span data-ttu-id="bde7a-120">Tutorial_HISystem パーティを作成します。</span><span class="sxs-lookup"><span data-stu-id="bde7a-120">Creates the Tutorial_HISystem party</span></span>  
  
- <span data-ttu-id="bde7a-121">BizTalk サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="bde7a-121">Restarts the BizTalk Service</span></span>  
  
  <span data-ttu-id="bde7a-122">エンド ツー エンド チュートリアル プログラムを実行した場合は、HL7 定義済みフォルダーでのテスト インスタンスを削除できます。</span><span class="sxs-lookup"><span data-stu-id="bde7a-122">If you have executed the end-to-end tutorial program, you can drop a test instance for HL7 in a pre-defined folder.</span></span> <span data-ttu-id="bde7a-123">フォルダーに関連付けられている受信パイプラインはメッセージを取得し、それを処理します。</span><span class="sxs-lookup"><span data-stu-id="bde7a-123">The receive pipeline associated with the folder picks up the message and processes it.</span></span> <span data-ttu-id="bde7a-124">フィルターに基づき、送信パイプラインは、目的のフォルダーにドキュメントをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="bde7a-124">Based on filters, a send pipeline routes the document to the destination folder.</span></span> <span data-ttu-id="bde7a-125">Microsoft の基本的な構成要素を実行する単純な「ラウンド トリップ」がこの[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) エンジンし、インストールを確認します。</span><span class="sxs-lookup"><span data-stu-id="bde7a-125">This simple "round-trip" exercises the basic building blocks of the Microsoft [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) engine and confirms your installation.</span></span>  
  
### <a name="to-test-your-installation"></a><span data-ttu-id="bde7a-126">インストールをテストします。</span><span class="sxs-lookup"><span data-stu-id="bde7a-126">To test your installation</span></span>  
  
1. <span data-ttu-id="bde7a-127">使用して[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーで、参照、 \<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for HL7\SDK\End ツー エンド チュートリアル フォルダー。</span><span class="sxs-lookup"><span data-stu-id="bde7a-127">Using [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, browse to the \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial folder.</span></span>  
  
2. <span data-ttu-id="bde7a-128">右クリックし、 **TutorialSampleInstance.txt**ファイルを開き、をクリックし、**コピー**します。</span><span class="sxs-lookup"><span data-stu-id="bde7a-128">Right-click the **TutorialSampleInstance.txt** file, and then click **Copy**.</span></span>  
  
3. <span data-ttu-id="bde7a-129">使用して[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーで、参照、 \<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\End ツー エンド Tutorial\Tutorial_ のアクセラレータBTAHL7PickUp フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="bde7a-129">Using [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, browse to the \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_BTAHL7PickUp folder.</span></span>  
  
4. <span data-ttu-id="bde7a-130">フォルダーを右クリックし、**貼り付け**します。</span><span class="sxs-lookup"><span data-stu-id="bde7a-130">Right-click the folder, and then click **Paste**.</span></span>  
  
5. <span data-ttu-id="bde7a-131">使用して[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーで、参照、 \<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\End ツー エンド Tutorial\Tutorial_ のアクセラレータBTAHL7Drop フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="bde7a-131">Using [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, browse to the \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_BTAHL7Drop folder.</span></span>  
  
    <span data-ttu-id="bde7a-132">かどうか、インストールが正常に処理済みのインスタンスが表示される場合を確認することができます、 **Tutorial_BTAHL7Drop**フォルダーとして\< *Guid*\>.txt します。</span><span class="sxs-lookup"><span data-stu-id="bde7a-132">You can verify if your installation was successful if the processed instance appears in the **Tutorial_BTAHL7Drop** folder as \<*Guid*\>.txt.</span></span>  
  
   <span data-ttu-id="bde7a-133">次の手順に進む[チュートリアルを使用する準備](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-tutorial2.md)します。</span><span class="sxs-lookup"><span data-stu-id="bde7a-133">Proceed to the next step, [Preparing to Use the Tutorial](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-tutorial2.md).</span></span>