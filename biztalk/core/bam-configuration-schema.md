---
title: BAM 構成スキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [BAM], scaling
- scaling, BAM
- BAM, scaling
- configuration schema [BAM]
ms.assetid: 7eeeb07f-012e-44eb-a8b5-06e374946e2d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4ece27da0bdbfe43981add9d7f39aeb0ba7a89e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358602"
---
# <a name="bam-configuration-schema"></a><span data-ttu-id="d12d6-102">BAM 構成スキーマ</span><span class="sxs-lookup"><span data-stu-id="d12d6-102">BAM Configuration Schema</span></span>
<span data-ttu-id="d12d6-103">BAM 構成スキーマは、インフラストラクチャに関する情報を含む XML ドキュメントを定義しており、BAM マネージャー ユーティリティでは、この情報を展開に使用します。</span><span class="sxs-lookup"><span data-stu-id="d12d6-103">The BAM configuration schema defines an XML document that contains information about your infrastructure that the BAM Manager Utility uses for deployment.</span></span> <span data-ttu-id="d12d6-104">データベースを複数のサーバーに展開して、スケーラビリティを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="d12d6-104">You can deploy your databases to multiple servers for scalability.</span></span> <span data-ttu-id="d12d6-105">このスケーラビリティをサポートするには、BAM 構成 XML ドキュメントに、複数のサーバー名と次のデータベースの構成設定を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="d12d6-105">To support this scalability, ensure that the BAM configuration XML document contains the different server names and configuration settings for the following databases:</span></span>  
  
-   <span data-ttu-id="d12d6-106">BAMPrimaryImport</span><span class="sxs-lookup"><span data-stu-id="d12d6-106">BAMPrimaryImport</span></span>  
  
-   <span data-ttu-id="d12d6-107">BAMStarSchema</span><span class="sxs-lookup"><span data-stu-id="d12d6-107">BAMStarSchema</span></span>  
  
-   <span data-ttu-id="d12d6-108">BAMAnalysis</span><span class="sxs-lookup"><span data-stu-id="d12d6-108">BAMAnalysis</span></span>  
  
-   <span data-ttu-id="d12d6-109">BAMArchive</span><span class="sxs-lookup"><span data-stu-id="d12d6-109">BAMArchive</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d12d6-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d12d6-110">In This Section</span></span>  
  
-   [<span data-ttu-id="d12d6-111">BAM DTS パッケージ</span><span class="sxs-lookup"><span data-stu-id="d12d6-111">BAM DTS Packages</span></span>](../core/bam-dts-packages.md)  
  
## <a name="see-also"></a><span data-ttu-id="d12d6-112">参照</span><span class="sxs-lookup"><span data-stu-id="d12d6-112">See Also</span></span>  
 [<span data-ttu-id="d12d6-113">BAM ランタイムの設定の変更</span><span class="sxs-lookup"><span data-stu-id="d12d6-113">Changing BAM Runtime Settings</span></span>](../core/changing-bam-runtime-settings.md)