---
title: BizTalk アセンブリ ビューアーを使用したアセンブリの表示 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9831eb88-84bc-4d18-8174-43c3baab83fe
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f548bca847aba8e15cd464a6699f894e15fe8d65
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243183"
---
# <a name="viewing-assemblies-with-the-biztalk-assembly-viewer"></a><span data-ttu-id="c3bb9-102">BizTalk アセンブリ ビューアーを使用したアセンブリの表示</span><span class="sxs-lookup"><span data-stu-id="c3bb9-102">Viewing Assemblies with the BizTalk Assembly Viewer</span></span>
<span data-ttu-id="c3bb9-103">アプリケーションの開発時やアセンブリの展開時には、どのアセンブリが展開されていて使用可能であるかを表示できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3bb9-103">When you are developing applications or deploying assemblies, you need to see which assemblies are deployed and available to you.</span></span> <span data-ttu-id="c3bb9-104">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] には、このための便利なツールとして BizTalk アセンブリ ビューアーが用意されています。</span><span class="sxs-lookup"><span data-stu-id="c3bb9-104">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] provides a convenient tool for this purpose - BizTalk Assembly Viewer.</span></span>  
  
 <span data-ttu-id="c3bb9-105">BizTalk アセンブリ ビューアーは、展開された BizTalk アセンブリとその種類を確認するための Windows シェル拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="c3bb9-105">The BizTalk Assembly Viewer is a Windows shell extension for examining deployed BizTalk assemblies and assembly types.</span></span> <span data-ttu-id="c3bb9-106">BizTalk アセンブリ ビューアーを使用すると、次のことが可能です。</span><span class="sxs-lookup"><span data-stu-id="c3bb9-106">BizTalk Assembly Viewer enables you to:</span></span>  
  
-   <span data-ttu-id="c3bb9-107">ローカル コンピューターのグローバル アセンブリ キャッシュ (GAC) にインストールされているすべての BizTalk Server アセンブリの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="c3bb9-107">View a list of all BizTalk Server assemblies installed in the global assembly cache (GAC) on your local computer.</span></span>  
  
-   <span data-ttu-id="c3bb9-108">BizTalk Server アセンブリ内にある種類を表示します。</span><span class="sxs-lookup"><span data-stu-id="c3bb9-108">View the types within a BizTalk Server assembly.</span></span>  
  
-   <span data-ttu-id="c3bb9-109">名前、バージョン、カルチャ、コード ベース、公開キー トークンなど、BizTalk Server アセンブリの属性を表示します。</span><span class="sxs-lookup"><span data-stu-id="c3bb9-109">View attributes of a BizTalk Server assembly, such as name, version, culture, code base, and public key token.</span></span>  
  
-   <span data-ttu-id="c3bb9-110">BizTalk Server アセンブリの参照アセンブリを表示します。</span><span class="sxs-lookup"><span data-stu-id="c3bb9-110">View referenced assemblies for a BizTalk Server assembly.</span></span>  
  
-   <span data-ttu-id="c3bb9-111">GAC にアセンブリを追加します。</span><span class="sxs-lookup"><span data-stu-id="c3bb9-111">Add assemblies in the GAC.</span></span>  
  
-   <span data-ttu-id="c3bb9-112">GAC からアセンブリを削除します。</span><span class="sxs-lookup"><span data-stu-id="c3bb9-112">Remove assemblies from the GAC.</span></span>  
  
-   <span data-ttu-id="c3bb9-113">スキーマ、マップ、オーケストレーション、パイプラインなど、さまざまな種類の XML コードを表示します。</span><span class="sxs-lookup"><span data-stu-id="c3bb9-113">View the XML code for various types including schemas, maps, orchestrations, and pipelines.</span></span>  
  
-   <span data-ttu-id="c3bb9-114">指定したサーバーに展開されているすべての BizTalk Server アセンブリから特定の種類を検索します。</span><span class="sxs-lookup"><span data-stu-id="c3bb9-114">Search for particular types across all BizTalk Server assemblies deployed on a given server.</span></span>  
  
-   <span data-ttu-id="c3bb9-115">BizTalk Server アセンブリ間の種類の依存関係を検索します。</span><span class="sxs-lookup"><span data-stu-id="c3bb9-115">Search type dependencies across BizTalk Server assemblies.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c3bb9-116">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c3bb9-116">In This Section</span></span>  
  
-   [<span data-ttu-id="c3bb9-117">登録および BizTalk アセンブリ ビューアーを削除する方法</span><span class="sxs-lookup"><span data-stu-id="c3bb9-117">How to Register and Remove the BizTalk Assembly Viewer</span></span>](../core/how-to-register-and-remove-the-biztalk-assembly-viewer.md)  
  
-   [<span data-ttu-id="c3bb9-118">ローカル サーバーにアセンブリおよび型を表示する方法</span><span class="sxs-lookup"><span data-stu-id="c3bb9-118">How to View Assemblies and Types on the Local Server</span></span>](../core/how-to-view-assemblies-and-types-on-the-local-server.md)