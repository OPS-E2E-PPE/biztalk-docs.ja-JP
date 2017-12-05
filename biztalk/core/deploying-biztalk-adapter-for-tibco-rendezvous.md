---
title: "TIBCO Rendezvous のバインドのインポート |Microsoft ドキュメント"
description: "TIBCO Rendezvous を BizTalk Server でバインドのインポート機能を使用してアプリケーションの BizTalk アダプターの展開します。"
ms.custom: 
ms.date: 10/24/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ec5751a9-0a08-4cf8-a3ef-e51e488a4180
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dab62d7d7836a59c66329c2c58f7768bc481c036
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="deploy-tibco-rendezvous-ports-and-assemblies"></a><span data-ttu-id="3b0d4-103">TIBCO Rendezvous ポートとアセンブリを展開します。</span><span class="sxs-lookup"><span data-stu-id="3b0d4-103">Deploy TIBCO Rendezvous ports and assemblies</span></span>
  
## <a name="overview"></a><span data-ttu-id="3b0d4-104">概要</span><span class="sxs-lookup"><span data-stu-id="3b0d4-104">Overview</span></span>
<span data-ttu-id="3b0d4-105">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用して、ターゲット コンピューター上でポートとアセンブリを複製できます。</span><span class="sxs-lookup"><span data-stu-id="3b0d4-105">Using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can duplicate ports and assemblies on a target computer.</span></span> <span data-ttu-id="3b0d4-106">ウィザードにより、送信ポートおよび受信場所の構成が XML ファイルにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="3b0d4-106">The wizard exports the send ports/receive location configuration into an XML file.</span></span>  
  
 <span data-ttu-id="3b0d4-107">BizTalk Server を使用すると、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="3b0d4-107">You use BizTalk Server to do the following tasks:</span></span>  
  
-   <span data-ttu-id="3b0d4-108">BizTalk 構成データベース内での、BizTalk Server アセンブリの展開または削除</span><span class="sxs-lookup"><span data-stu-id="3b0d4-108">Deploy or remove BizTalk Server assemblies in a BizTalk Configuration database.</span></span>  
  
-   <span data-ttu-id="3b0d4-109">グローバル アセンブリ キャッシュ (GAC) 内での、アセンブリのインストールまたはアンインストール</span><span class="sxs-lookup"><span data-stu-id="3b0d4-109">Install or uninstall the assemblies in the global assembly cache (GAC).</span></span>  
  
-   <span data-ttu-id="3b0d4-110">バインド ファイルに対する、BizTalk Server アセンブリのバインド情報のインポートまたはエクスポート</span><span class="sxs-lookup"><span data-stu-id="3b0d4-110">Import or export BizTalk Server assembly binding information to and from binding files.</span></span>  
  
 <span data-ttu-id="3b0d4-111">使用する方法については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ポートとアセンブリを展開するを参照してください。 [BizTalk アプリケーションのバインドのエクスポート方法](../core/how-to-export-bindings-for-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="3b0d4-111">For information about how to use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to deploy ports and assemblies, see [How to Export Bindings for a BizTalk Application](../core/how-to-export-bindings-for-a-biztalk-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3b0d4-112">Microsoft BizTalk Adapter for TIBCO Rendezvous の場合のみ、ソース (開発) コンピューターで Visual Studio が必要です。</span><span class="sxs-lookup"><span data-stu-id="3b0d4-112">Microsoft BizTalk Adapter for TIBCO Rendezvous only requires that you have Visual Studio on a source (development) computer.</span></span> <span data-ttu-id="3b0d4-113">実稼動コンピュータでは Visual Studio は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="3b0d4-113">Visual Studio is not required on the production computer.</span></span>  

## <a name="confirm-your-setup"></a><span data-ttu-id="3b0d4-114">セットアップを確認します。</span><span class="sxs-lookup"><span data-stu-id="3b0d4-114">Confirm your setup</span></span>

<span data-ttu-id="3b0d4-115">使用する前に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]バインド ファイルをインポートすることを確認、応答用のフォルダーが存在することは、新しいコンピューターで同一またはバインド ファイルを編集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b0d4-115">Before you use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to import a binding file, confirm that the folders for the responses exist, and that they are identical on the new computer, or you must edit the binding file.</span></span>  
  
## <a name="clean-the-target-computer"></a><span data-ttu-id="3b0d4-116">ターゲット コンピューターをクリーニングします。</span><span class="sxs-lookup"><span data-stu-id="3b0d4-116">Clean the target computer</span></span>
<span data-ttu-id="3b0d4-117">展開には、受信場所の構成が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="3b0d4-117">Deployment overwrites the receive location configuration.</span></span> <span data-ttu-id="3b0d4-118">バインド ファイル (およびアセンブリ) を展開先のコンピューターに展開すると、送信ポートと受信場所が、インポートされた XML バインド ファイルの送信ポートと受信場所に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="3b0d4-118">When you deploy a binding file (and assembly) on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are imported.</span></span>  
  
<span data-ttu-id="3b0d4-119">インポートすると、前に、送信ポートを削除し、受信場所、オーケストレーションにバインドします。</span><span class="sxs-lookup"><span data-stu-id="3b0d4-119">Before you import, remove send ports and receive locations bound to the orchestration.</span></span>  
  
<span data-ttu-id="3b0d4-120">Microsoft Visual Studio が展開先のコンピューターにインストールされていない場合は、次のスクリプトを実行してポートを削除できます。</span><span class="sxs-lookup"><span data-stu-id="3b0d4-120">If you do not have Microsoft Visual Studio installed on the target computer, you can remove the ports by running these scripts:</span></span>  
  
-   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="3b0d4-121">SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs</span><span class="sxs-lookup"><span data-stu-id="3b0d4-121">SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs</span></span>  
  
-   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="3b0d4-122">SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs</span><span class="sxs-lookup"><span data-stu-id="3b0d4-122">SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs</span></span>  
  
<span data-ttu-id="3b0d4-123">たとえば、コマンド プロンプトで次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="3b0d4-123">For example, at a command prompt, run:</span></span>  
  
```
cscript RemoveSendPort.vbs \<Send port name\>
```
  
## <a name="next-steps"></a><span data-ttu-id="3b0d4-124">次の手順</span><span class="sxs-lookup"><span data-stu-id="3b0d4-124">Next steps</span></span>
[<span data-ttu-id="3b0d4-125">BizTalk Server 例外処理を使用して、オーケストレーションで</span><span class="sxs-lookup"><span data-stu-id="3b0d4-125">Use BizTalk Server Exception Handling in your orchestration</span></span>](../core/using-biztalk-server-exception-handling4.md)  
<span data-ttu-id="3b0d4-126">[[トラブルシューティング]](../core/troubleshooting-tibco-rendezvous.md)</span><span class="sxs-lookup"><span data-stu-id="3b0d4-126">[Troubleshoot](../core/troubleshooting-tibco-rendezvous.md)</span></span>