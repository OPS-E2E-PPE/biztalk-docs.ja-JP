---
title: ビジネス プロセス管理ソリューションの展開 |Microsoft Docs
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
ms.openlocfilehash: a58f9d2be88cb2dde91906db8db663a1dc280e40
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351894"
---
# <a name="deploying-the-business-process-management-solution"></a><span data-ttu-id="0b03e-102">ビジネス プロセス管理ソリューションの展開</span><span class="sxs-lookup"><span data-stu-id="0b03e-102">Deploying the Business Process Management Solution</span></span>
<span data-ttu-id="0b03e-103">ビジネス プロセス管理 (BPM) ソリューションは、BizTalk アプリケーションでプロセス マネージャを構築する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="0b03e-103">The Business Process Management (BPM) solution shows one way to construct a process manager in a BizTalk application.</span></span> <span data-ttu-id="0b03e-104">ソリューションを選択し、注文処理ステージの順序を制御するコンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="0b03e-104">The solution uses a component to select and control the sequence of stages in order processing.</span></span> <span data-ttu-id="0b03e-105">ソリューションが注文を取得、新しいサービスをアップグレード、またはサービスの終了になる可能性がある-、ログに記録し、処理のため渡す前に、順序を確認します。</span><span class="sxs-lookup"><span data-stu-id="0b03e-105">The solution takes an order—which may be for a new service, an upgrade, or termination of service—logs it, and acknowledges the order before passing it on for processing.</span></span> <span data-ttu-id="0b03e-106">処理は、注文を処理する 1 つまたは複数のステージで構成されます。</span><span class="sxs-lookup"><span data-stu-id="0b03e-106">The processing consists of one or more stages that handle the order.</span></span> <span data-ttu-id="0b03e-107">最後に、ソリューションは、元の注文要求に応答を返します。</span><span class="sxs-lookup"><span data-stu-id="0b03e-107">Finally, the solution returns a response to the original order request.</span></span>  
  
 <span data-ttu-id="0b03e-108">このデプロイ ガイドでは、インストールして、開発用コンピューターおよび複数の実稼働サーバーで、ビジネス プロセス管理ソリューションを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0b03e-108">This deployment guide describes how to install and run the business process management solution on a development computer and multiple production servers.</span></span>  
  
 <span data-ttu-id="0b03e-109">ビジネス プロセス管理ソリューションの詳細については、次を参照してください。 [、ビジネス プロセス管理ソリューションを理解する](../core/understanding-the-business-process-management-solution.md)します。</span><span class="sxs-lookup"><span data-stu-id="0b03e-109">For more information about the business process management solution, see [Understanding the Business Process Management Solution](../core/understanding-the-business-process-management-solution.md).</span></span>  
  
 <span data-ttu-id="0b03e-110">**対象読者**</span><span class="sxs-lookup"><span data-stu-id="0b03e-110">**Reader Guidance**</span></span>  
  
 <span data-ttu-id="0b03e-111">このドキュメントは、BizTalk Server、Windows Server、および Microsoft に精通していることを前提としています。[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="0b03e-111">This document assumes that you are familiar with BizTalk Server, Windows Server, and Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="0b03e-112">また、エンタープライズ アプリケーション統合と Web サービスの基本的な概念についても理解していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="0b03e-112">It also assumes that you understand basic concepts about enterprise application integration and Web services.</span></span> <span data-ttu-id="0b03e-113">またを使用してアプリケーションをビルドする方法について理解しているが推奨[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]した参照の設定、デバッグおよびテスト ソリューションをデバッグ モードを使用してプロジェクトの作成について理解しているとします。</span><span class="sxs-lookup"><span data-stu-id="0b03e-113">Additionally, we recommend that you are familiar with how to build applications by using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and that you are familiar with creating projects, setting references, and using the debug mode to debug and test your solution.</span></span> <span data-ttu-id="0b03e-114">IT プロフェッショナルと開発者のスキルと知識の詳細については、次を参照してください。[前提条件のスキルと知識](../core/prerequisite-skills-and-knowledge5.md)します。</span><span class="sxs-lookup"><span data-stu-id="0b03e-114">For more information about the prerequisite skills and knowledge for IT professionals and developers, see [Prerequisite Skills and Knowledge](../core/prerequisite-skills-and-knowledge5.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0b03e-115">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="0b03e-115">In This Section</span></span>  
  
-   [<span data-ttu-id="0b03e-116">ビジネス プロセス管理ソリューションに対する開発者のコンピューター設定</span><span class="sxs-lookup"><span data-stu-id="0b03e-116">Developer Machine Setup for the Business Process Management Solution</span></span>](../core/developer-machine-setup-for-the-business-process-management-solution.md)