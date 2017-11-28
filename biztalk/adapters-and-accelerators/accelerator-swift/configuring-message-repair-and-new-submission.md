---
title: "Message Repair and New Submission の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Message Repair and New Submission, configuring
- A4SWIFT, Message Repair and New Submission
- configuring, Message Repair and New Submission
ms.assetid: e3e5e865-109c-469e-8b5b-c2675583d5a5
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00e42bcfc5e744aa005e2e0a790dfc505b7a834d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-message-repair-and-new-submission"></a><span data-ttu-id="50029-102">Message Repair and New Submission を構成します。</span><span class="sxs-lookup"><span data-stu-id="50029-102">Configuring Message Repair and New Submission</span></span>
<span data-ttu-id="50029-103">次のセクションの Message Repair and New Submission の機能を構成する手順を実行する必要があります[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]、次の図に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="50029-103">You must perform the steps in the following sections to configure the Message Repair and New Submission feature of [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)], as shown in the following figure.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-message-repair-configuration.gif "A4SWIFT_Message_Repair_Configuration")  
  
 <span data-ttu-id="50029-104">A4SWIFT のインストール ウィザードで、Message Repair および New Submission および FIN 対応調整 (FRR) または Message Repair and New Submission FRR、または Message Repair and New Submission せず FRR なしのインストールを選択できます。</span><span class="sxs-lookup"><span data-stu-id="50029-104">In the A4SWIFT Installation Wizard, you can choose to install Message Repair and New Submission and FIN Response Reconciliation (FRR), or Message Repair and New Submission without FRR, or FRR without Message Repair and New Submission.</span></span> <span data-ttu-id="50029-105">その結果、このセクションの手順に限りませんをインストールしている FRR を構成します。</span><span class="sxs-lookup"><span data-stu-id="50029-105">As a result, the instructions in this section do not assume that you are installing and configuring FRR.</span></span> <span data-ttu-id="50029-106">」の手順を実行したこと、ただし、前提、 [A4SWIFT コンポーネント構成ガイド](../../adapters-and-accelerators/accelerator-swift/a4swift-component-configuration-guide.md)セクションです。</span><span class="sxs-lookup"><span data-stu-id="50029-106">They do, however, assume that you have performed the steps in the [A4SWIFT Component Configuration Guide](../../adapters-and-accelerators/accelerator-swift/a4swift-component-configuration-guide.md) section.</span></span>  
  
 <span data-ttu-id="50029-107">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="50029-107">This section contains:</span></span>  
  
-   [<span data-ttu-id="50029-108">証明書のインストール</span><span class="sxs-lookup"><span data-stu-id="50029-108">Installing Certificates</span></span>](../../adapters-and-accelerators/accelerator-swift/installing-certificates.md)  
  
-   [<span data-ttu-id="50029-109">A4SWIFT のプロパティの設定</span><span class="sxs-lookup"><span data-stu-id="50029-109">Setting A4SWIFT Properties</span></span>](../../adapters-and-accelerators/accelerator-swift/setting-a4swift-properties.md)  
  
-   [<span data-ttu-id="50029-110">A4SWIFT のユーザーを追加して、Windows グループの更新</span><span class="sxs-lookup"><span data-stu-id="50029-110">Adding A4SWIFT Users and Updating Windows Groups</span></span>](../../adapters-and-accelerators/accelerator-swift/adding-a4swift-users-and-updating-windows-groups.md)  
  
-   [<span data-ttu-id="50029-111">ロールや部門の追加</span><span class="sxs-lookup"><span data-stu-id="50029-111">Adding Roles and Departments</span></span>](../../adapters-and-accelerators/accelerator-swift/adding-roles-and-departments.md)  
  
-   [<span data-ttu-id="50029-112">A4SWIFT エンベロープ スキーマを展開します。</span><span class="sxs-lookup"><span data-stu-id="50029-112">Deploying A4SWIFT Envelope Schemas</span></span>](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-envelope-schemas.md)  
  
-   [<span data-ttu-id="50029-113">InfoPath フォーム テンプレートの発行</span><span class="sxs-lookup"><span data-stu-id="50029-113">Publishing InfoPath Form Templates</span></span>](http://msdn.microsoft.com/en-us/2947e1ad-8c44-4cdb-bbde-7683e186b41b)