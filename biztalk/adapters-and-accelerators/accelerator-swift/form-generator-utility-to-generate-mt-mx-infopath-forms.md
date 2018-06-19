---
title: MT MX InfoPath フォームを生成するジェネレーター ユーティリティを形成 |Microsoft ドキュメント
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
ms.openlocfilehash: 1f85780b8c72f14d630871c98e10f9f85798aa53
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209210"
---
# <a name="form-generator-utility-to-generate-mtmx-infopath-forms"></a><span data-ttu-id="26901-102">MT/MX InfoPath フォームを生成するフォーム ジェネレーター ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="26901-102">Form Generator Utility to Generate MT/MX InfoPath Forms</span></span>
<span data-ttu-id="26901-103">このドキュメントの目的は、生成し、フォーム ジェネレーター ユーティリティを使用して、MT と MX InfoPath 2010 のフォームを公開する方法について説明です。</span><span class="sxs-lookup"><span data-stu-id="26901-103">The purpose of this document is to explain how to generate and publish MT and MX InfoPath 2010 forms using Form Generator Utility.</span></span> <span data-ttu-id="26901-104">これらの形式は、機能により使用される、Message Repair and New Submission の[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="26901-104">These forms are used by the Message Repair and New Submission feature of [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)].</span></span>  
  
 <span data-ttu-id="26901-105">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="26901-105">This section contains:</span></span>  
  
-   [<span data-ttu-id="26901-106">このサンプルを実装します。</span><span class="sxs-lookup"><span data-stu-id="26901-106">Implementing the Sample</span></span>](../../adapters-and-accelerators/accelerator-swift/implementing-the-sample.md)  
  
-   [<span data-ttu-id="26901-107">MT メッセージの例</span><span class="sxs-lookup"><span data-stu-id="26901-107">Examples of MT Messages</span></span>](../../adapters-and-accelerators/accelerator-swift/examples-of-mt-messages.md)  
  
-   [<span data-ttu-id="26901-108">0 のカテゴリと MT121 フォームを生成します。</span><span class="sxs-lookup"><span data-stu-id="26901-108">Generating Category 0 and MT121 Forms</span></span>](../../adapters-and-accelerators/accelerator-swift/generating-category-0-and-mt121-forms.md)  
  
-   [<span data-ttu-id="26901-109">MX メッセージの例</span><span class="sxs-lookup"><span data-stu-id="26901-109">Examples of MX Messages</span></span>](../../adapters-and-accelerators/accelerator-swift/examples-of-mx-messages.md)  
  
-   [<span data-ttu-id="26901-110">生成して、SharePoint サイトで MT/MX フォームの発行</span><span class="sxs-lookup"><span data-stu-id="26901-110">Generating and Publishing MT/MX Forms on the SharePoint Site</span></span>](../../adapters-and-accelerators/accelerator-swift/generating-and-publishing-mt-mx-forms-on-the-sharepoint-site.md)  
  
-   [<span data-ttu-id="26901-111">(新しいメッセージの作成) MT メッセージ インスタンスのファイルの発行</span><span class="sxs-lookup"><span data-stu-id="26901-111">Publishing the MT Message Instance File (Creating New Messages)</span></span>](../../adapters-and-accelerators/accelerator-swift/publishing-the-mt-message-instance-file-creating-new-messages.md)  
  
-   [<span data-ttu-id="26901-112">(新しいメッセージの作成) MX メッセージ インスタンスのファイルの発行</span><span class="sxs-lookup"><span data-stu-id="26901-112">Publishing the MX Message Instance File (Creating New Messages)</span></span>](../../adapters-and-accelerators/accelerator-swift/publishing-the-mx-message-instance-file-creating-new-messages.md)  
  
-   [<span data-ttu-id="26901-113">複数のビューの MX InfoPath フォーム</span><span class="sxs-lookup"><span data-stu-id="26901-113">Multiple Views of MX InfoPath forms</span></span>](../../adapters-and-accelerators/accelerator-swift/multiple-views-of-mx-infopath-forms.md)