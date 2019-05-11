---
title: Oracle データベース アプリケーションを作成する前提条件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- strong-name key file, creating a
ms.assetid: 7a6b2e50-8153-468c-a25e-c15612792773
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bf3988692592af3377403ffc454ad327f63c1da
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376249"
---
# <a name="prerequisites-to-create-oracle-database-applications"></a><span data-ttu-id="7c72d-102">Oracle データベース アプリケーションを作成するための必要条件</span><span class="sxs-lookup"><span data-stu-id="7c72d-102">Prerequisites to create Oracle Database applications</span></span>
<span data-ttu-id="7c72d-103">使用して BizTalk アプリケーションを開発する前に行う必要があります、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="7c72d-103">What you must do before developing BizTalk applications using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="7c72d-104">セクションには、BizTalk アプリケーションの開発に使用されるいくつかの BizTalk Server ツールも一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="7c72d-104">The section also lists some BizTalk Server tools that are used to develop BizTalk applications.</span></span>  

## <a name="create-a-strong-named-key-file"></a><span data-ttu-id="7c72d-105">厳密な名前キー ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="7c72d-105">Create a strong-named key file</span></span>

<span data-ttu-id="7c72d-106">Microsoft でプロジェクトをビルドする厳密な名前キー ファイルを作成する必要があります[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="7c72d-106">You must create a strong-name key file to build projects in Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="7c72d-107">厳密な名前は、プロジェクトの識別子で構成されています-その単純テキスト名、バージョン番号、およびカルチャ情報 (存在する場合)。公開キーとデジタル署名します。</span><span class="sxs-lookup"><span data-stu-id="7c72d-107">A strong name consists of the project's identity — its simple text name, version number, and culture information (if provided); plus a public key and a digital signature.</span></span> <span data-ttu-id="7c72d-108">厳密な名前キー ファイルには、公開キーと秘密キーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7c72d-108">The strong-name key file contains the public key and the private key.</span></span>  

> [!IMPORTANT]
>  <span data-ttu-id="7c72d-109">1 回限りのタスクは、厳密な名前キー ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="7c72d-109">Creating a strong-name key file is a one-time task.</span></span> <span data-ttu-id="7c72d-110">同じキーは、開発したすべての BizTalk アプリケーションを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="7c72d-110">You can use the same key for all the BizTalk applications you develop.</span></span>  

### <a name="prerequisites"></a><span data-ttu-id="7c72d-111">前提条件</span><span class="sxs-lookup"><span data-stu-id="7c72d-111">Prerequisites</span></span>  
 <span data-ttu-id="7c72d-112">Microsoft が必要[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]厳密な名前キーを作成するコンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="7c72d-112">You must have Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] installed on the computer where you want to create a strong-name key.</span></span>  

### <a name="create-a-strong-name-key-file"></a><span data-ttu-id="7c72d-113">厳密な名前キー ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="7c72d-113">Create a strong-name key file</span></span>  

1.  <span data-ttu-id="7c72d-114">Visual Studio 用開発者コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="7c72d-114">Open the developer command prompt for Visual Studio.</span></span>  

2.  <span data-ttu-id="7c72d-115">コマンド プロンプトでは、キー ファイルを作成する場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="7c72d-115">At the command prompt, navigate to the location where you want to create the key file.</span></span> <span data-ttu-id="7c72d-116">たとえば、「 `cd C:\Sample`、し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="7c72d-116">For example, type `cd C:\Sample`, and then press ENTER.</span></span>  

3.  <span data-ttu-id="7c72d-117">コマンド プロンプトで「`sn -k <key file name>.snk`」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="7c72d-117">At the command prompt, type `sn -k <key file name>.snk`, and then press ENTER.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="7c72d-118">キーのペアが厳密な名前キー ファイルに書き込まれたことを示すコマンド プロンプトでのメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7c72d-118">You should receive a message at the command prompt stating that the key pair was written to the strong-name key file.</span></span>  

4.  <span data-ttu-id="7c72d-119">コマンド プロンプトで「`exit`」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="7c72d-119">At the command prompt, type `exit`, and then press ENTER.</span></span>  

## <a name="learn-the-biztalk-server-tools"></a><span data-ttu-id="7c72d-120">BizTalk Server ツールについて説明します</span><span class="sxs-lookup"><span data-stu-id="7c72d-120">Learn the BizTalk Server tools</span></span>

<span data-ttu-id="7c72d-121">使用する方法に関するトピック、[!INCLUDE[adapteroracle_short_md](../../includes/adapteroracle-short-md.md)]で[Oracle データベースと BizTalk アプリケーションを開発する構成要素](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)の数に関する実用的な知識があることを前提として記述された[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ツール。</span><span class="sxs-lookup"><span data-stu-id="7c72d-121">The topics on how to use the [!INCLUDE[adapteroracle_short_md](../../includes/adapteroracle-short-md.md)] in [Building Blocks to develop BizTalk Applications with Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md) are written with the assumption that you have working knowledge of a number of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] tools.</span></span> <span data-ttu-id="7c72d-122">次のツールを使用して BizTalk アプリケーションの開発を使用して、 [!INCLUDE[adapteroracle_md](../../includes/adapteroracle-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="7c72d-122">You use the following tools to develop BizTalk applications using the [!INCLUDE[adapteroracle_md](../../includes/adapteroracle-md.md)]:</span></span>  

- <span data-ttu-id="7c72d-123">Microsoft [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c72d-123">Microsoft [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]</span></span> 

- <span data-ttu-id="7c72d-124">BizTalk エクスプ ローラー</span><span class="sxs-lookup"><span data-stu-id="7c72d-124">BizTalk Explorer</span></span>  

- <span data-ttu-id="7c72d-125">オーケストレーション eesigner</span><span class="sxs-lookup"><span data-stu-id="7c72d-125">Orchestration eesigner</span></span>  

- <span data-ttu-id="7c72d-126">パイプライン デザイナー</span><span class="sxs-lookup"><span data-stu-id="7c72d-126">Pipeline designer</span></span>  

- <span data-ttu-id="7c72d-127">BizTalk マッパー</span><span class="sxs-lookup"><span data-stu-id="7c72d-127">BizTalk mapper</span></span>  

- <span data-ttu-id="7c72d-128">BizTalk Server 管理コンソール</span><span class="sxs-lookup"><span data-stu-id="7c72d-128">BizTalk Server Administration console</span></span>  

### <a name="prerequisites"></a><span data-ttu-id="7c72d-129">前提条件</span><span class="sxs-lookup"><span data-stu-id="7c72d-129">Prerequisites</span></span>  
 <span data-ttu-id="7c72d-130">Microsoft をインストールする必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アクセスする前に、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ツール。</span><span class="sxs-lookup"><span data-stu-id="7c72d-130">You must install Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] before you can access the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] tools.</span></span>  

### <a name="biztalk-server-tools"></a><span data-ttu-id="7c72d-131">BizTalk Server ツール</span><span class="sxs-lookup"><span data-stu-id="7c72d-131">BizTalk Server Tools</span></span>  
 <span data-ttu-id="7c72d-132">次の表にトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ドキュメントの一覧表示されているツールを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7c72d-132">The following table includes topics in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] documentation that explain how to use each of the listed tools.</span></span>  


|                                   <span data-ttu-id="7c72d-133">ツール</span><span class="sxs-lookup"><span data-stu-id="7c72d-133">Tool</span></span>                                    |                                                                                                                                                                                              <span data-ttu-id="7c72d-134">トピックでは[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]コア ドキュメント</span><span class="sxs-lookup"><span data-stu-id="7c72d-134">Topics in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] core documentation</span></span>                                                                                                                                                                                               |
|---------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] | <span data-ttu-id="7c72d-135">-   [Visual Studio を使用](../../core/using-visual-studio.md)</span><span class="sxs-lookup"><span data-stu-id="7c72d-135">-   [Using Visual Studio](../../core/using-visual-studio.md)</span></span> <br /><span data-ttu-id="7c72d-136">-   [BizTalk プロジェクトでの作業](../../core/working-with-biztalk-projects.md)</span><span class="sxs-lookup"><span data-stu-id="7c72d-136">-   [Working with BizTalk Projects](../../core/working-with-biztalk-projects.md)</span></span><br /><span data-ttu-id="7c72d-137">-   [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリの展開](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)</span><span class="sxs-lookup"><span data-stu-id="7c72d-137">-   [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)</span></span><br /><br /> <span data-ttu-id="7c72d-138">詳細についての Visual Studio のソリューション、プロジェクト、およびにある項目について説明します[Visual Studio のソリューションおよびプロジェクト](https://msdn.microsoft.com/library/b142f8e7.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="7c72d-138">Learn more about Visual Studio solutions, projects, and items at [Solutions and Projects in Visual Studio](https://msdn.microsoft.com/library/b142f8e7.aspx).</span></span> |
|                          <span data-ttu-id="7c72d-139">オーケストレーション デザイナー</span><span class="sxs-lookup"><span data-stu-id="7c72d-139">Orchestration Designer</span></span>                           |                                                                                                                                                                                          [<span data-ttu-id="7c72d-140">オーケストレーション デザイナーを使用してオーケストレーションの作成</span><span class="sxs-lookup"><span data-stu-id="7c72d-140">Creating orchestrations using orchestration designer</span></span>](../../core/creating-orchestrations-using-orchestration-designer.md)                                                                                                                                                                                           |
|                             <span data-ttu-id="7c72d-141">パイプライン デザイナー</span><span class="sxs-lookup"><span data-stu-id="7c72d-141">Pipeline Designer</span></span>                             |                                                                                                                                                                                                    [<span data-ttu-id="7c72d-142">パイプライン デザイナーを使用してパイプラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="7c72d-142">Creating pipelines using pipeline designer</span></span>](../../core/creating-pipelines-using-pipeline-designer.md)                                                                                                                                                                                                     |
|                              <span data-ttu-id="7c72d-143">BizTalk マッパー</span><span class="sxs-lookup"><span data-stu-id="7c72d-143">BizTalk Mapper</span></span>                               |                                                                                                                                                                                                            [<span data-ttu-id="7c72d-144">BizTalk マッパーを使用してマップを作成します。</span><span class="sxs-lookup"><span data-stu-id="7c72d-144">Creating maps using BizTalk mapper</span></span>](../../core/creating-maps-using-biztalk-mapper.md)                                                                                                                                                                                                             |
|                   <span data-ttu-id="7c72d-145">BizTalk Server 管理コンソール</span><span class="sxs-lookup"><span data-stu-id="7c72d-145">BizTalk Server Administration console</span></span>                   |                                                                                                                                                                                               [<span data-ttu-id="7c72d-146">BizTalk Server 管理コンソールを使用します。</span><span class="sxs-lookup"><span data-stu-id="7c72d-146">Using the BizTalk Server Administration console</span></span>](../../core/using-the-biztalk-server-administration-console.md)                                                                                                                                                                                                |

## <a name="next"></a><span data-ttu-id="7c72d-147">Next</span><span class="sxs-lookup"><span data-stu-id="7c72d-147">Next</span></span>
[<span data-ttu-id="7c72d-148">Oracle データベースと BizTalk アプリケーションを開発する構成要素</span><span class="sxs-lookup"><span data-stu-id="7c72d-148">Building Blocks to develop BizTalk Applications with Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)