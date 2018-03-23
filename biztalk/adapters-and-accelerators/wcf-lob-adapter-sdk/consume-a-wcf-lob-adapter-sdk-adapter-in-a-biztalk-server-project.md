---
title: BizTalk Server プロジェクト内の WCF LOB Adapter SDK アダプターを使用する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 041f14cc-d00f-450d-b1e9-40a3e423c510
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84f81d23b56c2631879f366e6fe502840408a0d7
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2018
---
# <a name="consume-a-wcf-lob-adapter-sdk-adapter-in-a-biztalk-server-project"></a><span data-ttu-id="3dc0e-102">BizTalk Server プロジェクト内の WCF LOB Adapter SDK アダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="3dc0e-102">Consume a WCF LOB Adapter SDK adapter in a BizTalk Server project</span></span>
<span data-ttu-id="3dc0e-103">このトピックを使用して構築されたアダプターを使用する方法について説明、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]から[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を使用して、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3dc0e-103">This topic describes how to consume an adapter built using the [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] from [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3dc0e-104">使用するために、 [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、インストールする必要があります、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] 、同じホスト コンピューターでツール[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3dc0e-104">In order to use the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], you must install the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] tools on the same computer hosting [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 
## <a name="use-the-consume-adapter-service-add-in"></a><span data-ttu-id="3dc0e-105">使用して、アダプターを使用する追加のサービス</span><span class="sxs-lookup"><span data-stu-id="3dc0e-105">Use the Consume Adapter Service Add-in</span></span>  
 
  
1.  <span data-ttu-id="3dc0e-106">.NET アプリケーションを開く[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3dc0e-106">Open your .NET application in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="3dc0e-107">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]で、**プロジェクト** ウィンドウを右クリックし、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プロジェクトをクリックして**追加**&#124;**生成された項目の追加**&#124;です。**アダプター サービスの使用**です。</span><span class="sxs-lookup"><span data-stu-id="3dc0e-107">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], in the **Project** pane, right-click your [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] project, and then choose **Add**&#124;**Add Generated Items** &#124; **Consume Adapter Service**.</span></span>  
  
3.  <span data-ttu-id="3dc0e-108">[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]画面で、アダプターのバインドを選択します。</span><span class="sxs-lookup"><span data-stu-id="3dc0e-108">In the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] screen, select an adapter binding.</span></span>  
  
4.  <span data-ttu-id="3dc0e-109">をクリックして**構成**接続 URI、選択したアダプターのバインドを構成して、任意の資格情報、URI のプロパティ、およびバインドのプロパティを提供します。</span><span class="sxs-lookup"><span data-stu-id="3dc0e-109">Click **Configure** to configure the connection URI for the selected adapter binding and to provide any credentials, URI properties, and binding properties.</span></span> <span data-ttu-id="3dc0e-110">実際の要件は、選択したアダプターのバインドによって異なります。</span><span class="sxs-lookup"><span data-stu-id="3dc0e-110">Actual requirements will vary based on the selected adapter binding.</span></span>  
  
5.  <span data-ttu-id="3dc0e-111">をクリックして**OK** URI を構成した場合。</span><span class="sxs-lookup"><span data-stu-id="3dc0e-111">Click **OK** when you have configured the URI.</span></span>  
  
6.  <span data-ttu-id="3dc0e-112">**[接続]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3dc0e-112">Click **Connect**.</span></span> <span data-ttu-id="3dc0e-113">接続 URI が有効であり、クライアントの資格情報 (存在する場合) が受け入れられたら場合、**カテゴリ**ペインは、アダプターによって提供される操作とカテゴリで表示されます必要があります。</span><span class="sxs-lookup"><span data-stu-id="3dc0e-113">If the connection URI is valid and client credentials (if any) are accepted, the **Category** pane should be populated with the categories and operations provided by the adapter.</span></span>  
  
7.  <span data-ttu-id="3dc0e-114">場合は、アダプターは、検索をサポート、検索フィールドはアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="3dc0e-114">If the adapter support search, the search field will be active.</span></span> <span data-ttu-id="3dc0e-115">それ以外の場合、コントラクト型でフィルター処理および内のノードをクリックして、型および操作を探索できる、**カテゴリ**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="3dc0e-115">Otherwise, you can filter by contract type and explore types and operations by clicking nodes in the **Category** pane.</span></span>  
  
8.  <span data-ttu-id="3dc0e-116">をクリックして**OK**プロキシ成果物を生成します。</span><span class="sxs-lookup"><span data-stu-id="3dc0e-116">Click **OK** to generate the proxy artifacts.</span></span> <span data-ttu-id="3dc0e-117">成果物の数は、コントラクトの型によって異なります。</span><span class="sxs-lookup"><span data-stu-id="3dc0e-117">The number of artifacts varies based on the contract type:</span></span>  
  
    |<span data-ttu-id="3dc0e-118">コントラクトの型</span><span class="sxs-lookup"><span data-stu-id="3dc0e-118">Contract Type</span></span>|<span data-ttu-id="3dc0e-119">成果物</span><span class="sxs-lookup"><span data-stu-id="3dc0e-119">Artifact</span></span>|<span data-ttu-id="3dc0e-120">Description</span><span class="sxs-lookup"><span data-stu-id="3dc0e-120">Description</span></span>||  
    |-------------------|--------------|-----------------|-|  
    |<span data-ttu-id="3dc0e-121">送信</span><span class="sxs-lookup"><span data-stu-id="3dc0e-121">Outbound</span></span>|<span data-ttu-id="3dc0e-122">XML スキーマ</span><span class="sxs-lookup"><span data-stu-id="3dc0e-122">XML Schemas</span></span>|<span data-ttu-id="3dc0e-123">選択した種類および操作のスキーマが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3dc0e-123">Contains the schemas for the selected types and operations.</span></span>||  
    |<span data-ttu-id="3dc0e-124">送信</span><span class="sxs-lookup"><span data-stu-id="3dc0e-124">Outbound</span></span>||<span data-ttu-id="3dc0e-125">Wcf-custom 送信ポートのバインド情報 XML</span><span class="sxs-lookup"><span data-stu-id="3dc0e-125">WCF-Custom send port binding information XML</span></span>|<span data-ttu-id="3dc0e-126">Wcf-custom 送信ポートの構成 XML が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3dc0e-126">Contains configuration XML for the WCF-Custom send port.</span></span>|  
    |<span data-ttu-id="3dc0e-127">受信</span><span class="sxs-lookup"><span data-stu-id="3dc0e-127">Inbound</span></span>|<span data-ttu-id="3dc0e-128">XML スキーマ</span><span class="sxs-lookup"><span data-stu-id="3dc0e-128">XML Schemas</span></span>|<span data-ttu-id="3dc0e-129">選択した種類および操作のスキーマが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3dc0e-129">Contains the schemas for the selected types and operations.</span></span>||  
    |<span data-ttu-id="3dc0e-130">受信</span><span class="sxs-lookup"><span data-stu-id="3dc0e-130">Inbound</span></span>||<span data-ttu-id="3dc0e-131">Wcf-custom 受信ポートのバインド情報 XML</span><span class="sxs-lookup"><span data-stu-id="3dc0e-131">WCF-Custom receive port binding information XML</span></span>|<span data-ttu-id="3dc0e-132">Wcf-custom 受信ポートの構成 XML が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3dc0e-132">Contains configuration XML for the WCF-Custom receive port.</span></span>|  
  
9. <span data-ttu-id="3dc0e-133">内の XML スキーマ ファイルを使えるようになりました、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="3dc0e-133">You can now use the XML Schema files in your [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] application.</span></span>  
  
## <a name="deploy-the-biztalk-server-project"></a><span data-ttu-id="3dc0e-134">BizTalk Server プロジェクトを配置します。</span><span class="sxs-lookup"><span data-stu-id="3dc0e-134">Deploy the BizTalk Server project</span></span>  
  
1.  <span data-ttu-id="3dc0e-135">開いている **BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="3dc0e-135">Open **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="3dc0e-136">物理ポートを作成するには、ポートのバインド XML ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="3dc0e-136">Import the port binding XML file(s) to create the physical ports.</span></span> <span data-ttu-id="3dc0e-137">対象のアプリケーションを右クリックし、**アプリケーション**グループで、**バインドのインポート**に移動して、適切なポートのバインド情報 XML ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="3dc0e-137">Right-click your application under the **Applications** group, select **Import Bindings**, and then navigate to and select the appropriate port binding information XML file(s).</span></span>  
  
3.  <span data-ttu-id="3dc0e-138">定義されている論理ポートのマッピング、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を新しく作成した物理ポートにオーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="3dc0e-138">Map the logical ports defined in your [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] orchestrations to the newly created physical ports.</span></span>  
  
4.  <span data-ttu-id="3dc0e-139">をクリックして**オーケストレーション**、アプリケーションの下をクリックして、参加させ、オーケストレーションを右クリックして**Enlist**です。</span><span class="sxs-lookup"><span data-stu-id="3dc0e-139">Click **Orchestrations** under your application, right-click the orchestration to enlist, and then click **Enlist**.</span></span>  
  
5.  <span data-ttu-id="3dc0e-140">をクリックして**オーケストレーション**、アプリケーションの下をクリックして、参加させ、オーケストレーションを右クリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="3dc0e-140">Click **Orchestrations** under your application, right-click the orchestration to enlist, and then click **Start**.</span></span>  
  
6.  <span data-ttu-id="3dc0e-141">右クリックし、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アプリケーション、およびクリック**開始**です。</span><span class="sxs-lookup"><span data-stu-id="3dc0e-141">Right-click your [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] application, and then click **Start**.</span></span>  
  
## <a name="generate-multiple-schemas"></a><span data-ttu-id="3dc0e-142">複数のスキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="3dc0e-142">Generate Multiple Schemas</span></span>  
 <span data-ttu-id="3dc0e-143">1 つまたは複数の要素をスキーマのコンパイル エラーが発生しました。 重複する可能性が複数のスキーマを生成するアダプター サービス使用ウィザードを使用する場合、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="3dc0e-143">If you use the Consume Adapter Service Wizard to generate multiple schemas, one or more elements may be duplicated in the schemas resulting in compilation failure for the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] project.</span></span> <span data-ttu-id="3dc0e-144">選択してこれを回避する、**固有のスキーマ型の生成**一意の名前空間を持つスキーマ型が生成されるようにする チェック ボックスです。</span><span class="sxs-lookup"><span data-stu-id="3dc0e-144">You can avoid this by selecting the **Generate Unique Schema Type** check box to ensure that schema types are generated with unique namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3dc0e-145">参照</span><span class="sxs-lookup"><span data-stu-id="3dc0e-145">See Also</span></span>  
 [<span data-ttu-id="3dc0e-146">WCF LOB Adapter SDK を使用して作成されたアダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="3dc0e-146">Consume an adapter created using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/consume-an-adapter-created-using-the-wcf-lob-adapter-sdk.md)