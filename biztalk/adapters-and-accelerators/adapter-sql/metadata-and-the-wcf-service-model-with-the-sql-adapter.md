---
title: メタデータと、SQL アダプターで WCF サービス モデル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4353ce67-f0e8-4f96-b1d9-95deeee7f3e6
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a046615fb458991f51784f1059de609d1b3c73a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368721"
---
# <a name="metadata-and-the-wcf-service-model-with-the-sql-adapter"></a><span data-ttu-id="5166f-102">メタデータと、SQL アダプターで WCF サービス モデル</span><span class="sxs-lookup"><span data-stu-id="5166f-102">Metadata and the WCF Service Model with the SQL adapter</span></span>
<span data-ttu-id="5166f-103">WCF サービス モデルを使用して、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または、以下の ServiceModel メタデータ ユーティリティ ツール (svcutile.exe)。</span><span class="sxs-lookup"><span data-stu-id="5166f-103">In the WCF service model, you use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutile.exe) to do the following:</span></span>  
  
- <span data-ttu-id="5166f-104">サービス コントラクトの生成: WCF サービス コントラクト: により、コードは、アダプターから操作を受信できます。</span><span class="sxs-lookup"><span data-stu-id="5166f-104">Generate a service contract—the WCF service contract—through which your code can receive operations from the adapter.</span></span> <span data-ttu-id="5166f-105">この .NET インターフェイスでは、ターゲットのサービス コントラクトを表します。</span><span class="sxs-lookup"><span data-stu-id="5166f-105">This .NET interface represents the service contract for target operations.</span></span>  
  
- <span data-ttu-id="5166f-106">プロキシ クラスを生成、WCF クライアント クラス-コードにより、アダプターでの操作を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="5166f-106">Generate proxy classes—the WCF client class—through which your code can invoke operations on the adapter.</span></span>  
  
- <span data-ttu-id="5166f-107">サポートのメッセージ コントラクト、操作のコントラクト、およびサービス コントラクト用のデータ コントラクトを表す注釈クラス。</span><span class="sxs-lookup"><span data-stu-id="5166f-107">Annotated classes that represent the supporting message contracts, operation contracts, and data contracts for the service contract.</span></span>  
  
  <span data-ttu-id="5166f-108">この生成されたコードの構造を理解したり、次を参照してください。[生成されたクライアント コードを理解する](https://msdn.microsoft.com/library/ms733881.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="5166f-108">For help in understanding the structure of this generated code, see [Understanding Generated Client Code](https://msdn.microsoft.com/library/ms733881.aspx).</span></span> <span data-ttu-id="5166f-109">このトピックでは、svcutil.exe が生成されますが、そのコンテンツがコードに該当するものコードを具体的に説明する[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]が生成されます。</span><span class="sxs-lookup"><span data-stu-id="5166f-109">This topic specifically describes code that svcutil.exe generates, but its content is also applicable to the code that the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] generates.</span></span>  
  
  <span data-ttu-id="5166f-110">WCF クライアント クラスまたはターゲットの操作のための WCF サービス コントラクトを生成する方法について、および svcutil.exe の相違点について、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください[SQL Server のアイテムの WCF クライアントまたは WCF サービス コントラクトを生成します。](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="5166f-110">For information about how to generate a WCF client class or WCF service contract for target operations and about the differences between svcutil.exe and the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5166f-111">参照</span><span class="sxs-lookup"><span data-stu-id="5166f-111">See Also</span></span>  
[<span data-ttu-id="5166f-112">WCF サービス モデルを使用して SQL アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="5166f-112">Develop SQL applications using the WCF Service model</span></span>](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)