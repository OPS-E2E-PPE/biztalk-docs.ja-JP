---
title: "ポートと Assemblies1 展開 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ports, deploying
- deployment, ports
- deployment, assemblies
- assemblies, deploying
ms.assetid: e259f7fe-c443-4015-a630-f08220e5437a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf2515cd5ee80f62a55e0b26b33bb93c3685ce6b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="deploying-ports-and-assemblies"></a><span data-ttu-id="abf4d-102">ポートとアセンブリの展開</span><span class="sxs-lookup"><span data-stu-id="abf4d-102">Deploying Ports and Assemblies</span></span>
<span data-ttu-id="abf4d-103">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用して、ターゲット コンピューター上でポートとアセンブリを複製できます。</span><span class="sxs-lookup"><span data-stu-id="abf4d-103">Using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can duplicate ports and assemblies on a target computer.</span></span> <span data-ttu-id="abf4d-104">ウィザードにより、送信ポートおよび受信場所の構成が XML ファイルにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="abf4d-104">The wizard exports the send ports/receive location configuration into an XML file.</span></span>  
  
 <span data-ttu-id="abf4d-105">BizTalk Server を使用すると、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="abf4d-105">You use BizTalk Server to do the following tasks:</span></span>  
  
-   <span data-ttu-id="abf4d-106">BizTalk 構成データベース内での、BizTalk Server アセンブリの展開または削除</span><span class="sxs-lookup"><span data-stu-id="abf4d-106">Deploy or remove BizTalk Server assemblies in a BizTalk Configuration database.</span></span>  
  
-   <span data-ttu-id="abf4d-107">グローバル アセンブリ キャッシュ (GAC) 内での、アセンブリのインストールまたはアンインストール</span><span class="sxs-lookup"><span data-stu-id="abf4d-107">Install or uninstall the assemblies in the global assembly cache (GAC).</span></span>  
  
-   <span data-ttu-id="abf4d-108">バインド ファイルに対する、BizTalk Server アセンブリのバインド情報のインポートまたはエクスポート</span><span class="sxs-lookup"><span data-stu-id="abf4d-108">Import or export BizTalk Server assembly binding information to and from binding files.</span></span>  
  
 <span data-ttu-id="abf4d-109">使用する方法については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ポートとアセンブリを展開するを参照してください。 [BizTalk アプリケーションのバインドのエクスポート方法](../core/how-to-export-bindings-for-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="abf4d-109">For information about how to use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to deploy ports and assemblies, see [How to Export Bindings for a BizTalk Application](../core/how-to-export-bindings-for-a-biztalk-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="abf4d-110">Microsoft BizTalk Adapter for TIBCO Rendezvous の場合のみ、ソース (開発) コンピューターで Visual Studio が必要です。</span><span class="sxs-lookup"><span data-stu-id="abf4d-110">Microsoft BizTalk Adapter for TIBCO Rendezvous only requires that you have Visual Studio on a source (development) computer.</span></span> <span data-ttu-id="abf4d-111">実稼動コンピュータでは Visual Studio は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="abf4d-111">Visual Studio is not required on the production computer.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="abf4d-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="abf4d-112">In This Section</span></span>  
  
-   [<span data-ttu-id="abf4d-113">展開セットアップの確認</span><span class="sxs-lookup"><span data-stu-id="abf4d-113">Verifying the Deployment Setup</span></span>](../core/verifying-the-deployment-setup3.md)  
  
-   [<span data-ttu-id="abf4d-114">対象となるコンピューターをクリーニングする方法</span><span class="sxs-lookup"><span data-stu-id="abf4d-114">How to Clean the Target Computer</span></span>](../core/how-to-clean-the-target-computer1.md)