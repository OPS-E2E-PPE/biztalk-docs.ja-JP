---
title: MT MX InfoPath フォームを生成するジェネレーター ユーティリティを形成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 41f2fd51-c492-499b-89aa-1b44ed5c9669
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 438744d534dd8806a708a2eec527569d8451508e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377573"
---
# <a name="form-generator-utility-to-generate-mtmx-infopath-forms"></a><span data-ttu-id="f6db6-102">MT/MX InfoPath フォームを生成するフォーム ジェネレーター ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="f6db6-102">Form Generator Utility to Generate MT/MX InfoPath Forms</span></span>
<span data-ttu-id="f6db6-103">このドキュメントの目的では、生成し、フォーム ジェネレーター ユーティリティを使用して MT と MX InfoPath 2010 のフォームを公開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f6db6-103">The purpose of this document is to explain how to generate and publish MT and MX InfoPath 2010 forms using Form Generator Utility.</span></span> <span data-ttu-id="f6db6-104">これらのフォームがの Message Repair and New Submission の機能によって使用される[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="f6db6-104">These forms are used by the Message Repair and New Submission feature of [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)].</span></span>  
  
 <span data-ttu-id="f6db6-105">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f6db6-105">This section contains:</span></span>  
  
-   [<span data-ttu-id="f6db6-106">サンプルの実装</span><span class="sxs-lookup"><span data-stu-id="f6db6-106">Implementing the Sample</span></span>](../../adapters-and-accelerators/accelerator-swift/implementing-the-sample.md)  
  
-   [<span data-ttu-id="f6db6-107">MT メッセージの例</span><span class="sxs-lookup"><span data-stu-id="f6db6-107">Examples of MT Messages</span></span>](../../adapters-and-accelerators/accelerator-swift/examples-of-mt-messages.md)  
  
-   [<span data-ttu-id="f6db6-108">カテゴリ 0 と MT121 フォームの生成</span><span class="sxs-lookup"><span data-stu-id="f6db6-108">Generating Category 0 and MT121 Forms</span></span>](../../adapters-and-accelerators/accelerator-swift/generating-category-0-and-mt121-forms.md)  
  
-   [<span data-ttu-id="f6db6-109">MX メッセージの例</span><span class="sxs-lookup"><span data-stu-id="f6db6-109">Examples of MX Messages</span></span>](../../adapters-and-accelerators/accelerator-swift/examples-of-mx-messages.md)  
  
-   [<span data-ttu-id="f6db6-110">MT/MX フォームを生成して SharePoint サイトに発行する</span><span class="sxs-lookup"><span data-stu-id="f6db6-110">Generating and Publishing MT/MX Forms on the SharePoint Site</span></span>](../../adapters-and-accelerators/accelerator-swift/generating-and-publishing-mt-mx-forms-on-the-sharepoint-site.md)  
  
-   [<span data-ttu-id="f6db6-111">MT メッセージ インスタンス ファイルの発行 (新しいメッセージの作成)</span><span class="sxs-lookup"><span data-stu-id="f6db6-111">Publishing the MT Message Instance File (Creating New Messages)</span></span>](../../adapters-and-accelerators/accelerator-swift/publishing-the-mt-message-instance-file-creating-new-messages.md)  
  
-   [<span data-ttu-id="f6db6-112">MX メッセージ インスタンス ファイルの発行 (新しいメッセージの作成)</span><span class="sxs-lookup"><span data-stu-id="f6db6-112">Publishing the MX Message Instance File (Creating New Messages)</span></span>](../../adapters-and-accelerators/accelerator-swift/publishing-the-mx-message-instance-file-creating-new-messages.md)  
  
-   [<span data-ttu-id="f6db6-113">MX InfoPath フォームの複数のビュー</span><span class="sxs-lookup"><span data-stu-id="f6db6-113">Multiple Views of MX InfoPath forms</span></span>](../../adapters-and-accelerators/accelerator-swift/multiple-views-of-mx-infopath-forms.md)