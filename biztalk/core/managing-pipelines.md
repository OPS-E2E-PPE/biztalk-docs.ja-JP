---
title: "パイプラインの管理 |Microsoft ドキュメント"
description: "追跡や送信ポートのパイプライン プロパティを有効にするにまたは BizTalk Server で受信場所へのクイック リンク"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d60b54e0-0a5a-4264-b0e5-96bb187d782b
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0edfbdd97e134abc6f153acf136ff62a979f8b0c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="managing-pipelines"></a><span data-ttu-id="81e10-103">パイプラインの管理</span><span class="sxs-lookup"><span data-stu-id="81e10-103">Managing Pipelines</span></span>

## <a name="overview"></a><span data-ttu-id="81e10-104">概要</span><span class="sxs-lookup"><span data-stu-id="81e10-104">Overview</span></span>
<span data-ttu-id="81e10-105">ここでは、BizTalk Server 管理コンソールを使用して BizTalk グループのパイプラインを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="81e10-105">This section provides instructions on using the BizTalk Server Administration console to manage the pipelines in a BizTalk group.</span></span> <span data-ttu-id="81e10-106">特定の送信ポートまたは受信場所のパイプライン プロパティの構成に加え、イベントおよびメッセージの追跡を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="81e10-106">You can configure tracking for events and messages as well as configure pipeline properties for a specific send port or receive location.</span></span>  
  
 <span data-ttu-id="81e10-107">パイプラインでは、受信メッセージおよび送信メッセージに対して、ネイティブ形式から XML への変換、データの暗号化や復号化、プロパティの昇格などの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="81e10-107">Pipelines perform actions on incoming and outgoing messages, such as transforming them from a native format into XML, encrypting or unencrypting data, performing property promotion, and so on.</span></span>  
  
 <span data-ttu-id="81e10-108">パイプラインを単独でアプリケーションに追加することはできません。パイプラインは次のようにしてアプリケーションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="81e10-108">You cannot add a pipeline to an application individually; a pipeline is added to an application as follows:</span></span>  
  
-   <span data-ttu-id="81e10-109">」の説明に従って、アプリケーションに、パイプラインを含む BizTalk アセンブリを追加すると[BizTalk アセンブリをアプリケーションに追加する方法](../core/how-to-add-a-biztalk-assembly-to-an-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="81e10-109">When you add a BizTalk assembly containing a pipeline to the application, as described in [How to Add a BizTalk Assembly to an Application](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span></span>  
  
-   <span data-ttu-id="81e10-110">」の説明に従って、パイプラインを含む BizTalk アセンブリを含むアプリケーションを .msi ファイルをインポートしたとき[を BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="81e10-110">When you import an .msi file into an application that includes a BizTalk assembly containing a pipeline, as described in [How to Import a BizTalk Application](../core/how-to-import-a-biztalk-application.md).</span></span>  
  
-   <span data-ttu-id="81e10-111">開発者が展開したときのアプリケーションに、Visual Studio からパイプラインを含むアセンブリ」の説明に従って[BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開する](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="81e10-111">When a developer deploys into an application an assembly containing a pipeline from Visual Studio, as described in [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).</span></span>  
  
 <span data-ttu-id="81e10-112">パイプラインに関する背景情報については、次を参照してください。[パイプライン](../core/pipelines.md)です。</span><span class="sxs-lookup"><span data-stu-id="81e10-112">For background information about pipelines, see [Pipelines](../core/pipelines.md).</span></span> <span data-ttu-id="81e10-113">パイプラインの開発方法の詳細については、次を参照してください。[パイプライン デザイナーを使用してパイプラインを作成する](../core/creating-pipelines-using-pipeline-designer.md)です。</span><span class="sxs-lookup"><span data-stu-id="81e10-113">For information about developing pipelines, see [Creating Pipelines Using Pipeline Designer](../core/creating-pipelines-using-pipeline-designer.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="81e10-114">Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。</span><span class="sxs-lookup"><span data-stu-id="81e10-114">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="81e10-115">WMI の使用については、次を参照してください。、 **WMI クラス参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="81e10-115">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="81e10-116">次の手順</span><span class="sxs-lookup"><span data-stu-id="81e10-116">Next steps</span></span>
  
-   [<span data-ttu-id="81e10-117">パイプラインの追跡を構成します。</span><span class="sxs-lookup"><span data-stu-id="81e10-117">Configure Tracking for a Pipeline</span></span>](../core/how-to-configure-tracking-for-a-pipeline.md)  
  
-   [<span data-ttu-id="81e10-118">送信ポートのインスタンスごとにパイプライン プロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="81e10-118">Configure Per-Instance Pipeline Properties for a Send Port</span></span>](../core/how-to-configure-per-instance-pipeline-properties-for-a-send-port.md)  
  
-   [<span data-ttu-id="81e10-119">インスタンスごとのパイプライン プロパティを構成する受信場所</span><span class="sxs-lookup"><span data-stu-id="81e10-119">Configure Per-instance Pipeline Properties for a Receive Location</span></span>](../core/how-to-configure-per-instance-pipeline-properties-for-a-receive-location.md)