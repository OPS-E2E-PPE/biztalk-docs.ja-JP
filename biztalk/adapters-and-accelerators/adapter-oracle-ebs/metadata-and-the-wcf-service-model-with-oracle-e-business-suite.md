---
title: "メタデータと、WCF サービスの Oracle E-business Suite でモデル |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 95d3fcba-c72f-4ae9-82bd-abbfc2a0c2c4
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7cf87c0a579d1f0c0de590d78e559ead73be0cec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="metadata-and-the-wcf-service-model-with-oracle-e-business-suite"></a><span data-ttu-id="e1236-102">メタデータおよび Oracle E-business Suite では、WCF サービスのモデル</span><span class="sxs-lookup"><span data-stu-id="e1236-102">Metadata and the WCF Service Model with Oracle E-Business Suite</span></span>
<span data-ttu-id="e1236-103">WCF サービス モデルで使用して、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または、ServiceModel メタデータ ユーティリティ ツール (svcutile.exe) を次を行うには。</span><span class="sxs-lookup"><span data-stu-id="e1236-103">In the WCF service model, you use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutile.exe) to do the following:</span></span>  
  
-   <span data-ttu-id="e1236-104">サービス コントラクトを生成します: WCF サービス コントラクト: 使用する、コードは、アダプターから操作を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="e1236-104">Generate a service contract—the WCF service contract—through which your code can receive operations from the adapter.</span></span> <span data-ttu-id="e1236-105">この .NET インターフェイスは、操作を指定のサービス コントラクトを表します。</span><span class="sxs-lookup"><span data-stu-id="e1236-105">This .NET interface represents the service contract for target operations.</span></span>  
  
-   <span data-ttu-id="e1236-106">プロキシ クラスを生成: WCF クライアント クラス — 使用されるコードが、アダプターでの操作を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="e1236-106">Generate proxy classes—the WCF client class—through which your code can invoke operations on the adapter.</span></span>  
  
-   <span data-ttu-id="e1236-107">サポートのメッセージ コントラクト、操作コントラクトおよびサービス コントラクト用のデータ コントラクトを表す注釈付きのクラスです。</span><span class="sxs-lookup"><span data-stu-id="e1236-107">Annotated classes that represent the supporting message contracts, operation contracts, and data contracts for the service contract.</span></span>  
  
 <span data-ttu-id="e1236-108">生成されたこの構造についてのヘルプのコードを参照してください「生成されたクライアント コードを理解する」で[http://go.microsoft.com/fwlink/?LinkId=98365](http://go.microsoft.com/fwlink/?LinkId=98365)です。</span><span class="sxs-lookup"><span data-stu-id="e1236-108">For help in understanding the structure of this generated code, see "Understanding Generated Client Code" at [http://go.microsoft.com/fwlink/?LinkId=98365](http://go.microsoft.com/fwlink/?LinkId=98365).</span></span> <span data-ttu-id="e1236-109">このトピックでは、コード svcutil.exe が生成されますが、そのコンテンツがコードに該当するも特にについて説明する、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]が生成されます。</span><span class="sxs-lookup"><span data-stu-id="e1236-109">This topic specifically describes code that svcutil.exe generates, but its content is also applicable to the code that the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] generates.</span></span>  
  
 <span data-ttu-id="e1236-110">WCF クライアント クラスまたはターゲットの操作のための WCF サービス コントラクトを生成する方法の詳細および svcutil.exe の相違点について、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください[Oracle E-business の WCF クライアントまたは WCF サービス コントラクトを生成Suite ソリューションの成果物](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)です。</span><span class="sxs-lookup"><span data-stu-id="e1236-110">For information about how to generate a WCF client class or WCF service contract for target operations and about the differences between svcutil.exe and the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], see [Generate a WCF Client or a WCF Service Contract for Oracle E-Business Suite Solution Artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1236-111">参照</span><span class="sxs-lookup"><span data-stu-id="e1236-111">See Also</span></span>  
 [<span data-ttu-id="e1236-112">WCF サービス モデルを使用して Oracle E-business Suite アプリケーションの開発します。</span><span class="sxs-lookup"><span data-stu-id="e1236-112">Develop Oracle E-Business Suite Applications by Using the WCF service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)