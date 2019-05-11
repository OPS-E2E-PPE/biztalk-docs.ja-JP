---
title: SAP アプリケーションを作成する前提条件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 51ae9569-4081-4142-9ee2-8ae0069e9d90
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e10633cb6a8cc53d814ef25c83a1de9c6f8aad8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373115"
---
# <a name="prerequisites-to-create-sap-applications"></a><span data-ttu-id="f2f3d-102">SAP アプリケーションを作成するための必要条件</span><span class="sxs-lookup"><span data-stu-id="f2f3d-102">Prerequisites to create SAP applications</span></span>
<span data-ttu-id="f2f3d-103">このセクションを使用して BizTalk アプリケーションを開発する前に実行する必要がありますタスクに関する情報を提供する、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="f2f3d-103">This section provides information about tasks that you must perform before developing BizTalk applications using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="f2f3d-104">セクションには、BizTalk アプリケーションの開発に使用されるいくつかの BizTalk Server ツールも一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2f3d-104">The section also lists some BizTalk Server tools that are used to develop BizTalk applications.</span></span>  

## <a name="create-a-strong-name-key-file"></a><span data-ttu-id="f2f3d-105">厳密な名前キー ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="f2f3d-105">Create a strong-name key file</span></span>

<span data-ttu-id="f2f3d-106">Microsoft でプロジェクトをビルドする厳密な名前キー ファイルを作成する必要があります[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="f2f3d-106">You must create a strong-name key file to build projects in Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="f2f3d-107">厳密な名前は、プロジェクトの識別子で構成されています-その単純テキスト名、バージョン番号、およびカルチャ情報 (存在する場合) と公開キーおよびデジタル署名。</span><span class="sxs-lookup"><span data-stu-id="f2f3d-107">A strong name consists of the project's identity—its simple text name, version number, and culture information (if provided)—plus a public key and a digital signature.</span></span> <span data-ttu-id="f2f3d-108">厳密な名前キー ファイルには、公開キーと秘密キーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f2f3d-108">The strong-name key file contains the public key and the private key.</span></span>  

> [!IMPORTANT]
>  <span data-ttu-id="f2f3d-109">1 回限りのタスクは、厳密な名前キー ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="f2f3d-109">Creating a strong-name key file is a one-time task.</span></span> <span data-ttu-id="f2f3d-110">同じキーは、開発したすべての BizTalk アプリケーションを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="f2f3d-110">You can use the same key for all the BizTalk applications you develop.</span></span>  

1.  <span data-ttu-id="f2f3d-111">Visual Studio 用開発者コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="f2f3d-111">Open the developer command prompt for Visual Studio.</span></span>  

2.  <span data-ttu-id="f2f3d-112">コマンド プロンプトでは、キー ファイルを作成する場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="f2f3d-112">At the command prompt navigate to the location where you want to create the key file.</span></span> <span data-ttu-id="f2f3d-113">たとえば、「 **cd C:\Sample**し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="f2f3d-113">For example, type **cd C:\Sample**,and then press ENTER.</span></span>  

3.  <span data-ttu-id="f2f3d-114">コマンド プロンプトで「`sn -k <key file name\>.snk`」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="f2f3d-114">At the command prompt, type `sn -k <key file name\>.snk`, and then press ENTER.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="f2f3d-115">キーのペアが厳密な名前キー ファイルに書き込まれたことを示すコマンド プロンプトでのメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2f3d-115">You should receive a message at the command prompt stating that the key pair was written to the strong-name key file.</span></span>  

4.  <span data-ttu-id="f2f3d-116">コマンド プロンプトで「**終了**、し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="f2f3d-116">At the command prompt, type **exit**, and then press ENTER.</span></span>  

## <a name="learn-the-biztalk-server-tools"></a><span data-ttu-id="f2f3d-117">BizTalk Server ツールについて説明します</span><span class="sxs-lookup"><span data-stu-id="f2f3d-117">Learn the BizTalk Server tools</span></span>

<span data-ttu-id="f2f3d-118">使用する方法に関するトピック、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]で[開発の BizTalk アプリケーション](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)さまざまな BizTalk Server ツールに関する実用的な知識があることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="f2f3d-118">The topics on how to use the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] in [Develop BizTalk applications](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md) assume that you have working knowledge of a number of BizTalk Server tools.</span></span> <span data-ttu-id="f2f3d-119">次のツールを使用して BizTalk アプリケーションの開発に使用する[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="f2f3d-119">You will use the following tools to develop BizTalk applications using [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]:</span></span>  

- <span data-ttu-id="f2f3d-120">Microsoft [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2f3d-120">Microsoft [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]</span></span> 

- <span data-ttu-id="f2f3d-121">オーケストレーション eesigner</span><span class="sxs-lookup"><span data-stu-id="f2f3d-121">Orchestration eesigner</span></span>  

- <span data-ttu-id="f2f3d-122">パイプライン デザイナー</span><span class="sxs-lookup"><span data-stu-id="f2f3d-122">Pipeline designer</span></span>  

- <span data-ttu-id="f2f3d-123">BizTalk マッパー</span><span class="sxs-lookup"><span data-stu-id="f2f3d-123">BizTalk mapper</span></span>  

- [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="f2f3d-124">管理コンソール</span><span class="sxs-lookup"><span data-stu-id="f2f3d-124">Administration console</span></span>  


### <a name="prerequisites"></a><span data-ttu-id="f2f3d-125">前提条件</span><span class="sxs-lookup"><span data-stu-id="f2f3d-125">Prerequisites</span></span>  
 <span data-ttu-id="f2f3d-126">インストールする必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アクセスする前に、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ツール。</span><span class="sxs-lookup"><span data-stu-id="f2f3d-126">You must install [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] before you can access the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] tools.</span></span>  

### <a name="biztalk-server-tools"></a><span data-ttu-id="f2f3d-127">BizTalk Server ツール</span><span class="sxs-lookup"><span data-stu-id="f2f3d-127">BizTalk Server Tools</span></span>  
 <span data-ttu-id="f2f3d-128">次の表にトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ドキュメントの一覧表示されているツールを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f2f3d-128">The following table includes topics in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] documentation that explain how to use each of the listed tools.</span></span>  


|                                   <span data-ttu-id="f2f3d-129">ツール</span><span class="sxs-lookup"><span data-stu-id="f2f3d-129">Tool</span></span>                                    |                                                                                                                                                                                              <span data-ttu-id="f2f3d-130">トピックでは[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]コア ドキュメント</span><span class="sxs-lookup"><span data-stu-id="f2f3d-130">Topics in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] core documentation</span></span>                                                                                                                                                                                               |
|---------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] | <span data-ttu-id="f2f3d-131">-   [Visual Studio を使用](../../core/using-visual-studio.md)</span><span class="sxs-lookup"><span data-stu-id="f2f3d-131">-   [Using Visual Studio](../../core/using-visual-studio.md)</span></span> <br /><span data-ttu-id="f2f3d-132">-   [BizTalk プロジェクトでの作業](../../core/working-with-biztalk-projects.md)</span><span class="sxs-lookup"><span data-stu-id="f2f3d-132">-   [Working with BizTalk Projects](../../core/working-with-biztalk-projects.md)</span></span><br /><span data-ttu-id="f2f3d-133">-   [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリの展開](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)</span><span class="sxs-lookup"><span data-stu-id="f2f3d-133">-   [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)</span></span><br /><br /> <span data-ttu-id="f2f3d-134">詳細についての Visual Studio のソリューション、プロジェクト、およびにある項目について説明します[Visual Studio のソリューションおよびプロジェクト](https://msdn.microsoft.com/library/b142f8e7.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="f2f3d-134">Learn more about Visual Studio solutions, projects, and items at [Solutions and Projects in Visual Studio](https://msdn.microsoft.com/library/b142f8e7.aspx).</span></span> |
|                          <span data-ttu-id="f2f3d-135">オーケストレーション デザイナー</span><span class="sxs-lookup"><span data-stu-id="f2f3d-135">Orchestration Designer</span></span>                           |                                                                                                                                                                                          [<span data-ttu-id="f2f3d-136">オーケストレーション デザイナーを使用してオーケストレーションの作成</span><span class="sxs-lookup"><span data-stu-id="f2f3d-136">Creating orchestrations using orchestration designer</span></span>](../../core/creating-orchestrations-using-orchestration-designer.md)                                                                                                                                                                                           |
|                             <span data-ttu-id="f2f3d-137">パイプライン デザイナー</span><span class="sxs-lookup"><span data-stu-id="f2f3d-137">Pipeline Designer</span></span>                             |                                                                                                                                                                                                    [<span data-ttu-id="f2f3d-138">パイプライン デザイナーを使用してパイプラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="f2f3d-138">Creating pipelines using pipeline designer</span></span>](../../core/creating-pipelines-using-pipeline-designer.md)                                                                                                                                                                                                     |
|                              <span data-ttu-id="f2f3d-139">BizTalk マッパー</span><span class="sxs-lookup"><span data-stu-id="f2f3d-139">BizTalk Mapper</span></span>                               |                                                                                                                                                                                                            [<span data-ttu-id="f2f3d-140">BizTalk マッパーを使用してマップを作成します。</span><span class="sxs-lookup"><span data-stu-id="f2f3d-140">Creating maps using BizTalk mapper</span></span>](../../core/creating-maps-using-biztalk-mapper.md)                                                                                                                                                                                                             |
|                   <span data-ttu-id="f2f3d-141">BizTalk Server 管理コンソール</span><span class="sxs-lookup"><span data-stu-id="f2f3d-141">BizTalk Server Administration console</span></span>                   |                                                                                                                                                                                               [<span data-ttu-id="f2f3d-142">BizTalk Server 管理コンソールを使用します。</span><span class="sxs-lookup"><span data-stu-id="f2f3d-142">Using the BizTalk Server Administration console</span></span>](../../core/using-the-biztalk-server-administration-console.md)                                                                                                                                                                                                |

## <a name="next"></a><span data-ttu-id="f2f3d-143">Next</span><span class="sxs-lookup"><span data-stu-id="f2f3d-143">Next</span></span>
[<span data-ttu-id="f2f3d-144">SAP アプリケーションを作成するための構成要素</span><span class="sxs-lookup"><span data-stu-id="f2f3d-144">Building blocks to create SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)