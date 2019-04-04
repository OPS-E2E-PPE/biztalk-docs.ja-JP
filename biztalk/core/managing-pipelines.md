---
title: パイプラインを管理する |Microsoft Docs
description: 追跡や送信ポートのパイプライン プロパティを有効にするか、BizTalk Server で受信場所へのクイック リンク
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d60b54e0-0a5a-4264-b0e5-96bb187d782b
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b15931468b5ba3bf43f227563dd270aabbfa29b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995259"
---
# <a name="managing-pipelines"></a><span data-ttu-id="e1b5d-103">パイプラインの管理</span><span class="sxs-lookup"><span data-stu-id="e1b5d-103">Managing Pipelines</span></span>

## <a name="overview"></a><span data-ttu-id="e1b5d-104">概要</span><span class="sxs-lookup"><span data-stu-id="e1b5d-104">Overview</span></span>
<span data-ttu-id="e1b5d-105">ここでは、BizTalk Server 管理コンソールを使用して BizTalk グループのパイプラインを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e1b5d-105">This section provides instructions on using the BizTalk Server Administration console to manage the pipelines in a BizTalk group.</span></span> <span data-ttu-id="e1b5d-106">特定の送信ポートまたは受信場所のパイプライン プロパティの構成に加え、イベントおよびメッセージの追跡を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="e1b5d-106">You can configure tracking for events and messages as well as configure pipeline properties for a specific send port or receive location.</span></span>  
  
 <span data-ttu-id="e1b5d-107">パイプラインでは、受信メッセージおよび送信メッセージに対して、ネイティブ形式から XML への変換、データの暗号化や復号化、プロパティの昇格などの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e1b5d-107">Pipelines perform actions on incoming and outgoing messages, such as transforming them from a native format into XML, encrypting or unencrypting data, performing property promotion, and so on.</span></span>  
  
 <span data-ttu-id="e1b5d-108">パイプラインを単独でアプリケーションに追加することはできません。パイプラインは次のようにしてアプリケーションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="e1b5d-108">You cannot add a pipeline to an application individually; a pipeline is added to an application as follows:</span></span>  
  
- <span data-ttu-id="e1b5d-109">」の説明に従って、アプリケーションに、パイプラインを含む BizTalk アセンブリを追加するときに[アプリケーションに BizTalk アセンブリを追加する方法](../core/how-to-add-a-biztalk-assembly-to-an-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="e1b5d-109">When you add a BizTalk assembly containing a pipeline to the application, as described in [How to Add a BizTalk Assembly to an Application](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span></span>  
  
- <span data-ttu-id="e1b5d-110">」の説明に従って、パイプラインを含む BizTalk アセンブリを含むアプリケーションを .msi ファイルをインポートする[BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="e1b5d-110">When you import an .msi file into an application that includes a BizTalk assembly containing a pipeline, as described in [How to Import a BizTalk Application](../core/how-to-import-a-biztalk-application.md).</span></span>  
  
- <span data-ttu-id="e1b5d-111">開発者が展開したとき、アプリケーションに、Visual Studio からのパイプラインを含むアセンブリで説明されている[BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開する](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="e1b5d-111">When a developer deploys into an application an assembly containing a pipeline from Visual Studio, as described in [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).</span></span>  
  
  <span data-ttu-id="e1b5d-112">パイプラインに関する背景情報は、[パイプライン](../core/pipelines.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1b5d-112">For background information about pipelines, see [Pipelines](../core/pipelines.md).</span></span> <span data-ttu-id="e1b5d-113">パイプラインの開発方法の詳細については、[パイプライン デザイナーを使用してパイプラインを作成](../core/creating-pipelines-using-pipeline-designer.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1b5d-113">For information about developing pipelines, see [Creating Pipelines Using Pipeline Designer](../core/creating-pipelines-using-pipeline-designer.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e1b5d-114">Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。</span><span class="sxs-lookup"><span data-stu-id="e1b5d-114">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="e1b5d-115">WMI の使用方法の詳細については、、 **WMI クラスの参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1b5d-115">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="e1b5d-116">次のステップ</span><span class="sxs-lookup"><span data-stu-id="e1b5d-116">Next steps</span></span>
  
-   [<span data-ttu-id="e1b5d-117">パイプラインの追跡を構成する</span><span class="sxs-lookup"><span data-stu-id="e1b5d-117">Configure Tracking for a Pipeline</span></span>](../core/how-to-configure-tracking-for-a-pipeline.md)  
  
-   [<span data-ttu-id="e1b5d-118">送信ポートのインスタンスごとにパイプライン プロパティを構成する</span><span class="sxs-lookup"><span data-stu-id="e1b5d-118">Configure Per-Instance Pipeline Properties for a Send Port</span></span>](../core/how-to-configure-per-instance-pipeline-properties-for-a-send-port.md)  
  
-   [<span data-ttu-id="e1b5d-119">受信場所のインスタンスごとにパイプライン プロパティを構成する</span><span class="sxs-lookup"><span data-stu-id="e1b5d-119">Configure Per-instance Pipeline Properties for a Receive Location</span></span>](../core/how-to-configure-per-instance-pipeline-properties-for-a-receive-location.md)