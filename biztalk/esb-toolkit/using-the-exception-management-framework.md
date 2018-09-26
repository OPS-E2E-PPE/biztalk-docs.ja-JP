---
title: 例外管理フレームワークを使用して |Microsoft Docs
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
ms.openlocfilehash: 8146b3f2f9be6d076cfd7dddd651ee2c9bb4d3c6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991531"
---
# <a name="using-the-exception-management-framework"></a><span data-ttu-id="58a57-102">例外管理フレームワークの使用</span><span class="sxs-lookup"><span data-stu-id="58a57-102">Using the Exception Management Framework</span></span>
<span data-ttu-id="58a57-103">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]動的変換およびルーティングの障害 (展開されていないマップまたはマップ名を返さない規則など) の通信に例外を使用します。</span><span class="sxs-lookup"><span data-stu-id="58a57-103">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] uses exceptions to communicate failures (for example, a non-deployed map or rules that do not return a map name) for dynamic transformations and routing.</span></span> <span data-ttu-id="58a57-104">変換またはルーティング プロセスが失敗したときに、ESB は例外メッセージを作成し、メッセージ ボックス データベースに直接バインドされたポートを通じて送信します。</span><span class="sxs-lookup"><span data-stu-id="58a57-104">When a transformation or routing process fails, the ESB creates an exception message and submits it through a direct-bound port to the Message Box database.</span></span> <span data-ttu-id="58a57-105">ESB は、すべてをという名前の送信ポートも実装します。サブスクライブし、例外メッセージを取得し、ESB 管理ポータルに公開する例外です。</span><span class="sxs-lookup"><span data-stu-id="58a57-105">The ESB also implements a send port named ALL.Exceptions that subscribes to and retrieves exception messages and publishes them to the ESB Management Portal.</span></span>  

 <span data-ttu-id="58a57-106">さらに、すべてのオーケストレーション サンプル、ESB に失敗しましたオーケストレーション例外ルーティング API を使用して例外を処理します。</span><span class="sxs-lookup"><span data-stu-id="58a57-106">In addition, all orchestration samples use the ESB Failed Orchestration Exception Routing API to handle exceptions.</span></span> <span data-ttu-id="58a57-107">展開するすべてのオーケストレーション プロジェクトでは、この API を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="58a57-107">You can use this API in any orchestration project you deploy.</span></span> <span data-ttu-id="58a57-108">ESB 失敗オーケストレーションの例外ルーティング機能は、BizTalk Server 環境のすべての例外をトラップする標準的な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="58a57-108">The ESB Failed Orchestration Exception Routing feature provides a standard way to trap and report all exceptions in a BizTalk Server environment.</span></span>  

 <span data-ttu-id="58a57-109">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ESB 例外管理フレームワークを使用する方法を示すいくつかのサンプル プロジェクトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="58a57-109">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] contains several sample projects that demonstrate how to use the ESB Exception Management Framework.</span></span> <span data-ttu-id="58a57-110">次の 2 つのプロジェクトは、ESB 失敗オーケストレーションの例外ルーティング API をカプセル化します。</span><span class="sxs-lookup"><span data-stu-id="58a57-110">The following two projects encapsulate the ESB Failed Orchestration Exception Routing API:</span></span>  

- <span data-ttu-id="58a57-111">**ESB します。ExceptionHandling**します。</span><span class="sxs-lookup"><span data-stu-id="58a57-111">**ESB.ExceptionHandling**.</span></span> <span data-ttu-id="58a57-112">このプロジェクトには、オーケストレーションでメッセージ処理のエラーを処理するためのすべてのパブリック メソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="58a57-112">This project contains all the public methods for handling fault message processing in orchestrations.</span></span> <span data-ttu-id="58a57-113">ローカル サーバー上のグローバル アセンブリ キャッシュには、このプロジェクトには、アセンブリを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58a57-113">You must register the assembly in this project in the global assembly cache on the local server.</span></span>  

- <span data-ttu-id="58a57-114">**ESB します。ExceptionHandling.Schemas.Faults**します。</span><span class="sxs-lookup"><span data-stu-id="58a57-114">**ESB.ExceptionHandling.Schemas.Faults**.</span></span> <span data-ttu-id="58a57-115">このプロジェクトには、名前空間で定義されたエラー メッセージのスキーマが含まれている**http://schemas.microsoft.biztalk.practices.esb.com/exceptionhandling**とシステム プロパティのスキーマ。</span><span class="sxs-lookup"><span data-stu-id="58a57-115">This project contains the fault message schema defined by the namespace **http://schemas.microsoft.biztalk.practices.esb.com/exceptionhandling** and the system property schema.</span></span> <span data-ttu-id="58a57-116">このプロジェクトは、Microsoft.Practices.ESB アプリケーション コンテナーをデプロイする必要があります。</span><span class="sxs-lookup"><span data-stu-id="58a57-116">You must deploy this project to the Microsoft.Practices.ESB application container.</span></span>  

  <span data-ttu-id="58a57-117">ESB 失敗オーケストレーションの例外ルーティング API を使用するすべてのプロジェクトでは、コア アセンブリを参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58a57-117">All projects that use the ESB Failed Orchestration Exception Routing API must reference the core assemblies:</span></span>  

- <span data-ttu-id="58a57-118">**Microsoft.Practices.ESB.ExceptionHandling.dll**</span><span class="sxs-lookup"><span data-stu-id="58a57-118">**Microsoft.Practices.ESB.ExceptionHandling.dll**</span></span>  

- <span data-ttu-id="58a57-119">**Microsoft.Practices.ESB.ExceptionHandling.Schemas.Faults.dll**</span><span class="sxs-lookup"><span data-stu-id="58a57-119">**Microsoft.Practices.ESB.ExceptionHandling.Schemas.Faults.dll**</span></span>  

  <span data-ttu-id="58a57-120">次のセクションでは、ESB 例外管理フレームワークの使用の詳細についてを説明します。</span><span class="sxs-lookup"><span data-stu-id="58a57-120">The following sections provide more information about using the ESB Exception Management Framework:</span></span>  

- [<span data-ttu-id="58a57-121">ESB 例外 API メンバー</span><span class="sxs-lookup"><span data-stu-id="58a57-121">The ESB Exception API Members</span></span>](../esb-toolkit/the-esb-exception-api-members.md)  

- [<span data-ttu-id="58a57-122">エラー メッセージを作成し、発行する</span><span class="sxs-lookup"><span data-stu-id="58a57-122">Creating and Publishing Fault Messages</span></span>](../esb-toolkit/creating-and-publishing-fault-messages.md)  

- [<span data-ttu-id="58a57-123">メッセージをサブスクライブし、抽出する</span><span class="sxs-lookup"><span data-stu-id="58a57-123">Subscribing to and Extracting Messages</span></span>](../esb-toolkit/subscribing-to-and-extracting-messages.md)  

- [<span data-ttu-id="58a57-124">シナリオ ソリューションの手順</span><span class="sxs-lookup"><span data-stu-id="58a57-124">Scenario Solution Steps</span></span>](../esb-toolkit/scenario-solution-steps.md)
