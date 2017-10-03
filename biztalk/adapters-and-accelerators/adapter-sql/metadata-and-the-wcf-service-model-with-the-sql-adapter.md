---
title: "メタデータと、SQL アダプターで WCF サービス モデル |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4353ce67-f0e8-4f96-b1d9-95deeee7f3e6
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c95ed3188c01f0f6d568bd745decd9e601e6ee3b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="metadata-and-the-wcf-service-model-with-the-sql-adapter"></a><span data-ttu-id="8cb05-102">メタデータと、SQL アダプターで WCF サービス モデル</span><span class="sxs-lookup"><span data-stu-id="8cb05-102">Metadata and the WCF Service Model with the SQL adapter</span></span>
<span data-ttu-id="8cb05-103">WCF サービス モデルで使用して、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または、ServiceModel メタデータ ユーティリティ ツール (svcutile.exe) を次を行うには。</span><span class="sxs-lookup"><span data-stu-id="8cb05-103">In the WCF service model, you use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutile.exe) to do the following:</span></span>  
  
-   <span data-ttu-id="8cb05-104">サービス コントラクトを生成します: WCF サービス コントラクト: 使用する、コードは、アダプターから操作を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="8cb05-104">Generate a service contract—the WCF service contract—through which your code can receive operations from the adapter.</span></span> <span data-ttu-id="8cb05-105">この .NET インターフェイスは、操作を指定のサービス コントラクトを表します。</span><span class="sxs-lookup"><span data-stu-id="8cb05-105">This .NET interface represents the service contract for target operations.</span></span>  
  
-   <span data-ttu-id="8cb05-106">プロキシ クラスを生成: WCF クライアント クラス — 使用されるコードが、アダプターでの操作を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="8cb05-106">Generate proxy classes—the WCF client class—through which your code can invoke operations on the adapter.</span></span>  
  
-   <span data-ttu-id="8cb05-107">サポートのメッセージ コントラクト、操作コントラクトおよびサービス コントラクト用のデータ コントラクトを表す注釈付きのクラスです。</span><span class="sxs-lookup"><span data-stu-id="8cb05-107">Annotated classes that represent the supporting message contracts, operation contracts, and data contracts for the service contract.</span></span>  
  
 <span data-ttu-id="8cb05-108">ヘルプについては、この生成されたコードの構造を理解するうえで、次を参照してください。[生成されたクライアント コードを理解する](https://msdn.microsoft.com/library/ms733881.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="8cb05-108">For help in understanding the structure of this generated code, see [Understanding Generated Client Code](https://msdn.microsoft.com/library/ms733881.aspx).</span></span> <span data-ttu-id="8cb05-109">このトピックでは、コード svcutil.exe が生成されますが、そのコンテンツがコードに該当するも特にについて説明する、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]が生成されます。</span><span class="sxs-lookup"><span data-stu-id="8cb05-109">This topic specifically describes code that svcutil.exe generates, but its content is also applicable to the code that the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] generates.</span></span>  
  
 <span data-ttu-id="8cb05-110">WCF クライアント クラスまたはターゲットの操作のための WCF サービス コントラクトを生成する方法の詳細および svcutil.exe の相違点について、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください[SQL Server の成果物のために、WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="8cb05-110">For information about how to generate a WCF client class or WCF service contract for target operations and about the differences between svcutil.exe and the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cb05-111">参照</span><span class="sxs-lookup"><span data-stu-id="8cb05-111">See Also</span></span>  
[<span data-ttu-id="8cb05-112">WCF サービス モデルを使用して SQL アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="8cb05-112">Develop SQL applications using the WCF Service model</span></span>](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)