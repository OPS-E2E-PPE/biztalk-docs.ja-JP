---
title: "CIDX ソリューションのセットアップ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- CIDX, process configuration
- creating, CIDX solutions
- CIDX, connecting to Elemica network
- agreements, CIDX
- process configuration, CIDX
- CIDX, agreements
- PIPs, importing for CIDX
- CIDX, PIPs
- CIDX, creating solutions
- CIDX, importing PIPs
- PIPs, CIDX
ms.assetid: 7f1f159f-3b09-4efd-907b-9a75f7f3ecd1
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab617efc701551f1d5bcbae2a292676cc4f33251
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="setting-up-a-cidx-solution"></a><span data-ttu-id="8208b-102">CIDX ソリューションの設定</span><span class="sxs-lookup"><span data-stu-id="8208b-102">Setting Up a CIDX Solution</span></span>
<span data-ttu-id="8208b-103">Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] は、CIDX (Chemical Industry Data Exchange) XML メッセージ交換 (CIDX Chem eStandards バージョン 2.0 および 3.0) をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="8208b-103">Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] support for CIDX (Chemical Industry Data Exchange) XML message exchange (CIDX Chem eStandards versions 2.0 and 3.0).</span></span> <span data-ttu-id="8208b-104">ここでは、次の操作を行って CIDX ソリューションを設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8208b-104">This topic describes how to set up a CIDX solution by doing the following:</span></span>  
  
-   <span data-ttu-id="8208b-105">プロセス構成の設定</span><span class="sxs-lookup"><span data-stu-id="8208b-105">Setting up a process configuration</span></span>  
  
-   <span data-ttu-id="8208b-106">アグリーメントの設定</span><span class="sxs-lookup"><span data-stu-id="8208b-106">Setting up an agreement</span></span>  
  
-   <span data-ttu-id="8208b-107">PIP の適用</span><span class="sxs-lookup"><span data-stu-id="8208b-107">Applying a PIP</span></span>  
  
-   <span data-ttu-id="8208b-108">XSD ベース PIP のインポート</span><span class="sxs-lookup"><span data-stu-id="8208b-108">Importing an XSD-based PIP</span></span>  
  
-   <span data-ttu-id="8208b-109">Elemica ネットワークへの接続</span><span class="sxs-lookup"><span data-stu-id="8208b-109">Connecting to the Elemica Network</span></span>  
  
## <a name="setting-up-a-cidx-process-configuration"></a><span data-ttu-id="8208b-110">CIDX プロセス構成の設定</span><span class="sxs-lookup"><span data-stu-id="8208b-110">Setting Up a CIDX Process Configuration</span></span>  
 <span data-ttu-id="8208b-111">CIDX eStandards メッセージ交換を設定するには、次のプロパティを持つプロセス構成を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8208b-111">To set up a CIDX eStandards message exchange, you need to create a process configuration that has the following properties:</span></span>  
  
-   <span data-ttu-id="8208b-112">**標準的な**プロパティ設定されたプロセス構成設定に**CIDX**</span><span class="sxs-lookup"><span data-stu-id="8208b-112">**Standard** property in the process configuration settings set to **CIDX**</span></span>  
  
-   <span data-ttu-id="8208b-113">**シングル アクション**プロパティ設定されたプロセス構成設定に**は True。**</span><span class="sxs-lookup"><span data-stu-id="8208b-113">**Is Single Action** property in the process configuration settings set to **True**</span></span>  
  
-   <span data-ttu-id="8208b-114">**0A1 アグリーメント**プロパティに設定する、取引先アグリーメントに**非 0A1**</span><span class="sxs-lookup"><span data-stu-id="8208b-114">**0A1 agreement** property in the trading partner agreement set to **No 0A1**</span></span>  
  
 <span data-ttu-id="8208b-115">詳細については、次を参照してください。[設定を CIDX eStandards メッセージ交換](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md)です。</span><span class="sxs-lookup"><span data-stu-id="8208b-115">For more information, see [Setting Up CIDX eStandards Message Exchange](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md).</span></span>  
  
## <a name="creating-a-cidx-agreement"></a><span data-ttu-id="8208b-116">CIDX アグリーメントの作成</span><span class="sxs-lookup"><span data-stu-id="8208b-116">Creating a CIDX Agreement</span></span>  
 <span data-ttu-id="8208b-117">CIDX eStandards メッセージ交換を設定するには、次のプロパティを持つアグリーメントを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8208b-117">To set up a CIDX eStandards message exchange, you need to create an agreement that has the following properties:</span></span>  
  
-   <span data-ttu-id="8208b-118">**RNIF バージョン**プロパティ設定したアグリーメント設定に**V01.10.00**</span><span class="sxs-lookup"><span data-stu-id="8208b-118">**RNIF Version** property in the agreement settings set to **V01.10.00**</span></span>  
  
-   <span data-ttu-id="8208b-119">**0A1 アグリーメント**プロパティ設定したアグリーメント設定に**非 0A1**</span><span class="sxs-lookup"><span data-stu-id="8208b-119">**0A1 agreement** property in the agreement settings set to **No 0A1**</span></span>  
  
 <span data-ttu-id="8208b-120">詳細については、次を参照してください。[を作成するか、契約の編集](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)です。</span><span class="sxs-lookup"><span data-stu-id="8208b-120">For more information, see [Creating or Editing an Agreement](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md).</span></span>  
  
## <a name="applying-a-pip-for-cidx"></a><span data-ttu-id="8208b-121">CIDX 用 PIP の適用</span><span class="sxs-lookup"><span data-stu-id="8208b-121">Applying a PIP for CIDX</span></span>  
 <span data-ttu-id="8208b-122">PIP を CIDX 実装に適用するには、設定、**標準**プロパティには、プロセス構成プロファイル**CIDX**です。</span><span class="sxs-lookup"><span data-stu-id="8208b-122">To apply a PIP to a CIDX implementation, set the **Standard** property in the process configuration profile to **CIDX**.</span></span> <span data-ttu-id="8208b-123">値を入力したらができます、**メッセージ標準**、**標準バージョン**、および**ペイロードのバインド ID**です。</span><span class="sxs-lookup"><span data-stu-id="8208b-123">After you have finished, you will be able to enter values for the **Message standard**, **Standard version**, and **Payload binding ID**.</span></span> <span data-ttu-id="8208b-124">これらの値は CIDX Chem eStandards の仕様に含まれています。</span><span class="sxs-lookup"><span data-stu-id="8208b-124">You can find these values in the CIDX Chem eStandards specification.</span></span>  
  
## <a name="importing-an-xsd-based-pip-for-cidx"></a><span data-ttu-id="8208b-125">CIDX 用 XSD ベース PIP のインポート</span><span class="sxs-lookup"><span data-stu-id="8208b-125">Importing an XSD-based PIP for CIDX</span></span>  
 <span data-ttu-id="8208b-126">CIDX 用、XSD ベース PIP をインポートするには、CIDX.org から PIP の ZIP ファイルをダウンロードする必要があります[http://go.microsoft.com/FWLink/?LinkID=33859](http://go.microsoft.com/FWLink/?LinkID=62361)です。</span><span class="sxs-lookup"><span data-stu-id="8208b-126">To import an XSD-based PIP for CIDX, you need to download the PIP's ZIP file from CIDX.org at [http://go.microsoft.com/FWLink/?LinkID=33859](http://go.microsoft.com/FWLink/?LinkID=62361).</span></span> <span data-ttu-id="8208b-127">説明されているインポート手順に従います[XSD ベース PIP のインポート](../../adapters-and-accelerators/accelerator-rosettanet/importing-an-xsd-based-pip.md)です。</span><span class="sxs-lookup"><span data-stu-id="8208b-127">Follow the import procedure described in [Importing an XSD-based PIP](../../adapters-and-accelerators/accelerator-rosettanet/importing-an-xsd-based-pip.md).</span></span>  
  
## <a name="connecting-to-the-elemica-network"></a><span data-ttu-id="8208b-128">Elemica ネットワークへの接続</span><span class="sxs-lookup"><span data-stu-id="8208b-128">Connecting to the Elemica Network</span></span>  
 <span data-ttu-id="8208b-129">[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] をカスタマイズし、Elemica Connectivity Pack のプロジェクト ファイルを使用して Elemica に接続できます。</span><span class="sxs-lookup"><span data-stu-id="8208b-129">You can customize [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] to connect to Elemica using project files in the Elemica Connectivity Pack.</span></span> <span data-ttu-id="8208b-130">Connectivity Pack をダウンロードする[http://go.microsoft.com/fwlink/?LinkId=46195](http://go.microsoft.com/fwlink/?LinkId=46195)です。</span><span class="sxs-lookup"><span data-stu-id="8208b-130">You can download the Connectivity Pack from [http://go.microsoft.com/fwlink/?LinkId=46195](http://go.microsoft.com/fwlink/?LinkId=46195).</span></span> <span data-ttu-id="8208b-131">詳細については、MSDN サイトで、「BizTalk Accelerator for RosettaNet 3.0 での Elemica ネットワークへの接続」ホワイト ペーパーを参照してください。 [http://go.microsoft.com/fwlink/?linkid=46539](http://go.microsoft.com/fwlink/?linkid=46539)です。</span><span class="sxs-lookup"><span data-stu-id="8208b-131">For more information, see the “Connecting to the Elemica Network with BizTalk Accelerator for RosettaNet 3.0” white paper on MSDN at [http://go.microsoft.com/fwlink/?linkid=46539](http://go.microsoft.com/fwlink/?linkid=46539).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8208b-132">[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] に対して、ホワイト ペーパー『BizTalk Accelerator for RosettaNet 3.0 での Elemica ネットワークへの接続』の情報は有効です。</span><span class="sxs-lookup"><span data-stu-id="8208b-132">The information in the "Connecting to the Elemica Network with BizTalk Accelerator for RosettaNet 3.0" white paper is valid for [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8208b-133">参照</span><span class="sxs-lookup"><span data-stu-id="8208b-133">See Also</span></span>  
 <span data-ttu-id="8208b-134">[CIDX サポート](../../adapters-and-accelerators/accelerator-rosettanet/cidx-support.md) </span><span class="sxs-lookup"><span data-stu-id="8208b-134">[CIDX Support](../../adapters-and-accelerators/accelerator-rosettanet/cidx-support.md) </span></span>  
 <span data-ttu-id="8208b-135">[CIDX メッセージ規格](../../adapters-and-accelerators/accelerator-rosettanet/cidx-messaging-standards.md) </span><span class="sxs-lookup"><span data-stu-id="8208b-135">[CIDX Messaging Standards](../../adapters-and-accelerators/accelerator-rosettanet/cidx-messaging-standards.md) </span></span>  
 <span data-ttu-id="8208b-136">[設定を CIDX eStandards メッセージ交換](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md) </span><span class="sxs-lookup"><span data-stu-id="8208b-136">[Setting Up CIDX eStandards Message Exchange](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md) </span></span>  
 <span data-ttu-id="8208b-137">[作成するか、契約の編集](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md) </span><span class="sxs-lookup"><span data-stu-id="8208b-137">[Creating or Editing an Agreement](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md) </span></span>  
 [<span data-ttu-id="8208b-138">XSD ベース PIP のインポート</span><span class="sxs-lookup"><span data-stu-id="8208b-138">Importing an XSD-based PIP</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/importing-an-xsd-based-pip.md)