---
title: .NET アセンブリ、証明書、およびその他のリソースの管理 |Microsoft Docs
description: バインド ファイル、証明書、アセンブリ、仮想ディレクトリ、ファイル、および BizTalk Server では、複数の追加へのリンク
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: efe27a11-19d8-4eb3-9f8c-f4336e4c3d66
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9052b9a5bdee58e9d4cb3d51820905b492818fc3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65326596"
---
# <a name="manage-net-assemblies-certificates-and-other-resources"></a><span data-ttu-id="64470-103">.NET アセンブリ、証明書、およびその他のリソースを管理します。</span><span class="sxs-lookup"><span data-stu-id="64470-103">Manage .NET Assemblies, Certificates, and Other Resources</span></span>

## <a name="overview"></a><span data-ttu-id="64470-104">概要</span><span class="sxs-lookup"><span data-stu-id="64470-104">Overview</span></span>
<span data-ttu-id="64470-105">このセクションでは、BizTalk Server 管理コンソールと BTSTask コマンド ライン ツールを使用して、次の種類のリソース アイテムを BizTalk アプリケーションを管理するについて説明します。</span><span class="sxs-lookup"><span data-stu-id="64470-105">This section provides instructions on using the BizTalk Server Administration console and the BTSTask command-line tool to manage the following types of resource artifacts for a BizTalk application.</span></span> <span data-ttu-id="64470-106">これらのリソース アイテムに自動的に展開できません、Visual Studio から BizTalk アプリケーションにため、アプリケーションに手動で追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64470-106">These resource artifacts cannot be automatically deployed into a BizTalk application from Visual Studio, so you must add them manually to the application.</span></span> <span data-ttu-id="64470-107">アプリケーションに追加される、ただし、することができますをインポート、エクスポート、およびこれらのアプリケーションとその他のアイテムのユニットとしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="64470-107">Once added to an application, however, you can import, export, and install them as a unit with the application and its other artifacts.</span></span>  
  
-   <span data-ttu-id="64470-108">**ファイル。**</span><span class="sxs-lookup"><span data-stu-id="64470-108">**Files.**</span></span> <span data-ttu-id="64470-109">Readme ファイルなどのアドホック ファイルを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="64470-109">You can include ad hoc files, such as a Readme file.</span></span> <span data-ttu-id="64470-110">アプリケーションをインストールするときに、ファイルは、インストール フォルダーにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="64470-110">When you install the application, files are copied to the installation folder.</span></span>  
  
-   <span data-ttu-id="64470-111">**証明書。**</span><span class="sxs-lookup"><span data-stu-id="64470-111">**Certificates.**</span></span> <span data-ttu-id="64470-112">1 つの BizTalk グループから、別のアプリケーションをパッケージ化する証明書を転送できるようにアプリケーションに証明書ファイルを追加できます。</span><span class="sxs-lookup"><span data-stu-id="64470-112">You can add a certificate file to an application so that you can transport the certificate from one BizTalk group to another, packaged with an application.</span></span> <span data-ttu-id="64470-113">送信ポートおよび受信場所の id を確認して、セキュリティで保護されたリンクを確立するために証明書を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="64470-113">You assign certificates to send ports and receive locations to verify identities and to establish secure links.</span></span>  
  
-   <span data-ttu-id="64470-114">**COM と COM + コンポーネント。**</span><span class="sxs-lookup"><span data-stu-id="64470-114">**COM and COM+ components.**</span></span> <span data-ttu-id="64470-115">マネージ COM コンポーネントと、BizTalk アプリケーションに追加の機能を提供するマネージ COM + コンポーネントを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="64470-115">You can include managed COM and managed COM+ components to provide additional functionality in a BizTalk application.</span></span>  
  
-   <span data-ttu-id="64470-116">**.NET アセンブリです。**</span><span class="sxs-lookup"><span data-stu-id="64470-116">**.NET assemblies.**</span></span> <span data-ttu-id="64470-117">具体的には BizTalk アセンブリを BizTalk アプリケーション内ではない .NET アセンブリを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="64470-117">You can include .NET assemblies that are not specifically BizTalk assemblies in a BizTalk application.</span></span> <span data-ttu-id="64470-118">(BizTalk アセンブリは、BizTalk オーケストレーション、パイプライン、スキーマ、またはマップを含む .NET アセンブリです)。</span><span class="sxs-lookup"><span data-stu-id="64470-118">(BizTalk assemblies are .NET assemblies that contain BizTalk orchestrations, pipelines, schemas, or maps.)</span></span>  
  
-   <span data-ttu-id="64470-119">**BAM 定義ファイル。**</span><span class="sxs-lookup"><span data-stu-id="64470-119">**BAM definition files.**</span></span> <span data-ttu-id="64470-120">BAM の展開を容易にするには、BizTalk アプリケーションを作成し、BAM 定義を追加しています。</span><span class="sxs-lookup"><span data-stu-id="64470-120">To make BAM deployment easier, you can create a BizTalk application and add BAM definitions to it.</span></span> <span data-ttu-id="64470-121">さまざまな環境に BAM 定義を展開するのに BizTalk アプリケーションの展開機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="64470-121">You can then use the BizTalk application deployment features to deploy the BAM definitions into different environments.</span></span>  
  
-   <span data-ttu-id="64470-122">**バインド ファイルです。**</span><span class="sxs-lookup"><span data-stu-id="64470-122">**Binding files.**</span></span> <span data-ttu-id="64470-123">バインド ファイルを追加するには、アプリケーションを 1 つの展開環境から別のアプリケーションの移行も迅速かつ容易にします。</span><span class="sxs-lookup"><span data-stu-id="64470-123">You can add binding files to an application to make moving an application from one deployment environment to another quicker and easier.</span></span>  
  
-   <span data-ttu-id="64470-124">**仮想ディレクトリ。**</span><span class="sxs-lookup"><span data-stu-id="64470-124">**Virtual directories.**</span></span> <span data-ttu-id="64470-125">アプリケーションに仮想ディレクトリを追加するには、システムは、アプリケーションをデプロイできるようにします。</span><span class="sxs-lookup"><span data-stu-id="64470-125">You can add virtual directories to your application so that they will be deployed with the application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="64470-126">Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。</span><span class="sxs-lookup"><span data-stu-id="64470-126">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="64470-127">WMI の使用方法の詳細については、次を参照してください。、 **WMI クラスの参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="64470-127">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="64470-128">次のステップ</span><span class="sxs-lookup"><span data-stu-id="64470-128">Next steps</span></span>
  
-   [<span data-ttu-id="64470-129">アプリケーションにファイルを追加する</span><span class="sxs-lookup"><span data-stu-id="64470-129">Add a File to an Application</span></span>](../core/how-to-add-a-file-to-an-application.md)  
  
-   [<span data-ttu-id="64470-130">証明書をアプリケーションに追加する</span><span class="sxs-lookup"><span data-stu-id="64470-130">Add a Certificate to an Application</span></span>](../core/how-to-add-a-certificate-to-an-application.md)  
  
-   [<span data-ttu-id="64470-131">COM コンポーネントをアプリケーションに追加する</span><span class="sxs-lookup"><span data-stu-id="64470-131">Add a COM Component to an Application</span></span>](../core/how-to-add-a-com-component-to-an-application.md)  
  
-   [<span data-ttu-id="64470-132">.NET アセンブリをアプリケーションに追加する</span><span class="sxs-lookup"><span data-stu-id="64470-132">Add a .NET Assembly to an Application</span></span>](../core/how-to-add-a-net-assembly-to-an-application.md)  
  
-   [<span data-ttu-id="64470-133">アプリケーションに BAM アイテムを追加する</span><span class="sxs-lookup"><span data-stu-id="64470-133">Add a BAM Artifact to an Application</span></span>](../core/how-to-add-a-bam-artifact-to-an-application.md)  
  
-   [<span data-ttu-id="64470-134">アプリケーションにバインド ファイルを追加する</span><span class="sxs-lookup"><span data-stu-id="64470-134">Add a Binding File to an Application</span></span>](../core/how-to-add-a-binding-file-to-an-application2.md)  
  
-   [<span data-ttu-id="64470-135">仮想ディレクトリをアプリケーションに追加する</span><span class="sxs-lookup"><span data-stu-id="64470-135">Add a Virtual Directory to an Application</span></span>](../core/how-to-add-a-virtual-directory-to-an-application.md)  
  
-   [<span data-ttu-id="64470-136">.NET アセンブリ、COM コンポーネント、ファイル、または BAM アイテムの展開オプションを変更します。</span><span class="sxs-lookup"><span data-stu-id="64470-136">Modify the Deployment Options of a .NET Assembly, COM Component, File, or BAM Artifact</span></span>](../core/modify-deployment-options-of-net-assembly-com-component-file-bam-artifact.md)  
  
-   [<span data-ttu-id="64470-137">.NET アセンブリ、証明書またはその他のリソース アイテムをアプリケーションから削除する</span><span class="sxs-lookup"><span data-stu-id="64470-137">Remove a .NET Assembly, Certificate, or Other Resource Artifact from an Application</span></span>](../core/remove-a-net-assembly-certificate-or-resource-artifact-from-an-application.md)