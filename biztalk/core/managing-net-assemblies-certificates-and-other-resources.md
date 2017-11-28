---
title: ".NET アセンブリ、証明書、およびその他のリソースの管理 |Microsoft ドキュメント"
description: "バインド ファイル、証明書、アセンブリ、仮想ディレクトリ、ファイル、および BizTalk Server の詳細を追加するリンク"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: efe27a11-19d8-4eb3-9f8c-f4336e4c3d66
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fdb74762bdf08e6e9e2a79650a26dedb0915ea8f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="manage-net-assemblies-certificates-and-other-resources"></a><span data-ttu-id="4a8e7-103">.NET アセンブリ、証明書、およびその他のリソースを管理します。</span><span class="sxs-lookup"><span data-stu-id="4a8e7-103">Manage .NET Assemblies, Certificates, and Other Resources</span></span>

## <a name="overview"></a><span data-ttu-id="4a8e7-104">概要</span><span class="sxs-lookup"><span data-stu-id="4a8e7-104">Overview</span></span>
<span data-ttu-id="4a8e7-105">ここでは、BizTalk Server 管理コンソールと BTSTask コマンド ライン ツールを使用して、BizTalk アプリケーションの次の種類のリソース アイテムを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4a8e7-105">This section provides instructions on using the BizTalk Server Administration console and the BTSTask command-line tool to manage the following types of resource artifacts for a BizTalk application.</span></span> <span data-ttu-id="4a8e7-106">これらのリソース アイテムは、Visual Studio から BizTalk アプリケーションに自動的に展開できないため、手動でアプリケーションに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a8e7-106">These resource artifacts cannot be automatically deployed into a BizTalk application from Visual Studio, so you must add them manually to the application.</span></span> <span data-ttu-id="4a8e7-107">ただし、アプリケーションに追加した後は、アプリケーションおよびその他のアイテムで 1 つの単位としてインポート、エクスポート、およびインストールできます。</span><span class="sxs-lookup"><span data-stu-id="4a8e7-107">Once added to an application, however, you can import, export, and install them as a unit with the application and its other artifacts.</span></span>  
  
-   <span data-ttu-id="4a8e7-108">**ファイル。**</span><span class="sxs-lookup"><span data-stu-id="4a8e7-108">**Files.**</span></span> <span data-ttu-id="4a8e7-109">Readme ファイルなどのアドホック ファイルを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="4a8e7-109">You can include ad hoc files, such as a Readme file.</span></span> <span data-ttu-id="4a8e7-110">アプリケーションをインストールすると、ファイルはインストール フォルダーにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="4a8e7-110">When you install the application, files are copied to the installation folder.</span></span>  
  
-   <span data-ttu-id="4a8e7-111">**証明書。**</span><span class="sxs-lookup"><span data-stu-id="4a8e7-111">**Certificates.**</span></span> <span data-ttu-id="4a8e7-112">BizTalk アプリケーションに証明書を追加することで、アプリケーションでパッケージ化して、証明書を BizTalk グループの 1 つから別のグループに送信することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="4a8e7-112">You can add a certificate file to an application so that you can transport the certificate from one BizTalk group to another, packaged with an application.</span></span> <span data-ttu-id="4a8e7-113">証明書を送信ポートと受信場所に割り当てることにより、ID を検証し、安全なリンクを確立することができます。</span><span class="sxs-lookup"><span data-stu-id="4a8e7-113">You assign certificates to send ports and receive locations to verify identities and to establish secure links.</span></span>  
  
-   <span data-ttu-id="4a8e7-114">**COM と COM + コンポーネント。**</span><span class="sxs-lookup"><span data-stu-id="4a8e7-114">**COM and COM+ components.**</span></span> <span data-ttu-id="4a8e7-115">マネージ COM コンポーネントとマネージ COM+ コンポーネントを含めることにより、BizTalk アプリケーションに追加機能を提供できます。</span><span class="sxs-lookup"><span data-stu-id="4a8e7-115">You can include managed COM and managed COM+ components to provide additional functionality in a BizTalk application.</span></span>  
  
-   <span data-ttu-id="4a8e7-116">**.NET アセンブリです。**</span><span class="sxs-lookup"><span data-stu-id="4a8e7-116">**.NET assemblies.**</span></span> <span data-ttu-id="4a8e7-117">厳密には BizTalk アセンブリでない .NET アセンブリを BizTalk アプリケーションに含めることができます</span><span class="sxs-lookup"><span data-stu-id="4a8e7-117">You can include .NET assemblies that are not specifically BizTalk assemblies in a BizTalk application.</span></span> <span data-ttu-id="4a8e7-118">(BizTalk アセンブリは、BizTalk のオーケストレーション、パイプライン、スキーマ、またはマップを含む .NET アセンブリです)。</span><span class="sxs-lookup"><span data-stu-id="4a8e7-118">(BizTalk assemblies are .NET assemblies that contain BizTalk orchestrations, pipelines, schemas, or maps.)</span></span>  
  
-   <span data-ttu-id="4a8e7-119">**BAM 定義ファイル。**</span><span class="sxs-lookup"><span data-stu-id="4a8e7-119">**BAM definition files.**</span></span> <span data-ttu-id="4a8e7-120">BAM を簡単に展開するには、BizTalk アプリケーションを作成し、これに BAM 定義を追加します。</span><span class="sxs-lookup"><span data-stu-id="4a8e7-120">To make BAM deployment easier, you can create a BizTalk application and add BAM definitions to it.</span></span> <span data-ttu-id="4a8e7-121">その後、BizTalk アプリケーションの展開機能を使用すると、BAM 定義をさまざまな環境に展開できます。</span><span class="sxs-lookup"><span data-stu-id="4a8e7-121">You can then use the BizTalk application deployment features to deploy the BAM definitions into different environments.</span></span>  
  
-   <span data-ttu-id="4a8e7-122">**バインド ファイルです。**</span><span class="sxs-lookup"><span data-stu-id="4a8e7-122">**Binding files.**</span></span> <span data-ttu-id="4a8e7-123">バインド ファイルをアプリケーションに追加すると、アプリケーションをある展開環境から別の環境に迅速かつ容易に移動できます。</span><span class="sxs-lookup"><span data-stu-id="4a8e7-123">You can add binding files to an application to make moving an application from one deployment environment to another quicker and easier.</span></span>  
  
-   <span data-ttu-id="4a8e7-124">**仮想ディレクトリです。**</span><span class="sxs-lookup"><span data-stu-id="4a8e7-124">**Virtual directories.**</span></span> <span data-ttu-id="4a8e7-125">仮想ディレクトリをアプリケーションに追加すると、これらのディレクトリをアプリケーションと共に展開できます。</span><span class="sxs-lookup"><span data-stu-id="4a8e7-125">You can add virtual directories to your application so that they will be deployed with the application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4a8e7-126">Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。</span><span class="sxs-lookup"><span data-stu-id="4a8e7-126">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="4a8e7-127">WMI の使用については、次を参照してください。、 **WMI クラス参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="4a8e7-127">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="4a8e7-128">次の手順</span><span class="sxs-lookup"><span data-stu-id="4a8e7-128">Next steps</span></span>
  
-   [<span data-ttu-id="4a8e7-129">アプリケーションにファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="4a8e7-129">Add a File to an Application</span></span>](../core/how-to-add-a-file-to-an-application.md)  
  
-   [<span data-ttu-id="4a8e7-130">証明書をアプリケーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="4a8e7-130">Add a Certificate to an Application</span></span>](../core/how-to-add-a-certificate-to-an-application.md)  
  
-   [<span data-ttu-id="4a8e7-131">アプリケーションに COM コンポーネントを追加します。</span><span class="sxs-lookup"><span data-stu-id="4a8e7-131">Add a COM Component to an Application</span></span>](../core/how-to-add-a-com-component-to-an-application.md)  
  
-   [<span data-ttu-id="4a8e7-132">.NET アセンブリをアプリケーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="4a8e7-132">Add a .NET Assembly to an Application</span></span>](../core/how-to-add-a-net-assembly-to-an-application.md)  
  
-   [<span data-ttu-id="4a8e7-133">アプリケーションに BAM アイテムを追加します。</span><span class="sxs-lookup"><span data-stu-id="4a8e7-133">Add a BAM Artifact to an Application</span></span>](../core/how-to-add-a-bam-artifact-to-an-application.md)  
  
-   [<span data-ttu-id="4a8e7-134">バインド ファイルをアプリケーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="4a8e7-134">Add a Binding File to an Application</span></span>](../core/how-to-add-a-binding-file-to-an-application2.md)  
  
-   [<span data-ttu-id="4a8e7-135">仮想ディレクトリをアプリケーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="4a8e7-135">Add a Virtual Directory to an Application</span></span>](../core/how-to-add-a-virtual-directory-to-an-application.md)  
  
-   [<span data-ttu-id="4a8e7-136">.NET アセンブリ、COM コンポーネント、ファイル、または BAM アイテムの展開オプションを変更します。</span><span class="sxs-lookup"><span data-stu-id="4a8e7-136">Modify the Deployment Options of a .NET Assembly, COM Component, File, or BAM Artifact</span></span>](../core/modify-deployment-options-of-net-assembly-com-component-file-bam-artifact.md)  
  
-   [<span data-ttu-id="4a8e7-137">アプリケーションから .NET アセンブリ、証明書、またはその他のリソース アイテムを削除します。</span><span class="sxs-lookup"><span data-stu-id="4a8e7-137">Remove a .NET Assembly, Certificate, or Other Resource Artifact from an Application</span></span>](../core/remove-a-net-assembly-certificate-or-resource-artifact-from-an-application.md)