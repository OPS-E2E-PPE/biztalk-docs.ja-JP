---
title: "BizTalk Server がアダプターにインスタンス化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4ebe7585-5939-4142-9281-990b4849e28d
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b32e6e40bf39c09e747391bba51a54143fc67e57
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-biztalk-server-instantiates-an-adapter"></a><span data-ttu-id="ac1e4-102">BizTalk Server でのアダプターのインスタンス化</span><span class="sxs-lookup"><span data-stu-id="ac1e4-102">How BizTalk Server Instantiates an Adapter</span></span>
<span data-ttu-id="ac1e4-103">BizTalk サービスの開始時に、構成されてアクティブである受信場所が 1 つ以上ある場合は、すべての受信アダプターがインスタンス化されます。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-103">When the BizTalk service starts, all receive adapters are instantiated, as long as they have one or more configured and active receive locations.</span></span> <span data-ttu-id="ac1e4-104">既定では、送信アダプターによって送信される最初のメッセージをメッセージング エンジンがキューから削除するまで、送信アダプターはインスタンス化されません </span><span class="sxs-lookup"><span data-stu-id="ac1e4-104">By default a send adapter is not instantiated until the Messaging Engine removes from the queue the first message to be sent by using that send adapter.</span></span> <span data-ttu-id="ac1e4-105">(これとも呼ばれます「レイジー作成します」)ただし、サービスのスタートアップ時に送信アダプターのインスタンスを作成する必要がある場合を使えば、 **InitTransmitterOnServiceStart**アダプターの機能です。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-105">(This is sometimes called "lazy creation.") However, if you need to instantiate a send adapter on service startup, you can use the **InitTransmitterOnServiceStart** adapter capability.</span></span> <span data-ttu-id="ac1e4-106">これにより、メッセージング エンジンは既定のレイジー作成ではなく、サービスの開始時に送信アダプターを作成するようになります。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-106">This directs the Messaging Engine to create the send adapter on service startup rather than using the default lazy creation.</span></span> <span data-ttu-id="ac1e4-107">既定のレイジー作成の方法は、エンドポイントにアダプターが構成されていない場合に、システム リソースの使用量を削減する上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-107">The default lazy creation approach helps to reduce the amount of system resources used when adapters are not configured on endpoints.</span></span>  
  
 <span data-ttu-id="ac1e4-108">カスタム アダプターを作成するときには、マネージ コードを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-108">When you create a custom adapter, we recommend that you use managed code.</span></span> <span data-ttu-id="ac1e4-109">ただし、ネイティブ COM コンポーネントを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-109">However, it is possible to use native COM components.</span></span> <span data-ttu-id="ac1e4-110">通常の方法を使用して、COM コンポーネント、アダプターがインスタンス化される**CoCreateInstance**です。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-110">For COM components the adapter is instantiated in the normal manner using **CoCreateInstance**.</span></span>  
  
 <span data-ttu-id="ac1e4-111">マネージ コード用の .NET を指定する必要があります。**型**構成ファイルにあるアセンブリのパスは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-111">For managed code, you need to specify the .NET **type** in the configuration file; the assembly path is optional.</span></span>  
  
 <span data-ttu-id="ac1e4-112">使用できる展開オプションは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-112">The following deployment options are possible:</span></span>  
  
|<span data-ttu-id="ac1e4-113">.NET の種類</span><span class="sxs-lookup"><span data-stu-id="ac1e4-113">.NET type</span></span>|<span data-ttu-id="ac1e4-114">アセンブリ パス</span><span class="sxs-lookup"><span data-stu-id="ac1e4-114">Assembly path</span></span>|<span data-ttu-id="ac1e4-115">アセンブリ展開メソッド</span><span class="sxs-lookup"><span data-stu-id="ac1e4-115">Assembly deployment method</span></span>|  
|---------------|-------------------|--------------------------------|  
|<span data-ttu-id="ac1e4-116">[Specified]</span><span class="sxs-lookup"><span data-stu-id="ac1e4-116">Specified</span></span>|<span data-ttu-id="ac1e4-117">指定なし</span><span class="sxs-lookup"><span data-stu-id="ac1e4-117">Not specified</span></span>|<span data-ttu-id="ac1e4-118">アセンブリと同じ名前を持つ、製品ディレクトリまたは製品ディレクトリ内のサブディレクトリへの Copy アセンブリ</span><span class="sxs-lookup"><span data-stu-id="ac1e4-118">XCopy assembly to product directory or subdirectory in product directory with the same name as the assembly</span></span>|  
|<span data-ttu-id="ac1e4-119">[Specified]</span><span class="sxs-lookup"><span data-stu-id="ac1e4-119">Specified</span></span>|<span data-ttu-id="ac1e4-120">指定なし</span><span class="sxs-lookup"><span data-stu-id="ac1e4-120">Not specified</span></span>|<span data-ttu-id="ac1e4-121">グローバル アセンブリ キャッシュ (GAC) アセンブリ</span><span class="sxs-lookup"><span data-stu-id="ac1e4-121">Global assembly cache (GAC) assembly</span></span>|  
|<span data-ttu-id="ac1e4-122">[Specified]</span><span class="sxs-lookup"><span data-stu-id="ac1e4-122">Specified</span></span>|<span data-ttu-id="ac1e4-123">[Specified]</span><span class="sxs-lookup"><span data-stu-id="ac1e4-123">Specified</span></span>|<span data-ttu-id="ac1e4-124">指定されたディレクトリへの Copy アセンブリ</span><span class="sxs-lookup"><span data-stu-id="ac1e4-124">XCopy assembly to specified directory</span></span>|  
  
 <span data-ttu-id="ac1e4-125">**トラブルシューティングのヒント:**作成が失敗した場合に、マネージ コードを使用してアダプターを作成するときに、fuslogvw.exe ツールを使用して、解決できないアセンブリへの参照があるかを確認します。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-125">**Troubleshooting Tip:** When you create an adapter using managed code, if the creation fails, use the fuslogvw.exe tool to determine if there are references to assemblies that cannot be resolved.</span></span> <span data-ttu-id="ac1e4-126">これはよくある間違いです。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-126">This is a common mistake.</span></span>  
  
 <span data-ttu-id="ac1e4-127">指定された構成に応じた、アダプター作成時のロジックを次に示します。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-127">The following figure shows the logic for creating adapters, depending on the configuration specified:</span></span>  
  
 ![](../core/media/initializingtheadapter.gif "InitializingTheAdapter")  
  
 <span data-ttu-id="ac1e4-128">次の表に、受信アダプターを構成する方法と、ランタイム アセンブリを構成する方法の例を示します。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-128">The following table gives an example of how a receive adapter may be configured, and the ways the run-time assembly may be configured.</span></span>  
  
|<span data-ttu-id="ac1e4-129">アセンブリ展開メソッド</span><span class="sxs-lookup"><span data-stu-id="ac1e4-129">Assembly deployment method</span></span>|<span data-ttu-id="ac1e4-130">InboundTypeName</span><span class="sxs-lookup"><span data-stu-id="ac1e4-130">InboundTypeName</span></span>|<span data-ttu-id="ac1e4-131">InboundAssemblyPath</span><span class="sxs-lookup"><span data-stu-id="ac1e4-131">InboundAssemblyPath</span></span>|  
|--------------------------------|---------------------|-------------------------|  
|<span data-ttu-id="ac1e4-132">アセンブリの場所の指定</span><span class="sxs-lookup"><span data-stu-id="ac1e4-132">Specify assembly location</span></span>|<span data-ttu-id="ac1e4-133">Microsoft.Samples.MyReceiveAdapter</span><span class="sxs-lookup"><span data-stu-id="ac1e4-133">Microsoft.Samples.MyReceiveAdapter</span></span>|<span data-ttu-id="ac1e4-134">C:\MyAdapter\MyAdapter.dll</span><span class="sxs-lookup"><span data-stu-id="ac1e4-134">C:\MyAdapter\MyAdapter.dll</span></span>|  
|<span data-ttu-id="ac1e4-135">.NET 型 (公開キー、バージョン、およびカルチャ情報) の指定</span><span class="sxs-lookup"><span data-stu-id="ac1e4-135">Specify .NET type (include public key, version, and culture information)</span></span>|<span data-ttu-id="ac1e4-136">Microsoft.Samples.MyReceiveAdapter, MyReceiveAdapter, Version=1.0.2510.24622, Culture=neutral, PublicKeyToken=077cf886a2d1c020</span><span class="sxs-lookup"><span data-stu-id="ac1e4-136">Microsoft.Samples.MyReceiveAdapter, MyReceiveAdapter, Version=1.0.2510.24622, Culture=neutral, PublicKeyToken=077cf886a2d1c020</span></span>|<span data-ttu-id="ac1e4-137">なし</span><span class="sxs-lookup"><span data-stu-id="ac1e4-137">N/A</span></span>|  
|<span data-ttu-id="ac1e4-138">GAC アセンブリ</span><span class="sxs-lookup"><span data-stu-id="ac1e4-138">GAC assembly</span></span>|<span data-ttu-id="ac1e4-139">Microsoft.Samples.MyReceiveAdapter, MyReceiveAdapter, Version=1.0.2510.24622, Culture=neutral, PublicKeyToken=077cf886a2d1c020</span><span class="sxs-lookup"><span data-stu-id="ac1e4-139">Microsoft.Samples.MyReceiveAdapter, MyReceiveAdapter, Version=1.0.2510.24622, Culture=neutral, PublicKeyToken=077cf886a2d1c020</span></span>|<span data-ttu-id="ac1e4-140">なし</span><span class="sxs-lookup"><span data-stu-id="ac1e4-140">N/A</span></span>|