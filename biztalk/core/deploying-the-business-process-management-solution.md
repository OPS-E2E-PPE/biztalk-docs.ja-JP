---
title: ビジネス プロセス管理ソリューションの展開 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, process management solution tutorial
- process management solution tutorial, deploying
ms.assetid: e033e0cd-0333-4f16-a4a0-eaae9ce98fcc
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0a61048ecb90876b251657f00361c35587a7ec1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239442"
---
# <a name="deploying-the-business-process-management-solution"></a><span data-ttu-id="99650-102">ビジネス プロセス管理ソリューションの展開</span><span class="sxs-lookup"><span data-stu-id="99650-102">Deploying the Business Process Management Solution</span></span>
<span data-ttu-id="99650-103">ビジネス プロセス管理 (BPM) ソリューションは、BizTalk アプリケーションのプロセス マネージャを構築する方法の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="99650-103">The Business Process Management (BPM) solution shows one way to construct a process manager in a BizTalk application.</span></span> <span data-ttu-id="99650-104">このソリューションでは、1 つのコンポーネントを使用して、注文処理に含まれる一連のステージを選択および制御します。</span><span class="sxs-lookup"><span data-stu-id="99650-104">The solution uses a component to select and control the sequence of stages in order processing.</span></span> <span data-ttu-id="99650-105">ソリューションが注文を取得: 新しいサービス、アップグレード、またはサービスの終了の可能性もあります-ログの記録、および処理するため渡す前に、順序を確認します。</span><span class="sxs-lookup"><span data-stu-id="99650-105">The solution takes an order—which may be for a new service, an upgrade, or termination of service—logs it, and acknowledges the order before passing it on for processing.</span></span> <span data-ttu-id="99650-106">注文処理は、注文を扱う 1 つ以上のステージで構成されます。</span><span class="sxs-lookup"><span data-stu-id="99650-106">The processing consists of one or more stages that handle the order.</span></span> <span data-ttu-id="99650-107">処理が終わったら、元の注文要求に応答を返します。</span><span class="sxs-lookup"><span data-stu-id="99650-107">Finally, the solution returns a response to the original order request.</span></span>  
  
 <span data-ttu-id="99650-108">この展開ガイドでは、開発用コンピュータおよび複数の実稼働サーバーにビジネス プロセス管理ソリューションをインストールして実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="99650-108">This deployment guide describes how to install and run the business process management solution on a development computer and multiple production servers.</span></span>  
  
 <span data-ttu-id="99650-109">ビジネス プロセス管理ソリューションの詳細については、次を参照してください。[ビジネス プロセス管理ソリューションを理解する](../core/understanding-the-business-process-management-solution.md)です。</span><span class="sxs-lookup"><span data-stu-id="99650-109">For more information about the business process management solution, see [Understanding the Business Process Management Solution](../core/understanding-the-business-process-management-solution.md).</span></span>  
  
 <span data-ttu-id="99650-110">**対象読者**</span><span class="sxs-lookup"><span data-stu-id="99650-110">**Reader Guidance**</span></span>  
  
 <span data-ttu-id="99650-111">このドキュメントは、BizTalk Server、Windows Server、および Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] に関する知識があることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="99650-111">This document assumes that you are familiar with BizTalk Server, Windows Server, and Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="99650-112">また、エンタープライズ アプリケーション統合と Web サービスの基本的な概念についても理解していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="99650-112">It also assumes that you understand basic concepts about enterprise application integration and Web services.</span></span> <span data-ttu-id="99650-113">さらに、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を使用してアプリケーションを作成する方法や、プロジェクトの作成、参照の設定、デバッグ モードを使用したソリューションのデバッグおよびテストに関しても理解しておいてください。</span><span class="sxs-lookup"><span data-stu-id="99650-113">Additionally, we recommend that you are familiar with how to build applications by using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and that you are familiar with creating projects, setting references, and using the debug mode to debug and test your solution.</span></span> <span data-ttu-id="99650-114">IT 担当者および開発者の必要なスキルと知識の詳細については、次を参照してください。[前提条件のスキルと知識](../core/prerequisite-skills-and-knowledge5.md)です。</span><span class="sxs-lookup"><span data-stu-id="99650-114">For more information about the prerequisite skills and knowledge for IT professionals and developers, see [Prerequisite Skills and Knowledge](../core/prerequisite-skills-and-knowledge5.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="99650-115">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="99650-115">In This Section</span></span>  
  
-   [<span data-ttu-id="99650-116">ビジネス プロセス管理ソリューションの開発者のコンピュータ設定</span><span class="sxs-lookup"><span data-stu-id="99650-116">Developer Machine Setup for the Business Process Management Solution</span></span>](../core/developer-machine-setup-for-the-business-process-management-solution.md)