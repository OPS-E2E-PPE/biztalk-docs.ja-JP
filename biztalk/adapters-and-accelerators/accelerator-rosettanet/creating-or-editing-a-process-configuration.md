---
title: 作成または編集のプロセスの構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- process configuration, modifying
- process configuration, creating
- creating, process configuration
- modifying, process configuration
ms.assetid: 39cc2c93-0986-48d3-8c6f-4280ec9af4e0
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9130ab7370f8f6e1fcbe75bc7a85a6c74dfe328
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207122"
---
# <a name="creating-or-editing-a-process-configuration"></a><span data-ttu-id="c3787-102">作成またはプロセス構成を編集します。</span><span class="sxs-lookup"><span data-stu-id="c3787-102">Creating or Editing a Process Configuration</span></span>
<span data-ttu-id="c3787-103">このセクションを作成または構成を編集するプロセス、プロセス PIP (Partner Interface) で実装する方法について説明[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="c3787-103">This section describes how to create or edit a process configuration to implement a Partner Interface Process (PIP) in [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].</span></span> <span data-ttu-id="c3787-104">RosettaNet PIP は、2 つの取引先間におけるビジネス プロセス ダイアログを定義します。</span><span class="sxs-lookup"><span data-stu-id="c3787-104">A RosettaNet PIP defines a business-process dialog between two trading partners.</span></span> <span data-ttu-id="c3787-105">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]パートナーと PIP を作成するには、プロセス構成を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3787-105">In [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], to create a PIP with a partner, you must first create a process configuration.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="c3787-106">PIP のすべての構成の特徴を格納するのにには、このプロファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="c3787-106"> uses this profile to store all configuration characteristics of the PIP.</span></span> <span data-ttu-id="c3787-107">この構成は、パートナーとのアグリーメントの作成に使用できます。</span><span class="sxs-lookup"><span data-stu-id="c3787-107">You can then use this configuration to create an agreement with the partner.</span></span>  
  
 <span data-ttu-id="c3787-108">プロセス構成のプロパティ、および作成またはプロセス構成を編集するための手順については、次を参照してください。[を作成またはプロセス構成の編集方法](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)です。</span><span class="sxs-lookup"><span data-stu-id="c3787-108">For information about process configuration properties, and procedures for creating or editing a process configuration, see [How to Create or Edit a Process Configuration](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md).</span></span>  
  
 <span data-ttu-id="c3787-109">新しいプロセス構成を作成する場合は、RosettaNet 組織によって管理される PIP 仕様ドキュメントに基づいた設定を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3787-109">In creating a new process configuration, you must base the settings on the PIP specification document maintained by the RosettaNet organization.</span></span> <span data-ttu-id="c3787-110">すべてのプロセス構成設定は PIP 仕様に従って行われ、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] では、ほとんどの設定に既定値 (そのフィールドに最も一般的に使用される値) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c3787-110">All process configuration settings come from the PIP specifications, and [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] populates most of the settings with default values that are the most typically used values for the fields.</span></span> <span data-ttu-id="c3787-111">設定が適切な PIP 仕様の値に対応することを必ず確認してください。</span><span class="sxs-lookup"><span data-stu-id="c3787-111">You must verify that the settings correspond to the values in the appropriate PIP specification.</span></span> <span data-ttu-id="c3787-112">入力した PIP 設定が PIP 仕様のガイダンスにマップする方法の詳細については、次を参照してください。 [PIP 仕様を使用して、プロセス構成を作成する](../../adapters-and-accelerators/accelerator-rosettanet/using-the-pip-specification-to-create-a-process-configuration.md)です。</span><span class="sxs-lookup"><span data-stu-id="c3787-112">For more information about how the PIP settings that you enter map to the guidance in the PIP specification, see [Using the PIP Specification to Create a Process Configuration](../../adapters-and-accelerators/accelerator-rosettanet/using-the-pip-specification-to-create-a-process-configuration.md).</span></span>  
  
 <span data-ttu-id="c3787-113">プロセス構成は、RosettaNet または CIDX (Chemical Industry Data Exchange) のどちらにも構成できます。</span><span class="sxs-lookup"><span data-stu-id="c3787-113">The process configuration can be for either RosettaNet or CIDX (Chemical Industry Data Exchange).</span></span> <span data-ttu-id="c3787-114">CIDX の構成については、次を参照してください。[設定を CIDX eStandards メッセージ交換](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md)です。</span><span class="sxs-lookup"><span data-stu-id="c3787-114">For information about a CIDX configuration, see [Setting Up CIDX eStandards Message Exchange](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md).</span></span>  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="c3787-115"> では、プロセスがアクティブな間はプロセス構成を変更できません。</span><span class="sxs-lookup"><span data-stu-id="c3787-115"> does not support changing a process configuration while there are active processes.</span></span> <span data-ttu-id="c3787-116">プロセス構成を変更すると、アクティブなプロセスは失敗に終わります。</span><span class="sxs-lookup"><span data-stu-id="c3787-116">If you do so, the active processes will complete with failures.</span></span> <span data-ttu-id="c3787-117">プロセスを新しくすると、どのプロセスも新しい構成設定を正常に取得します。</span><span class="sxs-lookup"><span data-stu-id="c3787-117">All new processes will successfully pick up the new configuration settings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c3787-118">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c3787-118">In This Section</span></span>  
  
-   [<span data-ttu-id="c3787-119">作成またはプロセス構成を編集する方法</span><span class="sxs-lookup"><span data-stu-id="c3787-119">How to Create or Edit a Process Configuration</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)  
  
-   [<span data-ttu-id="c3787-120">PIP 仕様を使用して、プロセス構成を作成するには</span><span class="sxs-lookup"><span data-stu-id="c3787-120">Using the PIP Specification to Create a Process Configuration</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/using-the-pip-specification-to-create-a-process-configuration.md)  
  
-   [<span data-ttu-id="c3787-121">承認と否認不可プロパティ</span><span class="sxs-lookup"><span data-stu-id="c3787-121">Authorization and Non-Repudiation Properties</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/authorization-and-non-repudiation-properties.md)  
  
-   [<span data-ttu-id="c3787-122">設定を CIDX eStandards メッセージ交換</span><span class="sxs-lookup"><span data-stu-id="c3787-122">Setting Up CIDX eStandards Message Exchange</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md)