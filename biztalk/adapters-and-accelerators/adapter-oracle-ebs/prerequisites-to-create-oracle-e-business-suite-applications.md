---
title: Oracle E-business Suite のアプリケーションを作成する前提条件 |Microsoft Docs
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
ms.openlocfilehash: 2ba43429f7f28cbe1748feaa05efb41f9c06d07b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013323"
---
# <a name="prerequisites-to-create-oracle-e-business-suite-applications"></a><span data-ttu-id="58d68-102">Oracle E-business Suite のアプリケーションを作成するための必要条件</span><span class="sxs-lookup"><span data-stu-id="58d68-102">Prerequisites to create Oracle E-Business Suite applications</span></span>
<span data-ttu-id="58d68-103">このセクションを使用して BizTalk アプリケーションを開発する前に必要な作業について説明します、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="58d68-103">This section provides information about what you must do before developing BizTalk applications using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="58d68-104">このセクションを指す、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] BizTalk アプリケーションの開発に使用されるツールです。</span><span class="sxs-lookup"><span data-stu-id="58d68-104">This section also points you to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] tools that are used to develop BizTalk applications.</span></span>  

## <a name="create-a-strong-named-key-file"></a><span data-ttu-id="58d68-105">厳密な名前キー ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="58d68-105">Create a strong-named key file</span></span>

<span data-ttu-id="58d68-106">Microsoft でプロジェクトをビルドする厳密な名前キー ファイルを作成する必要があります[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="58d68-106">You must create a strong-name key file to build projects in Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="58d68-107">厳密な名前は、プロジェクトの識別子で構成されています-その単純テキスト名、バージョン番号、およびカルチャ情報 (存在する場合) と公開キーおよびデジタル署名。</span><span class="sxs-lookup"><span data-stu-id="58d68-107">A strong name consists of the project's identity—its simple text name, version number, and culture information (if provided)—plus a public key and a digital signature.</span></span> <span data-ttu-id="58d68-108">厳密な名前キー ファイルには、公開キーと秘密キーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="58d68-108">The strong-name key file contains the public key and the private key.</span></span>  

> [!IMPORTANT]
>  <span data-ttu-id="58d68-109">1 回限りのタスクは、厳密な名前キー ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="58d68-109">Creating a strong-name key file is a one-time task.</span></span> <span data-ttu-id="58d68-110">同じキーは、開発したすべての BizTalk アプリケーションを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="58d68-110">You can use the same key for all the BizTalk applications you develop.</span></span>  

### <a name="prerequisites"></a><span data-ttu-id="58d68-111">前提条件</span><span class="sxs-lookup"><span data-stu-id="58d68-111">Prerequisites</span></span>  
 <span data-ttu-id="58d68-112">Microsoft が必要[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]厳密な名前キーを作成するコンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="58d68-112">You must have Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] installed on the computer where you want to create a strong-name key.</span></span>  

### <a name="create-a-strong-name-key-file"></a><span data-ttu-id="58d68-113">厳密な名前キー ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="58d68-113">Create a strong-name key file</span></span>  

1.  <span data-ttu-id="58d68-114">Visual Studio 用開発者コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="58d68-114">Open the developer command prompt for Visual Studio.</span></span>  

2.  <span data-ttu-id="58d68-115">コマンド プロンプトでは、キー ファイルを作成する場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="58d68-115">At the command prompt, navigate to the location where you want to create the key file.</span></span> <span data-ttu-id="58d68-116">たとえば、「 `cd C:\Sample`、し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="58d68-116">For example, type `cd C:\Sample`, and then press ENTER.</span></span>  

3.  <span data-ttu-id="58d68-117">コマンド プロンプトで「`sn -k <key file name>.snk`」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="58d68-117">At the command prompt, type `sn -k <key file name>.snk`, and then press ENTER.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="58d68-118">キーのペアが厳密な名前キー ファイルに書き込まれたことを示すコマンド プロンプトでのメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="58d68-118">You should receive a message at the command prompt stating that the key pair was written to the strong-name key file.</span></span>  

4.  <span data-ttu-id="58d68-119">コマンド プロンプトで「`exit`」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="58d68-119">At the command prompt, type `exit`, and then press ENTER.</span></span>  

## <a name="learn-the-biztalk-server-tools"></a><span data-ttu-id="58d68-120">BizTalk Server ツールについて説明します</span><span class="sxs-lookup"><span data-stu-id="58d68-120">Learn the BizTalk Server tools</span></span>

<span data-ttu-id="58d68-121">使用する方法に関するトピック、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]で[BizTalk Server アプリケーションの開発](../../core/developing-biztalk-server-applications.md)の数に関する実用的な知識があることを前提として記述された[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ツール。</span><span class="sxs-lookup"><span data-stu-id="58d68-121">The topics on how to use the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] in [Developing BizTalk Server Applications](../../core/developing-biztalk-server-applications.md) are written with the assumption that you have working knowledge of a number of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] tools.</span></span> <span data-ttu-id="58d68-122">次のツールを使用して BizTalk アプリケーションの開発に使用する、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="58d68-122">You will use the following tools to develop BizTalk applications using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]:</span></span>  

- <span data-ttu-id="58d68-123">Microsoft [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58d68-123">Microsoft [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]</span></span> 

- <span data-ttu-id="58d68-124">BizTalk エクスプローラー</span><span class="sxs-lookup"><span data-stu-id="58d68-124">BizTalk Explorer</span></span>  

- <span data-ttu-id="58d68-125">オーケストレーション eesigner</span><span class="sxs-lookup"><span data-stu-id="58d68-125">Orchestration eesigner</span></span>  

- <span data-ttu-id="58d68-126">パイプライン デザイナー</span><span class="sxs-lookup"><span data-stu-id="58d68-126">Pipeline designer</span></span>  

- <span data-ttu-id="58d68-127">BizTalk マッパー</span><span class="sxs-lookup"><span data-stu-id="58d68-127">BizTalk mapper</span></span>  

- <span data-ttu-id="58d68-128">BizTalk Server 管理コンソール</span><span class="sxs-lookup"><span data-stu-id="58d68-128">BizTalk Server Administration console</span></span>  

### <a name="prerequisites"></a><span data-ttu-id="58d68-129">前提条件</span><span class="sxs-lookup"><span data-stu-id="58d68-129">Prerequisites</span></span>  
 <span data-ttu-id="58d68-130">Microsoft をインストールする必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アクセスする前に、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ツール。</span><span class="sxs-lookup"><span data-stu-id="58d68-130">You must install Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] before you can access the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] tools.</span></span>  

### <a name="biztalk-server-tools"></a><span data-ttu-id="58d68-131">BizTalk Server ツール</span><span class="sxs-lookup"><span data-stu-id="58d68-131">BizTalk Server Tools</span></span>  
 <span data-ttu-id="58d68-132">次の表にトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ドキュメントの一覧表示されているツールを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="58d68-132">The following table includes topics in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] documentation that explain how to use each of the listed tools.</span></span>  


|                                   <span data-ttu-id="58d68-133">ツール</span><span class="sxs-lookup"><span data-stu-id="58d68-133">Tool</span></span>                                    |                                                                                                                                                                                              <span data-ttu-id="58d68-134">トピックでは[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]コア ドキュメント</span><span class="sxs-lookup"><span data-stu-id="58d68-134">Topics in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] core documentation</span></span>                                                                                                                                                                                               |
|---------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] | <span data-ttu-id="58d68-135">-   [Visual Studio を使用](../../core/using-visual-studio.md)</span><span class="sxs-lookup"><span data-stu-id="58d68-135">-   [Using Visual Studio](../../core/using-visual-studio.md)</span></span> <br /><span data-ttu-id="58d68-136">-   [BizTalk プロジェクトでの作業](../../core/working-with-biztalk-projects.md)</span><span class="sxs-lookup"><span data-stu-id="58d68-136">-   [Working with BizTalk Projects](../../core/working-with-biztalk-projects.md)</span></span><br /><span data-ttu-id="58d68-137">-   [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリの展開](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)</span><span class="sxs-lookup"><span data-stu-id="58d68-137">-   [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)</span></span><br /><br /> <span data-ttu-id="58d68-138">詳細についての Visual Studio のソリューション、プロジェクト、およびにある項目について説明します[Visual Studio のソリューションおよびプロジェクト](https://msdn.microsoft.com/library/b142f8e7.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="58d68-138">Learn more about Visual Studio solutions, projects, and items at [Solutions and Projects in Visual Studio](https://msdn.microsoft.com/library/b142f8e7.aspx).</span></span> |
|                          <span data-ttu-id="58d68-139">オーケストレーション デザイナー</span><span class="sxs-lookup"><span data-stu-id="58d68-139">Orchestration Designer</span></span>                           |                                                                                                                                                                                          [<span data-ttu-id="58d68-140">オーケストレーション デザイナーを使用してオーケストレーションの作成</span><span class="sxs-lookup"><span data-stu-id="58d68-140">Creating orchestrations using orchestration designer</span></span>](../../core/creating-orchestrations-using-orchestration-designer.md)                                                                                                                                                                                           |
|                             <span data-ttu-id="58d68-141">パイプライン デザイナー</span><span class="sxs-lookup"><span data-stu-id="58d68-141">Pipeline Designer</span></span>                             |                                                                                                                                                                                                    [<span data-ttu-id="58d68-142">パイプライン デザイナーを使用してパイプラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="58d68-142">Creating pipelines using pipeline designer</span></span>](../../core/creating-pipelines-using-pipeline-designer.md)                                                                                                                                                                                                     |
|                              <span data-ttu-id="58d68-143">BizTalk マッパー</span><span class="sxs-lookup"><span data-stu-id="58d68-143">BizTalk Mapper</span></span>                               |                                                                                                                                                                                                            [<span data-ttu-id="58d68-144">BizTalk マッパーを使用してマップを作成します。</span><span class="sxs-lookup"><span data-stu-id="58d68-144">Creating maps using BizTalk mapper</span></span>](../../core/creating-maps-using-biztalk-mapper.md)                                                                                                                                                                                                             |
|                   <span data-ttu-id="58d68-145">BizTalk Server 管理コンソール</span><span class="sxs-lookup"><span data-stu-id="58d68-145">BizTalk Server Administration console</span></span>                   |                                                                                                                                                                                               [<span data-ttu-id="58d68-146">BizTalk Server 管理コンソールの使用</span><span class="sxs-lookup"><span data-stu-id="58d68-146">Using the BizTalk Server Administration console</span></span>](../../core/using-the-biztalk-server-administration-console.md)                                                                                                                                                                                                |

## <a name="next"></a><span data-ttu-id="58d68-147">Next</span><span class="sxs-lookup"><span data-stu-id="58d68-147">Next</span></span>

[<span data-ttu-id="58d68-148">Oracle E-business Suite のアプリケーションを作成する構成要素</span><span class="sxs-lookup"><span data-stu-id="58d68-148">Building blocks to create Oracle E-Business Suite applications</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)  