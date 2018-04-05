---
title: A4SWIFT コンポーネント構成ガイド |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- A4SWIFT, configuration guide
ms.assetid: ff4a3ee7-2fd9-44e7-8aa3-c3d214a6ce68
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 396e28d49b3e6a43e188e8358a045c3c91a627cb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="a4swift-component-configuration-guide"></a><span data-ttu-id="500e9-102">A4SWIFT コンポーネント構成ガイド</span><span class="sxs-lookup"><span data-stu-id="500e9-102">A4SWIFT Component Configuration Guide</span></span>
<span data-ttu-id="500e9-103">このガイドの構成に関する情報を提供する[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="500e9-103">This guide provides information about configuring [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)].</span></span> <span data-ttu-id="500e9-104">A4SWIFT をインストールし、(インストール ガイドで説明)、A4SWIFT 構成ウィザードを完了した後は、この構成ガイドの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="500e9-104">Perform the steps in this configuration guide after you have installed A4SWIFT and completed the A4SWIFT Configuration Wizard (as described in the Installation Guide).</span></span> <span data-ttu-id="500e9-105">この構成のガイドには、次の手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="500e9-105">This configuration guide includes the following instructions:</span></span>  
  
-   <span data-ttu-id="500e9-106">インストール後の手順のメッセージング シナリオ用の A4SWIFT ランタイムを構成します。</span><span class="sxs-lookup"><span data-stu-id="500e9-106">Post-installation steps for configuring the A4SWIFT runtime for messaging scenarios.</span></span>  
  
-   <span data-ttu-id="500e9-107">Message Repair and New Submission を構成する方法。</span><span class="sxs-lookup"><span data-stu-id="500e9-107">How to configure Message Repair and New Submission.</span></span> <span data-ttu-id="500e9-108">これを行うには、する必要がありますまず手動でランタイムを構成する A4SWIFT です。</span><span class="sxs-lookup"><span data-stu-id="500e9-108">To do so, you must first manually configure the A4SWIFT runtime.</span></span> <span data-ttu-id="500e9-109">これは、FIN 対応調整を構成することが必要ではありません。</span><span class="sxs-lookup"><span data-stu-id="500e9-109">This does not require that you configure FIN Response Reconciliation.</span></span>  
  
-   <span data-ttu-id="500e9-110">FIN 対応調整を構成する方法。</span><span class="sxs-lookup"><span data-stu-id="500e9-110">How to configure FIN Response Reconciliation.</span></span> <span data-ttu-id="500e9-111">これを行うには、する必要がありますまず手動でランタイムを構成する A4SWIFT です。</span><span class="sxs-lookup"><span data-stu-id="500e9-111">To do so, you must first manually configure the A4SWIFT runtime.</span></span> <span data-ttu-id="500e9-112">これは、Message Repair and New Submission を構成することが必要ではありません。</span><span class="sxs-lookup"><span data-stu-id="500e9-112">This does not require that you configure Message Repair and New Submission.</span></span>  
  
 <span data-ttu-id="500e9-113">次の図は、構成する A4SWIFT コンポーネントを示しています。</span><span class="sxs-lookup"><span data-stu-id="500e9-113">The following figure shows the A4SWIFT components that you will configure.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-component-configuration.gif "A4SWIFT_Component_Configuration")  
  
 <span data-ttu-id="500e9-114">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="500e9-114">This section contains:</span></span>  
  
-   [<span data-ttu-id="500e9-115">A4SWIFT のランタイムを構成します。</span><span class="sxs-lookup"><span data-stu-id="500e9-115">Configuring the A4SWIFT Runtime</span></span>](../../adapters-and-accelerators/accelerator-swift/configuring-the-a4swift-runtime.md)  
  
-   [<span data-ttu-id="500e9-116">Message Repair and New Submission を構成します。</span><span class="sxs-lookup"><span data-stu-id="500e9-116">Configuring Message Repair and New Submission</span></span>](../../adapters-and-accelerators/accelerator-swift/configuring-message-repair-and-new-submission.md)  
  
-   [<span data-ttu-id="500e9-117">FIN 対応調整を構成します。</span><span class="sxs-lookup"><span data-stu-id="500e9-117">Configuring FIN Response Reconciliation</span></span>](../../adapters-and-accelerators/accelerator-swift/configuring-fin-response-reconciliation.md)