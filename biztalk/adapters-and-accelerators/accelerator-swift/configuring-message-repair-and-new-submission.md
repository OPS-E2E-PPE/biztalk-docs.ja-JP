---
title: Message Repair and New Submission の構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Message Repair and New Submission, configuring
- A4SWIFT, Message Repair and New Submission
- configuring, Message Repair and New Submission
ms.assetid: e3e5e865-109c-469e-8b5b-c2675583d5a5
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d2cdbad69b017a3927d3912de42053072d061b6
ms.sourcegitcommit: 3371ffd8ceca02e2b3715d53a1e0c0a59045912e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/07/2018
ms.locfileid: "34848970"
---
# <a name="configuring-message-repair-and-new-submission"></a><span data-ttu-id="00d1e-102">Message Repair and New Submission を構成します。</span><span class="sxs-lookup"><span data-stu-id="00d1e-102">Configuring Message Repair and New Submission</span></span>
<span data-ttu-id="00d1e-103">次のセクションの Message Repair and New Submission の機能を構成する手順を実行する必要があります[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]、次の図に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="00d1e-103">You must perform the steps in the following sections to configure the Message Repair and New Submission feature of [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)], as shown in the following figure.</span></span>  
  
 <span data-ttu-id="00d1e-104">![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-message-repair-configuration.gif "A4SWIFT_Message_Repair_Configuration")</span><span class="sxs-lookup"><span data-stu-id="00d1e-104">![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-message-repair-configuration.gif "A4SWIFT_Message_Repair_Configuration")</span></span>  
  
 <span data-ttu-id="00d1e-105">A4SWIFT のインストール ウィザードで、Message Repair および New Submission および FIN 対応調整 (FRR) または Message Repair and New Submission FRR、または Message Repair and New Submission せず FRR なしのインストールを選択できます。</span><span class="sxs-lookup"><span data-stu-id="00d1e-105">In the A4SWIFT Installation Wizard, you can choose to install Message Repair and New Submission and FIN Response Reconciliation (FRR), or Message Repair and New Submission without FRR, or FRR without Message Repair and New Submission.</span></span> <span data-ttu-id="00d1e-106">その結果、このセクションの手順に限りませんをインストールしている FRR を構成します。</span><span class="sxs-lookup"><span data-stu-id="00d1e-106">As a result, the instructions in this section do not assume that you are installing and configuring FRR.</span></span> <span data-ttu-id="00d1e-107">」の手順を実行したこと、ただし、前提、 [A4SWIFT コンポーネント構成ガイド](../../adapters-and-accelerators/accelerator-swift/a4swift-component-configuration-guide.md)セクションです。</span><span class="sxs-lookup"><span data-stu-id="00d1e-107">They do, however, assume that you have performed the steps in the [A4SWIFT Component Configuration Guide](../../adapters-and-accelerators/accelerator-swift/a4swift-component-configuration-guide.md) section.</span></span>  
  
 <span data-ttu-id="00d1e-108">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="00d1e-108">This section contains:</span></span>  
  
-   [<span data-ttu-id="00d1e-109">証明書のインストール</span><span class="sxs-lookup"><span data-stu-id="00d1e-109">Installing Certificates</span></span>](../../adapters-and-accelerators/accelerator-swift/installing-certificates.md)  
  
-   [<span data-ttu-id="00d1e-110">A4SWIFT プロパティの設定</span><span class="sxs-lookup"><span data-stu-id="00d1e-110">Setting A4SWIFT Properties</span></span>](../../adapters-and-accelerators/accelerator-swift/setting-a4swift-properties.md)  
  
-   [<span data-ttu-id="00d1e-111">A4SWIFT ユーザーの追加と Windows グループの更新</span><span class="sxs-lookup"><span data-stu-id="00d1e-111">Adding A4SWIFT Users and Updating Windows Groups</span></span>](../../adapters-and-accelerators/accelerator-swift/adding-a4swift-users-and-updating-windows-groups.md)  
  
-   [<span data-ttu-id="00d1e-112">ロールと部門の追加</span><span class="sxs-lookup"><span data-stu-id="00d1e-112">Adding Roles and Departments</span></span>](../../adapters-and-accelerators/accelerator-swift/adding-roles-and-departments.md)  
  
-   [<span data-ttu-id="00d1e-113">A4SWIFT エンベロープ スキーマの展開</span><span class="sxs-lookup"><span data-stu-id="00d1e-113">Deploying A4SWIFT Envelope Schemas</span></span>](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-envelope-schemas.md)  
  
-   [<span data-ttu-id="00d1e-114">InfoPath フォーム テンプレートの発行</span><span class="sxs-lookup"><span data-stu-id="00d1e-114">Publishing InfoPath Form Templates</span></span>](http://msdn.microsoft.com/2947e1ad-8c44-4cdb-bbde-7683e186b41b)