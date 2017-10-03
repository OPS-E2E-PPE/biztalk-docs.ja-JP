---
title: "ポートと Assemblies5 展開 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ports, deploying
- assemblies, deploying
- deployment, ports and assemblies
ms.assetid: 11d980c4-2502-4da2-b505-d7326aae619a
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 31df94e2a659fa29e6f21d2bd705de31da3c6b9a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="deploying-ports-and-assemblies"></a><span data-ttu-id="c8a2d-102">ポートとアセンブリの展開</span><span class="sxs-lookup"><span data-stu-id="c8a2d-102">Deploying Ports and Assemblies</span></span>
<span data-ttu-id="c8a2d-103">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用して、ターゲット コンピューター上でポートとアセンブリを複製できます。</span><span class="sxs-lookup"><span data-stu-id="c8a2d-103">Using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can duplicate ports and assemblies on a target computer.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="c8a2d-104"> により、送信ポートおよび受信場所の構成が XML ファイルにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="c8a2d-104"> exports the send ports/receive location configuration into an XML file.</span></span>  
  
 <span data-ttu-id="c8a2d-105">使用する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]これらのタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="c8a2d-105">You use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to perform these tasks:</span></span>  
  
-   <span data-ttu-id="c8a2d-106">BizTalk 構成データベースで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アセンブリを展開または削除します。</span><span class="sxs-lookup"><span data-stu-id="c8a2d-106">Deploy or remove [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] assemblies in a BizTalk Configuration database.</span></span>  
  
-   <span data-ttu-id="c8a2d-107">グローバル アセンブリ キャッシュ (GAC) 内での、アセンブリのインストールまたはアンインストール</span><span class="sxs-lookup"><span data-stu-id="c8a2d-107">Install or uninstall the assemblies in the global assembly cache (GAC).</span></span>  
  
-   <span data-ttu-id="c8a2d-108">バインド ファイルに対する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アセンブリのバインド情報のインポートまたはエクスポート</span><span class="sxs-lookup"><span data-stu-id="c8a2d-108">Import or export [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] assembly binding information to and from binding files.</span></span>  
  
 <span data-ttu-id="c8a2d-109">使用する方法については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ポートとアセンブリを展開するを参照してください。 [BizTalk アプリケーションのバインドのエクスポート方法](../core/how-to-export-bindings-for-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="c8a2d-109">For information about how to use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to deploy ports and assemblies, see [How to Export Bindings for a BizTalk Application](../core/how-to-export-bindings-for-a-biztalk-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c8a2d-110">Microsoft BizTalk Adapter for PeopleSoft Enterprise の場合のみ、ソース (開発) コンピューターで Visual Studio が必要です。</span><span class="sxs-lookup"><span data-stu-id="c8a2d-110">The Microsoft BizTalk Adapter for PeopleSoft Enterprise only requires that you have Visual Studio on a source (development) computer.</span></span> <span data-ttu-id="c8a2d-111">実稼動コンピュータでは Visual Studio は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="c8a2d-111">Visual Studio is not required on the production computer.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c8a2d-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c8a2d-112">In This Section</span></span>  
  
-   [<span data-ttu-id="c8a2d-113">バインド ファイルのインポート</span><span class="sxs-lookup"><span data-stu-id="c8a2d-113">Importing Binding Files</span></span>](../core/importing-binding-files1.md)  
  
-   [<span data-ttu-id="c8a2d-114">展開の制限事項</span><span class="sxs-lookup"><span data-stu-id="c8a2d-114">Deployment Limitations</span></span>](../core/deployment-limitations3.md)