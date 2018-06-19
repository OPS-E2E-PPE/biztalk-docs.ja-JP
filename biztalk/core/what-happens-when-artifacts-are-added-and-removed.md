---
title: 成果物の追加または削除されるときの動作 |Microsoft ドキュメント
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
ms.openlocfilehash: 464964714993205ef65d5a67de3399935f79320f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288882"
---
# <a name="what-happens-when-artifacts-are-added-and-removed"></a><span data-ttu-id="aef59-102">アイテムを追加または削除した場合の動作</span><span class="sxs-lookup"><span data-stu-id="aef59-102">What Happens When Artifacts Are Added and Removed</span></span>
<span data-ttu-id="aef59-103">このトピックでは、アプリケーションにアイテムを追加した場合の動作について説明します。</span><span class="sxs-lookup"><span data-stu-id="aef59-103">This topic describes what happens when you add artifacts to an application.</span></span> <span data-ttu-id="aef59-104">BizTalk Server 管理コンソールまたは BTSTask コマンド ライン ツールを使用して、ファイルベースのアイテムをアプリケーションに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="aef59-104">You can add file-based artifacts to an application by using the BizTalk Server Administration console or the BTSTask command-line tool.</span></span> <span data-ttu-id="aef59-105">ファイルベースのアイテムには、次の種類のものがあります。</span><span class="sxs-lookup"><span data-stu-id="aef59-105">File-based artifacts include the following types:</span></span>  
  
-   <span data-ttu-id="aef59-106">BizTalk アセンブリ</span><span class="sxs-lookup"><span data-stu-id="aef59-106">BizTalk assemblies</span></span>  
  
-   <span data-ttu-id="aef59-107">BizTalk に固有でない .NET アセンブリ</span><span class="sxs-lookup"><span data-stu-id="aef59-107">.NET assemblies that are not BizTalk-specific</span></span>  
  
-   <span data-ttu-id="aef59-108">バインド (.xml) ファイル</span><span class="sxs-lookup"><span data-stu-id="aef59-108">Binding (.xml) files</span></span>  
  
-   <span data-ttu-id="aef59-109">COM コンポーネント</span><span class="sxs-lookup"><span data-stu-id="aef59-109">COM components</span></span>  
  
-   <span data-ttu-id="aef59-110">証明書</span><span class="sxs-lookup"><span data-stu-id="aef59-110">Certificates</span></span>  
  
-   <span data-ttu-id="aef59-111">処理前および処理後のスクリプト</span><span class="sxs-lookup"><span data-stu-id="aef59-111">Pre- and post-processing scripts</span></span>  
  
-   <span data-ttu-id="aef59-112">ポリシー</span><span class="sxs-lookup"><span data-stu-id="aef59-112">Policies</span></span>  
  
-   <span data-ttu-id="aef59-113">アドホック ファイル (Readme ファイルなど)</span><span class="sxs-lookup"><span data-stu-id="aef59-113">Ad hoc files, such as Readme files</span></span>  
  
-   <span data-ttu-id="aef59-114">仮想ディレクトリ</span><span class="sxs-lookup"><span data-stu-id="aef59-114">Virtual directories</span></span>  
  
-   <span data-ttu-id="aef59-115">BAM アイテム</span><span class="sxs-lookup"><span data-stu-id="aef59-115">BAM artifacts</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aef59-116">送信ポート、送信ポート グループ、受信場所、および受信ポートはファイルベースのアイテムではないため、アプリケーションに追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="aef59-116">Send ports, send port groups, receive locations, and receive ports are not file-based artifacts and cannot be added to an application.</span></span> <span data-ttu-id="aef59-117">これらのアイテムは、特定のアプリケーションで作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aef59-117">You must create these artifacts within a given application.</span></span> <span data-ttu-id="aef59-118">作成後に、必要に応じて他のアプリケーションに移動することができます。</span><span class="sxs-lookup"><span data-stu-id="aef59-118">You can then move them to a different application, if you want.</span></span> <span data-ttu-id="aef59-119">オーケストレーション、スキーマ、マップ、およびパイプラインは、これらを含むアセンブリの一部として、展開および管理します。</span><span class="sxs-lookup"><span data-stu-id="aef59-119">Orchestrations, schemas, maps and pipelines are all deployed and managed as part of the assemblies that contain them.</span></span>  
  
 <span data-ttu-id="aef59-120">アイテムをアプリケーションに追加すると、そのアイテムは BizTalk 管理データベースのアプリケーションに関連付けられ、アイテムのファイル ベースのデータも管理データベースに追加されます。</span><span class="sxs-lookup"><span data-stu-id="aef59-120">When you add an artifact to an application, the artifact is associated with the application in the BizTalk Management database, and file-based data for the artifact is added to the Management database as well.</span></span> <span data-ttu-id="aef59-121">これにより、アプリケーションとそのアイテムのデータを管理データベースから .msi ファイルにエクスポートし、そのファイルを他の BizTalk グループの管理データベースにインポートするだけで、アプリケーションおよびアイテムを移動できます。</span><span class="sxs-lookup"><span data-stu-id="aef59-121">This allows you to easily transport applications and artifacts from one BizTalk group to another because you can export the application and the data for its artifacts into an .msi file from the Management database, and then import it into a Management database in a different BizTalk group.</span></span>  
  
 <span data-ttu-id="aef59-122">アプリケーションにバインド ファイルを追加する場合は、バインドを適用する対象の展開環境を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="aef59-122">When you add a binding file to an application, you can specify the target deployment environment in which you want the bindings to be applied.</span></span> <span data-ttu-id="aef59-123">バインド ファイルのインポートとは異なり、バインド ファイルを追加しても、そのバインドは適用されません。</span><span class="sxs-lookup"><span data-stu-id="aef59-123">Unlike importing a binding file, when you add a binding file, its bindings are not applied.</span></span>  
  
 <span data-ttu-id="aef59-124">BizTalk アセンブリまたは .NET アセンブリをアプリケーションに追加する場合は、このオプションを選択すると、アセンブリがグローバル アセンブリ キャッシュに追加されます。</span><span class="sxs-lookup"><span data-stu-id="aef59-124">When you add a BizTalk assembly or a .NET assembly to an application, the assembly is added to the global assembly cache if you specify this option.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aef59-125">参照</span><span class="sxs-lookup"><span data-stu-id="aef59-125">See Also</span></span>  
 <span data-ttu-id="aef59-126">[アプリケーションの展開時の成果物を処理します。](../core/what-happens-to-artifacts-during-application-deployment.md) </span><span class="sxs-lookup"><span data-stu-id="aef59-126">[What Happens to Artifacts During Application Deployment](../core/what-happens-to-artifacts-during-application-deployment.md) </span></span>  
 <span data-ttu-id="aef59-127">[成果物を追加または作成する方法](../core/how-to-create-or-add-an-artifact.md) </span><span class="sxs-lookup"><span data-stu-id="aef59-127">[How to Create or Add an Artifact](../core/how-to-create-or-add-an-artifact.md) </span></span>  
 <span data-ttu-id="aef59-128">[BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md) </span><span class="sxs-lookup"><span data-stu-id="aef59-128">[How to Import a BizTalk Application](../core/how-to-import-a-biztalk-application.md) </span></span>  
 [<span data-ttu-id="aef59-129">BizTalk アプリケーションをエクスポートする方法</span><span class="sxs-lookup"><span data-stu-id="aef59-129">How to Export a BizTalk Application</span></span>](../core/how-to-export-a-biztalk-application.md)