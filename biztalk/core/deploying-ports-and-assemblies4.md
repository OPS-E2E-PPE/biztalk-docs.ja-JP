---
title: "ポートと Assemblies4 展開 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying assemblies
- ports, deploying
- Deployment Wizard
- deploying ports
- assemblies, deploying
- deployment, ports and assemblies
ms.assetid: 5a94a2c8-748c-4d1c-a87e-1cd763565886
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b83df400cba64ee55cab230826bf5bf75b1bca69
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="deploying-ports-and-assemblies"></a><span data-ttu-id="d36ee-102">ポートとアセンブリの展開</span><span class="sxs-lookup"><span data-stu-id="d36ee-102">Deploying Ports and Assemblies</span></span>
<span data-ttu-id="d36ee-103">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用して、ターゲット コンピューター上でポートとアセンブリを複製できます。</span><span class="sxs-lookup"><span data-stu-id="d36ee-103">Using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can duplicate ports and assemblies on a target computer.</span></span> <span data-ttu-id="d36ee-104">BizTalk Server により、送信ポートおよび受信場所の構成が XML ファイルにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="d36ee-104">BizTalk Server exports the send ports/receive location configuration into an XML file.</span></span>  
  
 <span data-ttu-id="d36ee-105">BizTalk Server を使用すると、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="d36ee-105">You can use BizTalk Server to do the following tasks:</span></span>  
  
-   <span data-ttu-id="d36ee-106">BizTalk 構成データベース内の BizTalk Server アセンブリを展開または削除する</span><span class="sxs-lookup"><span data-stu-id="d36ee-106">Deploy or remove BizTalk Server assemblies in a BizTalk Configuration database</span></span>  
  
-   <span data-ttu-id="d36ee-107">グローバル アセンブリ キャッシュ (GAC) にアセンブリをインストールまたはアンインストールする</span><span class="sxs-lookup"><span data-stu-id="d36ee-107">Install or uninstall the assemblies in the global assembly cache (GAC)</span></span>  
  
-   <span data-ttu-id="d36ee-108">BizTalk Server アセンブリのバインド情報をバインド ファイルからインポートする、またはバインド ファイルにエクスポートする</span><span class="sxs-lookup"><span data-stu-id="d36ee-108">Import or export BizTalk Server assembly binding information to and from binding files</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d36ee-109">Microsoft BizTalk Adapter for JD Edwards OneWorld の場合のみ、ソース (開発) コンピューターで Visual Studio が必要です。</span><span class="sxs-lookup"><span data-stu-id="d36ee-109">The Microsoft BizTalk Adapter for JD Edwards OneWorld only requires that you have Visual Studio on a source (development) computer.</span></span> <span data-ttu-id="d36ee-110">実稼動コンピュータでは Visual Studio は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="d36ee-110">Visual Studio is not required on the production computer.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d36ee-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d36ee-111">In This Section</span></span>  
  
-   [<span data-ttu-id="d36ee-112">バインド ファイルのインポート</span><span class="sxs-lookup"><span data-stu-id="d36ee-112">Importing Binding Files</span></span>](../core/importing-binding-files3.md)  
  
-   [<span data-ttu-id="d36ee-113">展開の制限事項</span><span class="sxs-lookup"><span data-stu-id="d36ee-113">Deployment Limitations</span></span>](../core/deployment-limitations2.md)