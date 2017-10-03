---
title: "Siebel アプリケーションを作成する前提条件 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2c08f853-7f72-4e08-aa63-debdab68c972
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eeea15b7a05eb50b498c4c177c987f5c5c736a85
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="prerequisites-to-create-siebel-applications"></a><span data-ttu-id="ac19a-102">Siebel アプリケーションを作成するための必要条件</span><span class="sxs-lookup"><span data-stu-id="ac19a-102">Prerequisites to create Siebel applications</span></span>
<span data-ttu-id="ac19a-103">使用して BizTalk アプリケーションを開発する前に行う必要があります、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ac19a-103">What you must do before developing BizTalk applications using the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span> <span data-ttu-id="ac19a-104">このトピックでは、BizTalk アプリケーションの開発に使用される一部の BizTalk Server ツールも表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac19a-104">The topic also lists some BizTalk Server tools that are used to develop BizTalk applications.</span></span>  
  
## <a name="create-a-strong-named-key-file"></a><span data-ttu-id="ac19a-105">厳密な名前キー ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="ac19a-105">Create a strong-named key file</span></span>

<span data-ttu-id="ac19a-106">Microsoft でプロジェクトをビルドするための厳密な名前キー ファイルを作成する必要があります[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ac19a-106">You must create a strong-name key file to build projects in Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="ac19a-107">厳密な名前は、プロジェクトの識別子で構成されています-その単純テキスト名、バージョン番号、およびカルチャ情報 (存在する場合)。公開キーとデジタル署名します。</span><span class="sxs-lookup"><span data-stu-id="ac19a-107">A strong name consists of the project's identity — its simple text name, version number, and culture information (if provided); plus a public key and a digital signature.</span></span> <span data-ttu-id="ac19a-108">厳密な名前キー ファイルには、公開キーと秘密キーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ac19a-108">The strong-name key file contains the public key and the private key.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ac19a-109">1 回限りのタスクは、厳密な名前キー ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="ac19a-109">Creating a strong-name key file is a one-time task.</span></span> <span data-ttu-id="ac19a-110">すべての BizTalk アプリケーションを開発するため、同じキーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ac19a-110">You can use the same key for all the BizTalk applications you develop.</span></span>  
  
### <a name="prerequisites"></a><span data-ttu-id="ac19a-111">前提条件</span><span class="sxs-lookup"><span data-stu-id="ac19a-111">Prerequisites</span></span>  
 <span data-ttu-id="ac19a-112">Microsoft に設定する必要があります[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]厳密な名前キーを作成するコンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="ac19a-112">You must have Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] installed on the computer where you want to create a strong-name key.</span></span>  
  
### <a name="create-a-strong-name-key-file"></a><span data-ttu-id="ac19a-113">厳密な名前キー ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="ac19a-113">Create a strong-name key file</span></span>  
  
1.  <span data-ttu-id="ac19a-114">Visual Studio 用開発者コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="ac19a-114">Open the developer command prompt for Visual Studio.</span></span>  
  
2.  <span data-ttu-id="ac19a-115">コマンド プロンプトで、キー ファイルを作成する場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="ac19a-115">At the command prompt, navigate to the location where you want to create the key file.</span></span> <span data-ttu-id="ac19a-116">たとえば、「 `cd C:\Sample`、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="ac19a-116">For example, type `cd C:\Sample`, and then press ENTER.</span></span>  
  
3.  <span data-ttu-id="ac19a-117">コマンド プロンプトで「`sn -k <key file name>.snk`」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="ac19a-117">At the command prompt, type `sn -k <key file name>.snk`, and then press ENTER.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ac19a-118">厳密な名前キー ファイルへのキー ペアが作成されたことを示すコマンド プロンプトでメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac19a-118">You should receive a message at the command prompt stating that the key pair was written to the strong-name key file.</span></span>  
  
4.  <span data-ttu-id="ac19a-119">コマンド プロンプトで「`exit`」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="ac19a-119">At the command prompt, type `exit`, and then press ENTER.</span></span>  
  
## <a name="learn-the-biztalk-server-tools"></a><span data-ttu-id="ac19a-120">BizTalk Server ツールを説明します。</span><span class="sxs-lookup"><span data-stu-id="ac19a-120">Learn the BizTalk Server tools</span></span>

<span data-ttu-id="ac19a-121">使用する方法に関するトピック、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]で[Siebel アダプターと BizTalk アプリケーションを作成するビルド ブロック](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)の数に関する実用的な知識があることを想定して記述された[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ツールです。</span><span class="sxs-lookup"><span data-stu-id="ac19a-121">The topics on how to use the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] in [Building blocks to create BizTalk applications with the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md) are written with the assumption that you have working knowledge of a number of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] tools.</span></span> <span data-ttu-id="ac19a-122">使用して BizTalk アプリケーションを開発する次のツールを使用する、 [!INCLUDE[adaptersiebel_md](../../includes/adaptersiebel-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="ac19a-122">You use the following tools to develop BizTalk applications using the [!INCLUDE[adaptersiebel_md](../../includes/adaptersiebel-md.md)]:</span></span>  
  
-   <span data-ttu-id="ac19a-123">Microsoft [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac19a-123">Microsoft [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]</span></span> 
  
-   <span data-ttu-id="ac19a-124">BizTalk エクスプローラー</span><span class="sxs-lookup"><span data-stu-id="ac19a-124">BizTalk Explorer</span></span>  
  
-   <span data-ttu-id="ac19a-125">オーケストレーション eesigner</span><span class="sxs-lookup"><span data-stu-id="ac19a-125">Orchestration eesigner</span></span>  
  
-   <span data-ttu-id="ac19a-126">パイプライン デザイナー</span><span class="sxs-lookup"><span data-stu-id="ac19a-126">Pipeline designer</span></span>  
  
-   <span data-ttu-id="ac19a-127">BizTalk マッパー</span><span class="sxs-lookup"><span data-stu-id="ac19a-127">BizTalk mapper</span></span>  
  
-   <span data-ttu-id="ac19a-128">BizTalk Server 管理コンソール</span><span class="sxs-lookup"><span data-stu-id="ac19a-128">BizTalk Server Administration console</span></span>  
  
### <a name="prerequisites"></a><span data-ttu-id="ac19a-129">前提条件</span><span class="sxs-lookup"><span data-stu-id="ac19a-129">Prerequisites</span></span>  
 <span data-ttu-id="ac19a-130">Microsoft をインストールする必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]にアクセスできるように、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ツールです。</span><span class="sxs-lookup"><span data-stu-id="ac19a-130">You must install Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] before you can access the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] tools.</span></span>  
  
### <a name="biztalk-server-tools"></a><span data-ttu-id="ac19a-131">BizTalk Server ツール</span><span class="sxs-lookup"><span data-stu-id="ac19a-131">BizTalk Server Tools</span></span>  
 <span data-ttu-id="ac19a-132">次の表にトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]各ツールの使用方法を説明するドキュメントです。</span><span class="sxs-lookup"><span data-stu-id="ac19a-132">The following table includes topics in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] documentation that explain how to use each of the listed tools.</span></span>  
  
|<span data-ttu-id="ac19a-133">ツール</span><span class="sxs-lookup"><span data-stu-id="ac19a-133">Tool</span></span>|<span data-ttu-id="ac19a-134">トピックでは[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]主要マニュアル</span><span class="sxs-lookup"><span data-stu-id="ac19a-134">Topics in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] core documentation</span></span>|  
|---|---|  
|[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]|<span data-ttu-id="ac19a-135">-   [Visual Studio の使用](../../core/using-visual-studio.md)</span><span class="sxs-lookup"><span data-stu-id="ac19a-135">-   [Using Visual Studio](../../core/using-visual-studio.md)</span></span> <br /><span data-ttu-id="ac19a-136">-   [BizTalk プロジェクトでの作業](../../core/working-with-biztalk-projects.md)</span><span class="sxs-lookup"><span data-stu-id="ac19a-136">-   [Working with BizTalk Projects](../../core/working-with-biztalk-projects.md)</span></span><br /><span data-ttu-id="ac19a-137">-   [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開します。](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)</span><span class="sxs-lookup"><span data-stu-id="ac19a-137">-   [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)</span></span><br /><br /> <span data-ttu-id="ac19a-138">詳細についての Visual Studio ソリューション、プロジェクトでは、ある項目の[Visual Studio のソリューションおよびプロジェクト](https://msdn.microsoft.com/library/b142f8e7.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="ac19a-138">Learn more about Visual Studio solutions, projects, and items at [Solutions and Projects in Visual Studio](https://msdn.microsoft.com/library/b142f8e7.aspx).</span></span>|  
|<span data-ttu-id="ac19a-139">オーケストレーション デザイナー</span><span class="sxs-lookup"><span data-stu-id="ac19a-139">Orchestration Designer</span></span>|[<span data-ttu-id="ac19a-140">オーケストレーション デザイナーを使用してオーケストレーションの作成</span><span class="sxs-lookup"><span data-stu-id="ac19a-140">Creating Orchestrations Using Orchestration Designer</span></span>](../../core/creating-orchestrations-using-orchestration-designer.md)|  
|<span data-ttu-id="ac19a-141">パイプライン デザイナー</span><span class="sxs-lookup"><span data-stu-id="ac19a-141">Pipeline Designer</span></span>| [<span data-ttu-id="ac19a-142">パイプライン デザイナーを使用してパイプラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="ac19a-142">Creating Pipelines Using Pipeline Designer</span></span>](../../core/creating-pipelines-using-pipeline-designer.md)|  
|<span data-ttu-id="ac19a-143">BizTalk マッパー</span><span class="sxs-lookup"><span data-stu-id="ac19a-143">BizTalk Mapper</span></span>| [<span data-ttu-id="ac19a-144">BizTalk マッパーを使用してマップを作成します。</span><span class="sxs-lookup"><span data-stu-id="ac19a-144">Creating Maps Using BizTalk Mapper</span></span>](../../core/creating-maps-using-biztalk-mapper.md)|  
|<span data-ttu-id="ac19a-145">BizTalk Server 管理コンソール</span><span class="sxs-lookup"><span data-stu-id="ac19a-145">BizTalk Server Administration console</span></span>|[<span data-ttu-id="ac19a-146">BizTalk Server 管理コンソールを使用します。</span><span class="sxs-lookup"><span data-stu-id="ac19a-146">Using the BizTalk Server Administration Console</span></span>](../../core/using-the-biztalk-server-administration-console.md)|  
  
## <a name="next"></a><span data-ttu-id="ac19a-147">Next</span><span class="sxs-lookup"><span data-stu-id="ac19a-147">Next</span></span>
[<span data-ttu-id="ac19a-148">Siebel アダプターと BizTalk アプリケーションを作成する構成要素</span><span class="sxs-lookup"><span data-stu-id="ac19a-148">Building blocks to create BizTalk applications with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)