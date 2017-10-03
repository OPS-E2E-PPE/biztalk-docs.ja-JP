---
title: "BAM 構成スキーマ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [BAM], scaling
- scaling, BAM
- BAM, scaling
- configuration schema [BAM]
ms.assetid: 7eeeb07f-012e-44eb-a8b5-06e374946e2d
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b0d73435dc0245c3c3ce2b1574aa5a70b468c60
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="bam-configuration-schema"></a><span data-ttu-id="0994e-102">BAM 構成スキーマ</span><span class="sxs-lookup"><span data-stu-id="0994e-102">BAM Configuration Schema</span></span>
<span data-ttu-id="0994e-103">BAM 構成スキーマは、インフラストラクチャに関する情報を含む XML ドキュメントを定義しており、BAM マネージャー ユーティリティでは、この情報を展開に使用します。</span><span class="sxs-lookup"><span data-stu-id="0994e-103">The BAM configuration schema defines an XML document that contains information about your infrastructure that the BAM Manager Utility uses for deployment.</span></span> <span data-ttu-id="0994e-104">データベースを複数のサーバーに展開して、スケーラビリティを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="0994e-104">You can deploy your databases to multiple servers for scalability.</span></span> <span data-ttu-id="0994e-105">このスケーラビリティをサポートするには、BAM 構成 XML ドキュメントに、複数のサーバー名と次のデータベースの構成設定を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="0994e-105">To support this scalability, ensure that the BAM configuration XML document contains the different server names and configuration settings for the following databases:</span></span>  
  
-   <span data-ttu-id="0994e-106">BAMPrimaryImport</span><span class="sxs-lookup"><span data-stu-id="0994e-106">BAMPrimaryImport</span></span>  
  
-   <span data-ttu-id="0994e-107">BAMStarSchema</span><span class="sxs-lookup"><span data-stu-id="0994e-107">BAMStarSchema</span></span>  
  
-   <span data-ttu-id="0994e-108">BAMAnalysis</span><span class="sxs-lookup"><span data-stu-id="0994e-108">BAMAnalysis</span></span>  
  
-   <span data-ttu-id="0994e-109">BAMArchive</span><span class="sxs-lookup"><span data-stu-id="0994e-109">BAMArchive</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0994e-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="0994e-110">In This Section</span></span>  
  
-   [<span data-ttu-id="0994e-111">BAM DTS パッケージ</span><span class="sxs-lookup"><span data-stu-id="0994e-111">BAM DTS Packages</span></span>](../core/bam-dts-packages.md)  
  
## <a name="see-also"></a><span data-ttu-id="0994e-112">参照</span><span class="sxs-lookup"><span data-stu-id="0994e-112">See Also</span></span>  
 [<span data-ttu-id="0994e-113">BAM ランタイムの設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="0994e-113">Changing BAM Runtime Settings</span></span>](../core/changing-bam-runtime-settings.md)