---
title: Message Repair and New Submission の構成 |Microsoft Docs
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
ms.openlocfilehash: 0544adb9fc2ffa60bfc3b69ebee1937e5eb7a18a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995795"
---
# <a name="configuring-message-repair-and-new-submission"></a><span data-ttu-id="50b37-102">Message Repair and New Submission の構成</span><span class="sxs-lookup"><span data-stu-id="50b37-102">Configuring Message Repair and New Submission</span></span>
<span data-ttu-id="50b37-103">Microsoft の Message Repair and New Submission の機能を構成する次のセクションで手順を実行する必要があります[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]、次の図に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="50b37-103">You must perform the steps in the following sections to configure the Message Repair and New Submission feature of Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)], as shown in the following figure.</span></span>  
  
 <span data-ttu-id="50b37-104">![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-message-repair-configuration.gif "A4SWIFT_Message_Repair_Configuration")</span><span class="sxs-lookup"><span data-stu-id="50b37-104">![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-message-repair-configuration.gif "A4SWIFT_Message_Repair_Configuration")</span></span>  
  
 <span data-ttu-id="50b37-105">A4SWIFT のインストール ウィザードでは、Message Repair および New Submission および FIN 応答の調整 (FRR) または Message Repair and New Submission FRR、または Message Repair and New Submission せず FRR せずにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="50b37-105">In the A4SWIFT Installation Wizard, you can choose to install Message Repair and New Submission and FIN Response Reconciliation (FRR), or Message Repair and New Submission without FRR, or FRR without Message Repair and New Submission.</span></span> <span data-ttu-id="50b37-106">その結果、インストールと構成の FRR は、このセクションの手順には想定しないでください。</span><span class="sxs-lookup"><span data-stu-id="50b37-106">As a result, the instructions in this section do not assume that you are installing and configuring FRR.</span></span> <span data-ttu-id="50b37-107">ただし、前提としている手順を実行したこと、 [A4SWIFT コンポーネント構成ガイド](../../adapters-and-accelerators/accelerator-swift/a4swift-component-configuration-guide.md)セクション。</span><span class="sxs-lookup"><span data-stu-id="50b37-107">They do, however, assume that you have performed the steps in the [A4SWIFT Component Configuration Guide](../../adapters-and-accelerators/accelerator-swift/a4swift-component-configuration-guide.md) section.</span></span>  
  
 <span data-ttu-id="50b37-108">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="50b37-108">This section contains:</span></span>  
  
-   [<span data-ttu-id="50b37-109">証明書のインストール</span><span class="sxs-lookup"><span data-stu-id="50b37-109">Installing Certificates</span></span>](../../adapters-and-accelerators/accelerator-swift/installing-certificates.md)  
  
-   [<span data-ttu-id="50b37-110">A4SWIFT プロパティの設定</span><span class="sxs-lookup"><span data-stu-id="50b37-110">Setting A4SWIFT Properties</span></span>](../../adapters-and-accelerators/accelerator-swift/setting-a4swift-properties.md)  
  
-   [<span data-ttu-id="50b37-111">A4SWIFT ユーザーの追加と Windows グループの更新</span><span class="sxs-lookup"><span data-stu-id="50b37-111">Adding A4SWIFT Users and Updating Windows Groups</span></span>](../../adapters-and-accelerators/accelerator-swift/adding-a4swift-users-and-updating-windows-groups.md)  
  
-   [<span data-ttu-id="50b37-112">ロールと部門の追加</span><span class="sxs-lookup"><span data-stu-id="50b37-112">Adding Roles and Departments</span></span>](../../adapters-and-accelerators/accelerator-swift/adding-roles-and-departments.md)  
  
-   [<span data-ttu-id="50b37-113">A4SWIFT エンベロープ スキーマの展開</span><span class="sxs-lookup"><span data-stu-id="50b37-113">Deploying A4SWIFT Envelope Schemas</span></span>](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-envelope-schemas.md)  
  
-   [<span data-ttu-id="50b37-114">InfoPath フォーム テンプレートの発行</span><span class="sxs-lookup"><span data-stu-id="50b37-114">Publishing InfoPath Form Templates</span></span>](http://msdn.microsoft.com/2947e1ad-8c44-4cdb-bbde-7683e186b41b)