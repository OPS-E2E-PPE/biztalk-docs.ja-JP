---
title: BizTalk Server がアダプターをインスタンス化する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4ebe7585-5939-4142-9281-990b4849e28d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4082d9ac17ce7e97b94cd9b585eb1a6ce326f0e0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344225"
---
# <a name="how-biztalk-server-instantiates-an-adapter"></a><span data-ttu-id="ca8fe-102">BizTalk Server がアダプターをインスタンス化する方法</span><span class="sxs-lookup"><span data-stu-id="ca8fe-102">How BizTalk Server Instantiates an Adapter</span></span>
<span data-ttu-id="ca8fe-103">BizTalk サービスの開始時に、すべての受信アダプターがインスタンス化される場合は、1 つ以上の構成があるし、アクティブな場所を受信する限り、します。</span><span class="sxs-lookup"><span data-stu-id="ca8fe-103">When the BizTalk service starts, all receive adapters are instantiated, as long as they have one or more configured and active receive locations.</span></span> <span data-ttu-id="ca8fe-104">既定では、メッセージング エンジンを使用して送信する最初のメッセージをキューからに削除するまで、送信アダプターがインスタンス化されないを送信アダプターです。</span><span class="sxs-lookup"><span data-stu-id="ca8fe-104">By default a send adapter is not instantiated until the Messaging Engine removes from the queue the first message to be sent by using that send adapter.</span></span> <span data-ttu-id="ca8fe-105">(これとも呼ばれます「レイジー作成します」)ただし、サービスのスタートアップ時に送信アダプターをインスタンス化する必要がある場合を使えば、 **InitTransmitterOnServiceStart**アダプターの機能です。</span><span class="sxs-lookup"><span data-stu-id="ca8fe-105">(This is sometimes called "lazy creation.") However, if you need to instantiate a send adapter on service startup, you can use the **InitTransmitterOnServiceStart** adapter capability.</span></span> <span data-ttu-id="ca8fe-106">既定のレイジー作成を使用するのではなく、サービスのスタートアップに送信アダプターを作成するメッセージング エンジンに指示します。</span><span class="sxs-lookup"><span data-stu-id="ca8fe-106">This directs the Messaging Engine to create the send adapter on service startup rather than using the default lazy creation.</span></span> <span data-ttu-id="ca8fe-107">既定のレイジー作成の方法では、アダプターがエンドポイントで構成されていない場合に使用されるシステム リソースの量を削減できます。</span><span class="sxs-lookup"><span data-stu-id="ca8fe-107">The default lazy creation approach helps to reduce the amount of system resources used when adapters are not configured on endpoints.</span></span>  
  
 <span data-ttu-id="ca8fe-108">カスタム アダプターを作成するときに、マネージ コードを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ca8fe-108">When you create a custom adapter, we recommend that you use managed code.</span></span> <span data-ttu-id="ca8fe-109">ただし、ネイティブの COM コンポーネントを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="ca8fe-109">However, it is possible to use native COM components.</span></span> <span data-ttu-id="ca8fe-110">使用して、通常の方法で COM コンポーネント、アダプターがインスタンス化される**CoCreateInstance**します。</span><span class="sxs-lookup"><span data-stu-id="ca8fe-110">For COM components the adapter is instantiated in the normal manner using **CoCreateInstance**.</span></span>  
  
 <span data-ttu-id="ca8fe-111">.NET を指定する必要が、マネージ コードの**型**では構成ファイルはアセンブリのパスは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="ca8fe-111">For managed code, you need to specify the .NET **type** in the configuration file; the assembly path is optional.</span></span>  
  
 <span data-ttu-id="ca8fe-112">次の展開オプションが考えられます。</span><span class="sxs-lookup"><span data-stu-id="ca8fe-112">The following deployment options are possible:</span></span>  
  
|<span data-ttu-id="ca8fe-113">.NET の種類</span><span class="sxs-lookup"><span data-stu-id="ca8fe-113">.NET type</span></span>|<span data-ttu-id="ca8fe-114">アセンブリのパス</span><span class="sxs-lookup"><span data-stu-id="ca8fe-114">Assembly path</span></span>|<span data-ttu-id="ca8fe-115">アセンブリ展開メソッド</span><span class="sxs-lookup"><span data-stu-id="ca8fe-115">Assembly deployment method</span></span>|  
|---------------|-------------------|--------------------------------|  
|<span data-ttu-id="ca8fe-116">[Specified]</span><span class="sxs-lookup"><span data-stu-id="ca8fe-116">Specified</span></span>|<span data-ttu-id="ca8fe-117">指定なし</span><span class="sxs-lookup"><span data-stu-id="ca8fe-117">Not specified</span></span>|<span data-ttu-id="ca8fe-118">アセンブリと、製品ディレクトリまたは製品ディレクトリと同じ名前のサブディレクトリへの Copy アセンブリ</span><span class="sxs-lookup"><span data-stu-id="ca8fe-118">XCopy assembly to product directory or subdirectory in product directory with the same name as the assembly</span></span>|  
|<span data-ttu-id="ca8fe-119">[Specified]</span><span class="sxs-lookup"><span data-stu-id="ca8fe-119">Specified</span></span>|<span data-ttu-id="ca8fe-120">指定なし</span><span class="sxs-lookup"><span data-stu-id="ca8fe-120">Not specified</span></span>|<span data-ttu-id="ca8fe-121">グローバル アセンブリ キャッシュ (GAC) アセンブリ</span><span class="sxs-lookup"><span data-stu-id="ca8fe-121">Global assembly cache (GAC) assembly</span></span>|  
|<span data-ttu-id="ca8fe-122">[Specified]</span><span class="sxs-lookup"><span data-stu-id="ca8fe-122">Specified</span></span>|<span data-ttu-id="ca8fe-123">[Specified]</span><span class="sxs-lookup"><span data-stu-id="ca8fe-123">Specified</span></span>|<span data-ttu-id="ca8fe-124">指定されたディレクトリへの Copy アセンブリ</span><span class="sxs-lookup"><span data-stu-id="ca8fe-124">XCopy assembly to specified directory</span></span>|  
  
 <span data-ttu-id="ca8fe-125">**トラブルシューティングのヒント。** 作成できない場合に、マネージ コードを使用してアダプターを作成するときに、fuslogvw.exe ツールを使用して、解決できないアセンブリへの参照があるかを確認します。</span><span class="sxs-lookup"><span data-stu-id="ca8fe-125">**Troubleshooting Tip:** When you create an adapter using managed code, if the creation fails, use the fuslogvw.exe tool to determine if there are references to assemblies that cannot be resolved.</span></span> <span data-ttu-id="ca8fe-126">これは、よくある間違いです。</span><span class="sxs-lookup"><span data-stu-id="ca8fe-126">This is a common mistake.</span></span>  
  
 <span data-ttu-id="ca8fe-127">次の図は、指定された構成に応じた、アダプターを作成するためのロジックを示しています。</span><span class="sxs-lookup"><span data-stu-id="ca8fe-127">The following figure shows the logic for creating adapters, depending on the configuration specified:</span></span>  
  
 <span data-ttu-id="ca8fe-128">![](../core/media/initializingtheadapter.gif "InitializingTheAdapter")</span><span class="sxs-lookup"><span data-stu-id="ca8fe-128">![](../core/media/initializingtheadapter.gif "InitializingTheAdapter")</span></span>  
  
 <span data-ttu-id="ca8fe-129">次の表は、受信アダプターが構成する方法の例と方法、実行時のアセンブリを構成することがあります。</span><span class="sxs-lookup"><span data-stu-id="ca8fe-129">The following table gives an example of how a receive adapter may be configured, and the ways the run-time assembly may be configured.</span></span>  
  
|<span data-ttu-id="ca8fe-130">アセンブリ展開メソッド</span><span class="sxs-lookup"><span data-stu-id="ca8fe-130">Assembly deployment method</span></span>|<span data-ttu-id="ca8fe-131">InboundTypeName</span><span class="sxs-lookup"><span data-stu-id="ca8fe-131">InboundTypeName</span></span>|<span data-ttu-id="ca8fe-132">InboundAssemblyPath</span><span class="sxs-lookup"><span data-stu-id="ca8fe-132">InboundAssemblyPath</span></span>|  
|--------------------------------|---------------------|-------------------------|  
|<span data-ttu-id="ca8fe-133">アセンブリの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="ca8fe-133">Specify assembly location</span></span>|<span data-ttu-id="ca8fe-134">Microsoft.Samples.MyReceiveAdapter</span><span class="sxs-lookup"><span data-stu-id="ca8fe-134">Microsoft.Samples.MyReceiveAdapter</span></span>|<span data-ttu-id="ca8fe-135">C:\MyAdapter\MyAdapter.dll</span><span class="sxs-lookup"><span data-stu-id="ca8fe-135">C:\MyAdapter\MyAdapter.dll</span></span>|  
|<span data-ttu-id="ca8fe-136">.NET 型の指定 (公開キー、バージョン、およびカルチャ情報を含む)</span><span class="sxs-lookup"><span data-stu-id="ca8fe-136">Specify .NET type (include public key, version, and culture information)</span></span>|<span data-ttu-id="ca8fe-137">Microsoft.Samples.MyReceiveAdapter、MyReceiveAdapter、バージョン = 1.0.2510.24622、Culture = neutral, PublicKeyToken = 077cf886a2d1c020</span><span class="sxs-lookup"><span data-stu-id="ca8fe-137">Microsoft.Samples.MyReceiveAdapter, MyReceiveAdapter, Version=1.0.2510.24622, Culture=neutral, PublicKeyToken=077cf886a2d1c020</span></span>|<span data-ttu-id="ca8fe-138">なし</span><span class="sxs-lookup"><span data-stu-id="ca8fe-138">N/A</span></span>|  
|<span data-ttu-id="ca8fe-139">GAC アセンブリ</span><span class="sxs-lookup"><span data-stu-id="ca8fe-139">GAC assembly</span></span>|<span data-ttu-id="ca8fe-140">Microsoft.Samples.MyReceiveAdapter、MyReceiveAdapter、バージョン = 1.0.2510.24622、Culture = neutral, PublicKeyToken = 077cf886a2d1c020</span><span class="sxs-lookup"><span data-stu-id="ca8fe-140">Microsoft.Samples.MyReceiveAdapter, MyReceiveAdapter, Version=1.0.2510.24622, Culture=neutral, PublicKeyToken=077cf886a2d1c020</span></span>|<span data-ttu-id="ca8fe-141">なし</span><span class="sxs-lookup"><span data-stu-id="ca8fe-141">N/A</span></span>|