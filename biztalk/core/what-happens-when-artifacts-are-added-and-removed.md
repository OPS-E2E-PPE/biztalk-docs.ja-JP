---
title: アイテムを追加または削除されたときの動作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, artifacts
- artifacts, deleting
- artifacts, creating
- deleting, artifacts
ms.assetid: 811166ba-3ff4-4224-9d84-a2f4ed31bf4d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dbda3968ec4337ccf3b00bf1b1698d73c9232c47
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401077"
---
# <a name="what-happens-when-artifacts-are-added-and-removed"></a><span data-ttu-id="2110b-102">アイテムを追加または削除した場合の動作</span><span class="sxs-lookup"><span data-stu-id="2110b-102">What Happens When Artifacts Are Added and Removed</span></span>
<span data-ttu-id="2110b-103">このトピックでは、アプリケーションにアイテムを追加するときの動作について説明します。</span><span class="sxs-lookup"><span data-stu-id="2110b-103">This topic describes what happens when you add artifacts to an application.</span></span> <span data-ttu-id="2110b-104">ファイル ベースのアイテムは、BizTalk Server 管理コンソールまたは BTSTask コマンド ライン ツールを使用してアプリケーションを追加できます。</span><span class="sxs-lookup"><span data-stu-id="2110b-104">You can add file-based artifacts to an application by using the BizTalk Server Administration console or the BTSTask command-line tool.</span></span> <span data-ttu-id="2110b-105">ファイル ベースのアイテムは、次の種類を含めます。</span><span class="sxs-lookup"><span data-stu-id="2110b-105">File-based artifacts include the following types:</span></span>  
  
-   <span data-ttu-id="2110b-106">BizTalk アセンブリ</span><span class="sxs-lookup"><span data-stu-id="2110b-106">BizTalk assemblies</span></span>  
  
-   <span data-ttu-id="2110b-107">BizTalk に固有ではない .NET アセンブリ</span><span class="sxs-lookup"><span data-stu-id="2110b-107">.NET assemblies that are not BizTalk-specific</span></span>  
  
-   <span data-ttu-id="2110b-108">バインド (.xml) ファイル</span><span class="sxs-lookup"><span data-stu-id="2110b-108">Binding (.xml) files</span></span>  
  
-   <span data-ttu-id="2110b-109">COM コンポーネント</span><span class="sxs-lookup"><span data-stu-id="2110b-109">COM components</span></span>  
  
-   <span data-ttu-id="2110b-110">証明書</span><span class="sxs-lookup"><span data-stu-id="2110b-110">Certificates</span></span>  
  
-   <span data-ttu-id="2110b-111">処理前および処理後のスクリプト</span><span class="sxs-lookup"><span data-stu-id="2110b-111">Pre- and post-processing scripts</span></span>  
  
-   <span data-ttu-id="2110b-112">ポリシー</span><span class="sxs-lookup"><span data-stu-id="2110b-112">Policies</span></span>  
  
-   <span data-ttu-id="2110b-113">Readme ファイルなどのアドホック ファイル</span><span class="sxs-lookup"><span data-stu-id="2110b-113">Ad hoc files, such as Readme files</span></span>  
  
-   <span data-ttu-id="2110b-114">仮想ディレクトリ</span><span class="sxs-lookup"><span data-stu-id="2110b-114">Virtual directories</span></span>  
  
-   <span data-ttu-id="2110b-115">BAM アイテム</span><span class="sxs-lookup"><span data-stu-id="2110b-115">BAM artifacts</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2110b-116">送信ポート、送信ポート グループ、受信場所、および受信ポートは、ファイル ベースのアイテムでないし、アプリケーションに追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="2110b-116">Send ports, send port groups, receive locations, and receive ports are not file-based artifacts and cannot be added to an application.</span></span> <span data-ttu-id="2110b-117">特定のアプリケーションでこれらの成果物を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2110b-117">You must create these artifacts within a given application.</span></span> <span data-ttu-id="2110b-118">できますしに移動する別のアプリケーションにする場合。</span><span class="sxs-lookup"><span data-stu-id="2110b-118">You can then move them to a different application, if you want.</span></span> <span data-ttu-id="2110b-119">オーケストレーション、スキーマ、マップおよびパイプラインすべてデプロイし、管理を含むアセンブリの一部として。</span><span class="sxs-lookup"><span data-stu-id="2110b-119">Orchestrations, schemas, maps and pipelines are all deployed and managed as part of the assemblies that contain them.</span></span>  
  
 <span data-ttu-id="2110b-120">アプリケーションにアイテムを追加して、成果物は、BizTalk 管理データベースでのアプリケーションに関連付けられた成果物のファイル ベースのデータは管理データベースに追加されます。</span><span class="sxs-lookup"><span data-stu-id="2110b-120">When you add an artifact to an application, the artifact is associated with the application in the BizTalk Management database, and file-based data for the artifact is added to the Management database as well.</span></span> <span data-ttu-id="2110b-121">アプリケーションを簡単に転送することができ、管理データベースから .msi ファイルに、アプリケーションとそのアイテムのデータをエクスポートし、管理データベースにインポートできるので別に 1 つの BizTalk から成果物をグループ化します。別の BizTalk グループ。</span><span class="sxs-lookup"><span data-stu-id="2110b-121">This allows you to easily transport applications and artifacts from one BizTalk group to another because you can export the application and the data for its artifacts into an .msi file from the Management database, and then import it into a Management database in a different BizTalk group.</span></span>  
  
 <span data-ttu-id="2110b-122">バインド ファイルをアプリケーションに追加する場合は、バインドを適用する対象の展開環境を指定できます。</span><span class="sxs-lookup"><span data-stu-id="2110b-122">When you add a binding file to an application, you can specify the target deployment environment in which you want the bindings to be applied.</span></span> <span data-ttu-id="2110b-123">バインド ファイルをインポートするとは異なり、バインド ファイルを追加する場合は、そのバインドを適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="2110b-123">Unlike importing a binding file, when you add a binding file, its bindings are not applied.</span></span>  
  
 <span data-ttu-id="2110b-124">BizTalk アセンブリまたは .NET アセンブリをアプリケーションに追加すると、このオプションを指定する場合、アセンブリがグローバル アセンブリ キャッシュに追加されます。</span><span class="sxs-lookup"><span data-stu-id="2110b-124">When you add a BizTalk assembly or a .NET assembly to an application, the assembly is added to the global assembly cache if you specify this option.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2110b-125">参照</span><span class="sxs-lookup"><span data-stu-id="2110b-125">See Also</span></span>  
 <span data-ttu-id="2110b-126">[アプリケーション展開中にアイテムを処理します。](../core/what-happens-to-artifacts-during-application-deployment.md) </span><span class="sxs-lookup"><span data-stu-id="2110b-126">[What Happens to Artifacts During Application Deployment](../core/what-happens-to-artifacts-during-application-deployment.md) </span></span>  
 <span data-ttu-id="2110b-127">[成果物を追加または作成する方法](../core/how-to-create-or-add-an-artifact.md) </span><span class="sxs-lookup"><span data-stu-id="2110b-127">[How to Create or Add an Artifact](../core/how-to-create-or-add-an-artifact.md) </span></span>  
 <span data-ttu-id="2110b-128">[BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md) </span><span class="sxs-lookup"><span data-stu-id="2110b-128">[How to Import a BizTalk Application](../core/how-to-import-a-biztalk-application.md) </span></span>  
 [<span data-ttu-id="2110b-129">BizTalk アプリケーションをエクスポートする方法</span><span class="sxs-lookup"><span data-stu-id="2110b-129">How to Export a BizTalk Application</span></span>](../core/how-to-export-a-biztalk-application.md)