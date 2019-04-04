---
title: PIP の実装 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- PIPs
- PIPs, element-level constraints
- Document Type Definitions (DTDs)
- PIPs, schemas
- examples, schemas
- schemas, examples
- PIPs, about PIPs
- element-level constraints
- PIPs, DTDs
- schemas, PIPs
- XML Schema Definition files (XSDs)
- Partner Interface Processes (PIPs)
- DTDs, XSDs
- schemas, XSDs
ms.assetid: 0d964223-e0b6-4377-b26a-5fdc89ec81f4
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba85938e2e0da2b8ee09de476c81acdf202b449c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983003"
---
# <a name="pip-implementation"></a><span data-ttu-id="091b8-102">PIP 実装</span><span class="sxs-lookup"><span data-stu-id="091b8-102">PIP Implementation</span></span>
<span data-ttu-id="091b8-103">RosettaNet Partner Interface Process (Pip) は、サプライ チェーン内の取引先間のビジネス プロセスを定義します。</span><span class="sxs-lookup"><span data-stu-id="091b8-103">RosettaNet Partner Interface Processes (PIPs) define business processes between trading partners in a supply chain.</span></span> <span data-ttu-id="091b8-104">Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]一連の Pip のボックスのことができますを作成して Pip を追加します。</span><span class="sxs-lookup"><span data-stu-id="091b8-104">Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] provides a set of PIPs out-of-the-box and you can create additional PIPs.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="091b8-105">RosettaNet 組織で定義されているすべての Pip をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="091b8-105">supports all PIPs defined by the RosettaNet organization.</span></span>  
  
 <span data-ttu-id="091b8-106">詳細については、[RosettaNet Pip](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-pips.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="091b8-106">For more information, see [RosettaNet PIPs](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-pips.md).</span></span>  
  
## <a name="schemas-in-btarn"></a><span data-ttu-id="091b8-107">BTARN のスキーマ</span><span class="sxs-lookup"><span data-stu-id="091b8-107">Schemas in BTARN</span></span>  
 <span data-ttu-id="091b8-108">RosettaNet は、文書型定義 (DTD) の形式で PIP メッセージ スキーマをすべて指定します。</span><span class="sxs-lookup"><span data-stu-id="091b8-108">RosettaNet specifies all PIP message schemas in the form of Document Type Definitions (DTDs).</span></span> <span data-ttu-id="091b8-109">ビジネス ドキュメントを交換する取引先は、これらの DTD に準拠している必要があります。</span><span class="sxs-lookup"><span data-stu-id="091b8-109">Trading partners who participate in the business-document exchange must comply with these DTDs.</span></span> <span data-ttu-id="091b8-110">ただし、 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Microsoft BizTalk Server は、Dtd ではなく Xsd を使用してドキュメントを表すために、これらの Dtd を XML スキーマ定義ファイル (Xsd) として実装します。</span><span class="sxs-lookup"><span data-stu-id="091b8-110">However, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] implements these DTDs as XML Schema Definition files (XSDs), because Microsoft  BizTalk Server represents documents by using XSDs, not DTDs.</span></span> <span data-ttu-id="091b8-111">機能面では XSD が DTD に優先しており、XSD はメッセージ ガイドラインに提供されるほとんどの情報をネイティブに表すことができます。</span><span class="sxs-lookup"><span data-stu-id="091b8-111">XSDs supersede DTDs in terms of functionality, and can represent most of the information provided in the message guidelines natively.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="091b8-112">は、最近 RosettaNet 組織によって発行された、XSD 仕様を使用する次世代の PIP もサポートします。</span><span class="sxs-lookup"><span data-stu-id="091b8-112">also supports next-generation PIPs, recently published by the RosettaNet organization, that use XSD specifications.</span></span>  
  
 <span data-ttu-id="091b8-113">新しい PIP を実装するためには、PIP の DTD を XSD へ変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="091b8-113">To implement a new PIP, you must convert the PIP's DTD into an XSD.</span></span> <span data-ttu-id="091b8-114">RosettaNet の Web サイトから PIP に関連付けられている DTD をダウンロードする[ http://go.microsoft.com/fwlink/?linkid=33859](http://go.microsoft.com/fwlink/?linkid=33859)します。</span><span class="sxs-lookup"><span data-stu-id="091b8-114">You download the DTD associated with the PIP from the RosettaNet Web site at [http://go.microsoft.com/fwlink/?linkid=33859](http://go.microsoft.com/fwlink/?linkid=33859).</span></span> <span data-ttu-id="091b8-115">次に、PIP に基づく [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] プロセス構成プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="091b8-115">You then create a [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] process configuration profile based on the PIP.</span></span> <span data-ttu-id="091b8-116">詳細については、[新しい Partner Interface Process の組み込み](../../adapters-and-accelerators/accelerator-rosettanet/incorporating-a-new-partner-interface-process.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="091b8-116">For more information, see [Incorporating a New Partner Interface Process](../../adapters-and-accelerators/accelerator-rosettanet/incorporating-a-new-partner-interface-process.md).</span></span>  
  
 <span data-ttu-id="091b8-117">既存のプロファイルに基づいて、新しいプロセス構成プロファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="091b8-117">You can create a new process configuration profile based on an existing profile.</span></span> <span data-ttu-id="091b8-118">詳細については、[を作成またはプロセス構成の編集方法](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="091b8-118">For more information, see [How to Create or Edit a Process Configuration](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md).</span></span> <span data-ttu-id="091b8-119">1 つのプロセス構成プロファイルに基づいて、同じパートナー間で複数のアグリーメントを作成できます。</span><span class="sxs-lookup"><span data-stu-id="091b8-119">You can create multiple agreements based on the same process configuration profile between the same partners.</span></span> <span data-ttu-id="091b8-120">ただし、アクティブ化できるアグリーメントは一度に 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="091b8-120">However, you can only activate one of them at a time.</span></span> <span data-ttu-id="091b8-121">作成し、アグリーメントをアクティブ化を参照してください。[を作成または編集するアグリーメント](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)します。</span><span class="sxs-lookup"><span data-stu-id="091b8-121">To create and activate an agreement, see [Creating or Editing an Agreement](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md).</span></span>  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="091b8-122">では、以下の RosettaNet ヘッダーに対して RosettaNet メッセージ ガイドラインの制約を適用して XSD を実装します。</span><span class="sxs-lookup"><span data-stu-id="091b8-122">implements XSDs with the RosettaNet message-guideline constraints for the following RosettaNet headers:</span></span>  
  
-   <span data-ttu-id="091b8-123">RNIF 1.1 および RNIF 2.01 の Preamble</span><span class="sxs-lookup"><span data-stu-id="091b8-123">Preamble for RNIF 1.1 and RNIF 2.01</span></span>  
  
-   <span data-ttu-id="091b8-124">RNIF 1.1 および RNIF 2.0 の Service Header</span><span class="sxs-lookup"><span data-stu-id="091b8-124">Service header for RNIF 1.1 and RNIF 2.0</span></span>  
  
-   <span data-ttu-id="091b8-125">RNIF 2.0 の Delivery Header</span><span class="sxs-lookup"><span data-stu-id="091b8-125">Delivery header for RNIF 2.0</span></span>  
  
-   <span data-ttu-id="091b8-126">RNIF 1.1 および RNIF 2.01 のすべてのシグナル メッセージの Service Content</span><span class="sxs-lookup"><span data-stu-id="091b8-126">Service content for all signal messages of RNIF 1.1 and RNIF 2.01.</span></span>  
  
## <a name="sample-schemas"></a><span data-ttu-id="091b8-127">サンプル スキーマ</span><span class="sxs-lookup"><span data-stu-id="091b8-127">Sample Schemas</span></span>  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="091b8-128">セットアップのインストールに Pip のセット\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\schemas します。</span><span class="sxs-lookup"><span data-stu-id="091b8-128">setup installs a set of PIPs in \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\Schemas.</span></span> <span data-ttu-id="091b8-129">これらはサンプルとしてのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="091b8-129">These are for sample purposes only.</span></span> <span data-ttu-id="091b8-130">実際に使用する前に、これらのスキーマを公開された最新の RosettaNet PIP 仕様およびメッセージ ガイドラインと照らし合わせることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="091b8-130">Before using them in production, it is highly recommended that you compare these schemas against the latest published RosettaNet PIP specifications and message guidelines.</span></span> <span data-ttu-id="091b8-131">BTARN は、すべての RosettaNet PIP の実装をサポートします。</span><span class="sxs-lookup"><span data-stu-id="091b8-131">BTARN supports implementation of all RosettaNet PIPs.</span></span>  
  
## <a name="element-level-constraints-in-btarn"></a><span data-ttu-id="091b8-132">BTARN の要素レベルの制約</span><span class="sxs-lookup"><span data-stu-id="091b8-132">Element-Level Constraints in BTARN</span></span>  
 <span data-ttu-id="091b8-133">BTARN では、PIP メッセージ ガイドライン文書で指定されている要素レベルの制約をプロセス構成の設定として実装します。</span><span class="sxs-lookup"><span data-stu-id="091b8-133">In BTARN, you implement the element-level constraints specified in the PIP message-guideline documents as process configuration settings.</span></span> <span data-ttu-id="091b8-134">ランタイム コンポーネントはプロセス構成を使用して、特定の PIP の処理方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="091b8-134">Runtime components use the process configuration to determine how to process a specific PIP.</span></span>  
  
 <span data-ttu-id="091b8-135">新しい PIP を実装するためには、新しいプロセス構成プロファイルを作成して、PIP にメッセージ ガイドライン制約を適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="091b8-135">To implement a new PIP, you must apply the message guideline constraints for the PIP by creating a new process configuration profile.</span></span> <span data-ttu-id="091b8-136">この操作は BTARN 管理コンソールで行います。</span><span class="sxs-lookup"><span data-stu-id="091b8-136">You do this in the BTARN Management Console.</span></span> <span data-ttu-id="091b8-137">詳細については、[を作成またはプロセス構成の編集方法](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="091b8-137">For more information, see [How to Create or Edit a Process Configuration](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md).</span></span>  
  
 <span data-ttu-id="091b8-138">プロセス構成プロファイルは、のように、RosettaNet PIP 仕様にマップ[PIP 仕様を使用して、プロセス構成を作成する](../../adapters-and-accelerators/accelerator-rosettanet/using-the-pip-specification-to-create-a-process-configuration.md)します。</span><span class="sxs-lookup"><span data-stu-id="091b8-138">The process configuration profile maps to the RosettaNet PIP specification as shown in [Using the PIP Specification to Create a Process Configuration](../../adapters-and-accelerators/accelerator-rosettanet/using-the-pip-specification-to-create-a-process-configuration.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="091b8-139">参照</span><span class="sxs-lookup"><span data-stu-id="091b8-139">See Also</span></span>  
 <span data-ttu-id="091b8-140">[BizTalk Server に BizTalk Accelerator for RosettaNet の追加](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="091b8-140">[What BizTalk Accelerator for RosettaNet Adds to BizTalk Server](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md) </span></span>  
 <span data-ttu-id="091b8-141">[取引先アグリーメント](../../adapters-and-accelerators/accelerator-rosettanet/trading-partner-agreements.md) </span><span class="sxs-lookup"><span data-stu-id="091b8-141">[Trading Partner Agreements](../../adapters-and-accelerators/accelerator-rosettanet/trading-partner-agreements.md) </span></span>  
 [<span data-ttu-id="091b8-142">RosettaNet PIP</span><span class="sxs-lookup"><span data-stu-id="091b8-142">RosettaNet PIPs</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-pips.md)
