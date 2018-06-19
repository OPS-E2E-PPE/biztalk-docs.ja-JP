---
title: Oracle E-business Suite アプリケーションを作成する前提条件 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b02ea286-f301-46b3-b748-d954dead23a1
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90eac318264f53e95aade98cf9574fc0eea45483
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216762"
---
# <a name="prerequisites-to-create-oracle-e-business-suite-applications"></a><span data-ttu-id="17b4d-102">Oracle E-business Suite アプリケーションを作成するための必要条件</span><span class="sxs-lookup"><span data-stu-id="17b4d-102">Prerequisites to create Oracle E-Business Suite applications</span></span>
<span data-ttu-id="17b4d-103">このセクションの内容を使用して BizTalk アプリケーションを開発する前に行う必要がありますに関する情報を提供する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="17b4d-103">This section provides information about what you must do before developing BizTalk applications using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="17b4d-104">このセクションのリンクもに、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] BizTalk アプリケーションを開発するために使用するツールです。</span><span class="sxs-lookup"><span data-stu-id="17b4d-104">This section also points you to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] tools that are used to develop BizTalk applications.</span></span>  
  
## <a name="create-a-strong-named-key-file"></a><span data-ttu-id="17b4d-105">厳密な名前キー ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="17b4d-105">Create a strong-named key file</span></span>

<span data-ttu-id="17b4d-106">Microsoft でプロジェクトをビルドするための厳密な名前キー ファイルを作成する必要があります[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="17b4d-106">You must create a strong-name key file to build projects in Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="17b4d-107">厳密な名前は、プロジェクトの識別子で構成されています-その単純テキスト名、バージョン番号、およびカルチャ情報 (存在する場合)-と公開キーおよびデジタル署名します。</span><span class="sxs-lookup"><span data-stu-id="17b4d-107">A strong name consists of the project's identity—its simple text name, version number, and culture information (if provided)—plus a public key and a digital signature.</span></span> <span data-ttu-id="17b4d-108">厳密な名前キー ファイルには、公開キーと秘密キーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="17b4d-108">The strong-name key file contains the public key and the private key.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="17b4d-109">1 回限りのタスクは、厳密な名前キー ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="17b4d-109">Creating a strong-name key file is a one-time task.</span></span> <span data-ttu-id="17b4d-110">すべての BizTalk アプリケーションを開発するため、同じキーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="17b4d-110">You can use the same key for all the BizTalk applications you develop.</span></span>  
  
### <a name="prerequisites"></a><span data-ttu-id="17b4d-111">前提条件</span><span class="sxs-lookup"><span data-stu-id="17b4d-111">Prerequisites</span></span>  
 <span data-ttu-id="17b4d-112">Microsoft に設定する必要があります[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]厳密な名前キーを作成するコンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="17b4d-112">You must have Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] installed on the computer where you want to create a strong-name key.</span></span>  
  
### <a name="create-a-strong-name-key-file"></a><span data-ttu-id="17b4d-113">厳密な名前キー ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="17b4d-113">Create a strong-name key file</span></span>  
  
1.  <span data-ttu-id="17b4d-114">Visual Studio 用開発者コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="17b4d-114">Open the developer command prompt for Visual Studio.</span></span>  
  
2.  <span data-ttu-id="17b4d-115">コマンド プロンプトで、キー ファイルを作成する場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="17b4d-115">At the command prompt, navigate to the location where you want to create the key file.</span></span> <span data-ttu-id="17b4d-116">たとえば、「 `cd C:\Sample`、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="17b4d-116">For example, type `cd C:\Sample`, and then press ENTER.</span></span>  
  
3.  <span data-ttu-id="17b4d-117">コマンド プロンプトで「`sn -k <key file name>.snk`」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="17b4d-117">At the command prompt, type `sn -k <key file name>.snk`, and then press ENTER.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="17b4d-118">厳密な名前キー ファイルへのキー ペアが作成されたことを示すコマンド プロンプトでメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="17b4d-118">You should receive a message at the command prompt stating that the key pair was written to the strong-name key file.</span></span>  
  
4.  <span data-ttu-id="17b4d-119">コマンド プロンプトで「`exit`」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="17b4d-119">At the command prompt, type `exit`, and then press ENTER.</span></span>  
  
## <a name="learn-the-biztalk-server-tools"></a><span data-ttu-id="17b4d-120">BizTalk Server ツールを説明します。</span><span class="sxs-lookup"><span data-stu-id="17b4d-120">Learn the BizTalk Server tools</span></span>

<span data-ttu-id="17b4d-121">使用する方法に関するトピック、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]で[BizTalk Server アプリケーションの開発](../../core/developing-biztalk-server-applications.md)の数に関する実用的な知識があることを想定して記述された[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ツールです。</span><span class="sxs-lookup"><span data-stu-id="17b4d-121">The topics on how to use the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] in [Developing BizTalk Server Applications](../../core/developing-biztalk-server-applications.md) are written with the assumption that you have working knowledge of a number of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] tools.</span></span> <span data-ttu-id="17b4d-122">使用して BizTalk アプリケーションを開発する、次のツールを使用するが、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="17b4d-122">You will use the following tools to develop BizTalk applications using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]:</span></span>  
  
-   <span data-ttu-id="17b4d-123">Microsoft [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17b4d-123">Microsoft [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]</span></span> 
  
-   <span data-ttu-id="17b4d-124">BizTalk エクスプローラー</span><span class="sxs-lookup"><span data-stu-id="17b4d-124">BizTalk Explorer</span></span>  
  
-   <span data-ttu-id="17b4d-125">オーケストレーション eesigner</span><span class="sxs-lookup"><span data-stu-id="17b4d-125">Orchestration eesigner</span></span>  
  
-   <span data-ttu-id="17b4d-126">パイプライン デザイナー</span><span class="sxs-lookup"><span data-stu-id="17b4d-126">Pipeline designer</span></span>  
  
-   <span data-ttu-id="17b4d-127">BizTalk マッパー</span><span class="sxs-lookup"><span data-stu-id="17b4d-127">BizTalk mapper</span></span>  
  
-   <span data-ttu-id="17b4d-128">BizTalk Server 管理コンソール</span><span class="sxs-lookup"><span data-stu-id="17b4d-128">BizTalk Server Administration console</span></span>  
  
### <a name="prerequisites"></a><span data-ttu-id="17b4d-129">前提条件</span><span class="sxs-lookup"><span data-stu-id="17b4d-129">Prerequisites</span></span>  
 <span data-ttu-id="17b4d-130">Microsoft をインストールする必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]にアクセスできるように、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ツールです。</span><span class="sxs-lookup"><span data-stu-id="17b4d-130">You must install Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] before you can access the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] tools.</span></span>  
  
### <a name="biztalk-server-tools"></a><span data-ttu-id="17b4d-131">BizTalk Server ツール</span><span class="sxs-lookup"><span data-stu-id="17b4d-131">BizTalk Server Tools</span></span>  
 <span data-ttu-id="17b4d-132">次の表にトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]各ツールの使用方法を説明するドキュメントです。</span><span class="sxs-lookup"><span data-stu-id="17b4d-132">The following table includes topics in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] documentation that explain how to use each of the listed tools.</span></span>  
  
|<span data-ttu-id="17b4d-133">ツール</span><span class="sxs-lookup"><span data-stu-id="17b4d-133">Tool</span></span>|<span data-ttu-id="17b4d-134">トピックでは[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]主要マニュアル</span><span class="sxs-lookup"><span data-stu-id="17b4d-134">Topics in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] core documentation</span></span>|  
|---|---|  
|[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]|<span data-ttu-id="17b4d-135">-   [Visual Studio の使用](../../core/using-visual-studio.md)</span><span class="sxs-lookup"><span data-stu-id="17b4d-135">-   [Using Visual Studio](../../core/using-visual-studio.md)</span></span> <br /><span data-ttu-id="17b4d-136">-   [BizTalk プロジェクトでの作業](../../core/working-with-biztalk-projects.md)</span><span class="sxs-lookup"><span data-stu-id="17b4d-136">-   [Working with BizTalk Projects](../../core/working-with-biztalk-projects.md)</span></span><br /><span data-ttu-id="17b4d-137">-   [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開します。](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)</span><span class="sxs-lookup"><span data-stu-id="17b4d-137">-   [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)</span></span><br /><br /> <span data-ttu-id="17b4d-138">詳細についての Visual Studio ソリューション、プロジェクトでは、ある項目の[Visual Studio のソリューションおよびプロジェクト](https://msdn.microsoft.com/library/b142f8e7.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="17b4d-138">Learn more about Visual Studio solutions, projects, and items at [Solutions and Projects in Visual Studio](https://msdn.microsoft.com/library/b142f8e7.aspx).</span></span>|  
|<span data-ttu-id="17b4d-139">オーケストレーション デザイナー</span><span class="sxs-lookup"><span data-stu-id="17b4d-139">Orchestration Designer</span></span>|[<span data-ttu-id="17b4d-140">オーケストレーション デザイナーを使用してオーケストレーションの作成</span><span class="sxs-lookup"><span data-stu-id="17b4d-140">Creating orchestrations using orchestration designer</span></span>](../../core/creating-orchestrations-using-orchestration-designer.md)|  
|<span data-ttu-id="17b4d-141">パイプライン デザイナー</span><span class="sxs-lookup"><span data-stu-id="17b4d-141">Pipeline Designer</span></span>| [<span data-ttu-id="17b4d-142">パイプライン デザイナーを使用してパイプラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="17b4d-142">Creating pipelines using pipeline designer</span></span>](../../core/creating-pipelines-using-pipeline-designer.md)|  
|<span data-ttu-id="17b4d-143">BizTalk マッパー</span><span class="sxs-lookup"><span data-stu-id="17b4d-143">BizTalk Mapper</span></span>| [<span data-ttu-id="17b4d-144">BizTalk マッパーを使用してマップを作成します。</span><span class="sxs-lookup"><span data-stu-id="17b4d-144">Creating maps using BizTalk mapper</span></span>](../../core/creating-maps-using-biztalk-mapper.md)|  
|<span data-ttu-id="17b4d-145">BizTalk Server 管理コンソール</span><span class="sxs-lookup"><span data-stu-id="17b4d-145">BizTalk Server Administration console</span></span>|[<span data-ttu-id="17b4d-146">BizTalk Server 管理コンソールの使用</span><span class="sxs-lookup"><span data-stu-id="17b4d-146">Using the BizTalk Server Administration console</span></span>](../../core/using-the-biztalk-server-administration-console.md)|  
  
## <a name="next"></a><span data-ttu-id="17b4d-147">Next</span><span class="sxs-lookup"><span data-stu-id="17b4d-147">Next</span></span>

[<span data-ttu-id="17b4d-148">Oracle E-business Suite アプリケーションを作成する構成要素</span><span class="sxs-lookup"><span data-stu-id="17b4d-148">Building blocks to create Oracle E-Business Suite applications</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)  