---
title: "ポートと Assemblies2 展開 |Microsoft ドキュメント"
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
ms.assetid: abbc1391-2b90-42a5-a747-416bc517bb39
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74c3cc840b9dca222d1b55e9277b1ffd6cf326db
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="deploying-ports-and-assemblies"></a><span data-ttu-id="4e498-102">ポートとアセンブリの展開</span><span class="sxs-lookup"><span data-stu-id="4e498-102">Deploying Ports and Assemblies</span></span>
<span data-ttu-id="4e498-103">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ポートとターゲット コンピューター上のアセンブリを複製することができます。</span><span class="sxs-lookup"><span data-stu-id="4e498-103">With [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can duplicate ports and assemblies on a target computer.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="4e498-104">エクスポートは、ポートおよび受信場所の構成を XML ファイルに送信します。</span><span class="sxs-lookup"><span data-stu-id="4e498-104"> exports send ports/receive location configuration into an XML file.</span></span>  
  
 <span data-ttu-id="4e498-105">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用すると、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="4e498-105">You can use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to do the following tasks:</span></span>  
  
-   <span data-ttu-id="4e498-106">BizTalk 構成データベースで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アセンブリを展開または削除します。</span><span class="sxs-lookup"><span data-stu-id="4e498-106">Deploy or remove [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] assemblies in a BizTalk Configuration database.</span></span>  
  
-   <span data-ttu-id="4e498-107">グローバル アセンブリ キャッシュ (GAC) 内での、アセンブリのインストールまたはアンインストール</span><span class="sxs-lookup"><span data-stu-id="4e498-107">Install or uninstall the assemblies in the global assembly cache (GAC).</span></span>  
  
-   <span data-ttu-id="4e498-108">バインド ファイルに対する、BizTalk アセンブリのバインド情報のインポートまたはエクスポート</span><span class="sxs-lookup"><span data-stu-id="4e498-108">Import or export BizTalk assembly binding information to and from binding files.</span></span>  
  
 <span data-ttu-id="4e498-109">使用する方法については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ポートとアセンブリを展開するを参照してください。 [BizTalk アプリケーションのバインドのエクスポート方法](../core/how-to-export-bindings-for-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="4e498-109">For information about how to use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to deploy ports and assemblies, see [How to Export Bindings for a BizTalk Application](../core/how-to-export-bindings-for-a-biztalk-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4e498-110">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service の場合のみ、ソース (開発) コンピューターに Visual Studio がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e498-110">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service only requires that you have Visual Studio on a source (development) computer.</span></span> <span data-ttu-id="4e498-111">実稼動コンピュータでは Visual Studio は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="4e498-111">Visual Studio is not required on the production computer.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4e498-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="4e498-112">In This Section</span></span>  
  
-   [<span data-ttu-id="4e498-113">展開セットアップの確認</span><span class="sxs-lookup"><span data-stu-id="4e498-113">Verifying the Deployment Setup</span></span>](../core/verifying-the-deployment-setup2.md)  
  
-   [<span data-ttu-id="4e498-114">対象となるコンピューターをクリーニングする方法</span><span class="sxs-lookup"><span data-stu-id="4e498-114">How to Clean the Target Computer</span></span>](../core/how-to-clean-the-target-computer2.md)  
  
-   [<span data-ttu-id="4e498-115">展開の制限事項</span><span class="sxs-lookup"><span data-stu-id="4e498-115">Deployment Limitations</span></span>](../core/deployment-limitations1.md)