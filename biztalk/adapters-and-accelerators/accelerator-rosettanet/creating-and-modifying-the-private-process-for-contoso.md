---
title: 作成と Contoso のプライベート プロセスの変更 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private processes, creating
- configuring, private processes
- private processes, configuring
- private process tutorial, creating private processes
- creating, private processes
- private process tutorial, configuring private processes
ms.assetid: 0690aaef-cd9e-46aa-8bd5-22744d5aec4c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f89a9c51d99ba257acbda7c1b417e46b2ad48a03
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65284520"
---
# <a name="creating-and-modifying-the-private-process-for-contoso"></a><span data-ttu-id="deef7-102">作成と Contoso のプライベート プロセスの変更</span><span class="sxs-lookup"><span data-stu-id="deef7-102">Creating and Modifying the Private Process for Contoso</span></span>
<span data-ttu-id="deef7-103">Microsoft® 内でプライベート プロセスをカスタマイズすることで、ソリューションを実装する場合は、RosettaNet ベースのメッセージで追加のタスクを実行することができます[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="deef7-103">You can perform additional tasks with RosettaNet-based messages when implementing your solution by customizing the private process within Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].</span></span> <span data-ttu-id="deef7-104">このセクションでは、ポリシーと、プライベート プロセス オーケストレーションをカスタマイズする BizTalk エディターを作成するビジネス ルール エンジン (BRE) を使用して、プライベート プロセスをカスタマイズする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="deef7-104">This section demonstrates how to customize the private process by using the Business Rule Engine (BRE) to create policies and BizTalk Editor to customize the private process orchestration.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="deef7-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="deef7-105">In This Section</span></span>  
  
-   [<span data-ttu-id="deef7-106">ステップ 1: 既存の Contoso ソリューションへの既存の BizTalk プロジェクトの追加</span><span class="sxs-lookup"><span data-stu-id="deef7-106">Step 1: Adding an Existing BizTalk Project to the Existing Contoso Solution</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-1-adding-an-existing-biztalk-project-to-the-existing-contoso-solution.md)  
  
-   [<span data-ttu-id="deef7-107">手順 2:Contoso 用のボキャブラリの定義と公開</span><span class="sxs-lookup"><span data-stu-id="deef7-107">Step 2: Defining and Publishing the Vocabulary for Contoso</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-2-defining-and-publishing-the-vocabulary-for-contoso.md)  
  
-   [<span data-ttu-id="deef7-108">ステップ 3:Contoso のビジネス ポリシーの定義、公開、展開</span><span class="sxs-lookup"><span data-stu-id="deef7-108">Step 3: Defining, Publishing, and Deploying the Business Policy for Contoso</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-3-defining-publishing-and-deploying-the-business-policy-for-contoso.md)  
  
-   [<span data-ttu-id="deef7-109">手順 4:HeaderHelper プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="deef7-109">Step 4: Creating the HeaderHelper Project</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-4-creating-the-headerhelper-project.md)  
  
-   [<span data-ttu-id="deef7-110">手順 5:Contoso プライベート プロセス オーケストレーションの変更</span><span class="sxs-lookup"><span data-stu-id="deef7-110">Step 5: Modifying the Contoso Private Process Orchestration</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-5-modifying-the-contoso-private-process-orchestration.md)  
  
-   [<span data-ttu-id="deef7-111">手順 6:オーケストレーション図形の構成 (Contoso)</span><span class="sxs-lookup"><span data-stu-id="deef7-111">Step 6: Configuring Orchestration Shapes (Contoso)</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-6-configuring-orchestration-shapes-contoso.md)  
  
-   [<span data-ttu-id="deef7-112">手順 7:ポートの作成と構成</span><span class="sxs-lookup"><span data-stu-id="deef7-112">Step 7: Creating and Configuring Ports</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-7-creating-and-configuring-ports.md)  
  
-   [<span data-ttu-id="deef7-113">手順 8:Contoso オーケストレーションのビルドと展開</span><span class="sxs-lookup"><span data-stu-id="deef7-113">Step 8: Building and Deploying the Contoso Orchestration</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-8-building-and-deploying-the-contoso-orchestration.md)  
  
-   [<span data-ttu-id="deef7-114">手順 9:Contoso オーケストレーションの開始</span><span class="sxs-lookup"><span data-stu-id="deef7-114">Step 9: Starting the Contoso Orchestration</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-9-starting-the-contoso-orchestration.md)