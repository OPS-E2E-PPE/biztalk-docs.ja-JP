---
title: 例外管理フレームワークを使用して |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b69c9c01-e7e4-4788-8fe2-43d32075155d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47442604831a3a11bb9d00b65f9dc34961de2367
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295186"
---
# <a name="using-the-exception-management-framework"></a><span data-ttu-id="2f0be-102">例外管理フレームワークを使用します。</span><span class="sxs-lookup"><span data-stu-id="2f0be-102">Using the Exception Management Framework</span></span>
<span data-ttu-id="2f0be-103">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]動的変換およびルーティングの障害 (たとえば、展開されていないマップまたはマップ名を返さないルール) を通信するために例外を使用します。</span><span class="sxs-lookup"><span data-stu-id="2f0be-103">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] uses exceptions to communicate failures (for example, a non-deployed map or rules that do not return a map name) for dynamic transformations and routing.</span></span> <span data-ttu-id="2f0be-104">変換またはルーティング プロセスが失敗したときに、ESB は、例外メッセージを作成し、メッセージ ボックス データベースに直接バインド ポートを通じて送信します。</span><span class="sxs-lookup"><span data-stu-id="2f0be-104">When a transformation or routing process fails, the ESB creates an exception message and submits it through a direct-bound port to the Message Box database.</span></span> <span data-ttu-id="2f0be-105">ESB は、ALL という名前の送信ポートも実装します。サブスクライブしている、例外メッセージを取得して ESB 管理ポータルに公開される例外。</span><span class="sxs-lookup"><span data-stu-id="2f0be-105">The ESB also implements a send port named ALL.Exceptions that subscribes to and retrieves exception messages and publishes them to the ESB Management Portal.</span></span>  
  
 <span data-ttu-id="2f0be-106">さらに、すべてのオーケストレーション サンプル、ESB に失敗しましたオーケストレーション例外ルーティング API を使用して例外を処理します。</span><span class="sxs-lookup"><span data-stu-id="2f0be-106">In addition, all orchestration samples use the ESB Failed Orchestration Exception Routing API to handle exceptions.</span></span> <span data-ttu-id="2f0be-107">この API は、展開するすべてのオーケストレーション プロジェクトで使用できます。</span><span class="sxs-lookup"><span data-stu-id="2f0be-107">You can use this API in any orchestration project you deploy.</span></span> <span data-ttu-id="2f0be-108">ESB 失敗オーケストレーション例外ルーティング機能は、トラップして、BizTalk Server 環境のすべての例外を報告する標準的な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="2f0be-108">The ESB Failed Orchestration Exception Routing feature provides a standard way to trap and report all exceptions in a BizTalk Server environment.</span></span>  
  
 <span data-ttu-id="2f0be-109">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ESB 例外管理フレームワークを使用する方法を示すいくつかのサンプル プロジェクトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2f0be-109">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] contains several sample projects that demonstrate how to use the ESB Exception Management Framework.</span></span> <span data-ttu-id="2f0be-110">次の 2 つのプロジェクトは、ESB 失敗オーケストレーション例外ルーティング API をカプセル化します。</span><span class="sxs-lookup"><span data-stu-id="2f0be-110">The following two projects encapsulate the ESB Failed Orchestration Exception Routing API:</span></span>  
  
-   <span data-ttu-id="2f0be-111">**ESB です。ExceptionHandling**です。</span><span class="sxs-lookup"><span data-stu-id="2f0be-111">**ESB.ExceptionHandling**.</span></span> <span data-ttu-id="2f0be-112">このプロジェクトには、オーケストレーションでメッセージ処理のエラーを処理するためのすべてのパブリック メソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2f0be-112">This project contains all the public methods for handling fault message processing in orchestrations.</span></span> <span data-ttu-id="2f0be-113">ローカル サーバー上のグローバル アセンブリ キャッシュ内のこのプロジェクトにアセンブリを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f0be-113">You must register the assembly in this project in the global assembly cache on the local server.</span></span>  
  
-   <span data-ttu-id="2f0be-114">**ESB です。ExceptionHandling.Schemas.Faults**です。</span><span class="sxs-lookup"><span data-stu-id="2f0be-114">**ESB.ExceptionHandling.Schemas.Faults**.</span></span> <span data-ttu-id="2f0be-115">このプロジェクトには、名前空間で定義されているエラー メッセージのスキーマが含まれています。 **http://schemas.microsoft.biztalk.practices.esb.com/exceptionhandling**とシステム プロパティ スキーマです。</span><span class="sxs-lookup"><span data-stu-id="2f0be-115">This project contains the fault message schema defined by the namespace **http://schemas.microsoft.biztalk.practices.esb.com/exceptionhandling** and the system property schema.</span></span> <span data-ttu-id="2f0be-116">このプロジェクトは、Microsoft.Practices.ESB アプリケーション コンテナーを配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f0be-116">You must deploy this project to the Microsoft.Practices.ESB application container.</span></span>  
  
 <span data-ttu-id="2f0be-117">ESB 失敗オーケストレーション例外ルーティング API を使用するすべてのプロジェクトには、コア アセンブリを参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f0be-117">All projects that use the ESB Failed Orchestration Exception Routing API must reference the core assemblies:</span></span>  
  
-   <span data-ttu-id="2f0be-118">**Microsoft.Practices.ESB.ExceptionHandling.dll**</span><span class="sxs-lookup"><span data-stu-id="2f0be-118">**Microsoft.Practices.ESB.ExceptionHandling.dll**</span></span>  
  
-   <span data-ttu-id="2f0be-119">**Microsoft.Practices.ESB.ExceptionHandling.Schemas.Faults.dll**</span><span class="sxs-lookup"><span data-stu-id="2f0be-119">**Microsoft.Practices.ESB.ExceptionHandling.Schemas.Faults.dll**</span></span>  
  
 <span data-ttu-id="2f0be-120">以下のセクションでは、ESB 例外管理フレームワークを使用してについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="2f0be-120">The following sections provide more information about using the ESB Exception Management Framework:</span></span>  
  
-   [<span data-ttu-id="2f0be-121">ESB 例外 API メンバー</span><span class="sxs-lookup"><span data-stu-id="2f0be-121">The ESB Exception API Members</span></span>](../esb-toolkit/the-esb-exception-api-members.md)  
  
-   [<span data-ttu-id="2f0be-122">作成、およびエラー メッセージの公開</span><span class="sxs-lookup"><span data-stu-id="2f0be-122">Creating and Publishing Fault Messages</span></span>](../esb-toolkit/creating-and-publishing-fault-messages.md)  
  
-   [<span data-ttu-id="2f0be-123">サブスクライブおよびメッセージの抽出</span><span class="sxs-lookup"><span data-stu-id="2f0be-123">Subscribing to and Extracting Messages</span></span>](../esb-toolkit/subscribing-to-and-extracting-messages.md)  
  
-   [<span data-ttu-id="2f0be-124">ソリューションのシナリオの手順</span><span class="sxs-lookup"><span data-stu-id="2f0be-124">Scenario Solution Steps</span></span>](../esb-toolkit/scenario-solution-steps.md)