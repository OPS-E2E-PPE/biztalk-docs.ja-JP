---
title: メタデータと、WCF サービスの Siebel 使用モデルの |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model, metadata
- metadata, and the WCF service model
ms.assetid: 3aca1835-fb9e-4841-a920-078da0b3fe76
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed348c2ab183960b7af1383768259f67c4ca6270
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22221898"
---
# <a name="metadata-and-the-wcf-service-model-with-siebel"></a><span data-ttu-id="ed730-102">メタデータと Siebel で WCF サービスのモデル</span><span class="sxs-lookup"><span data-stu-id="ed730-102">Metadata and the WCF Service Model with Siebel</span></span>
<span data-ttu-id="ed730-103">使用する WCF サービス モデルで、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または、ServiceModel メタデータ ユーティリティ ツール (svcutile.exe) プロキシ クラスを生成する: WCF クライアント クラス — をコードできます操作の呼び出しで使用、[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ed730-103">In the WCF service model, you use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutile.exe) to generate a proxy class—the WCF client class—through which your code can invoke operations on the [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)].</span></span>  
  
 <span data-ttu-id="ed730-104">これらのツールでは、アダプターによって公開されるメタデータを使用して、生成します。</span><span class="sxs-lookup"><span data-stu-id="ed730-104">These tools use the metadata exposed by the adapter to generate:</span></span>  
  
-   <span data-ttu-id="ed730-105">ターゲットのサービス コントラクトを表す注釈付き .NET インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="ed730-105">An annotated .NET interface that represents the service contract for target operations.</span></span> <span data-ttu-id="ed730-106">このインターフェイスは、WCF サービス コントラクトと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="ed730-106">This interface is called the WCF service contract.</span></span>  
  
-   <span data-ttu-id="ed730-107">サポートのメッセージ コントラクト、操作コントラクトおよびサービス コントラクト用のデータ コントラクトを表す注釈付きのクラスです。</span><span class="sxs-lookup"><span data-stu-id="ed730-107">Annotated classes that represent the supporting message contracts, operation contracts, and data contracts for the service contract.</span></span>  
  
-   <span data-ttu-id="ed730-108">WCF クライアント クラスを WCF サービス コントラクトによって公開されるサービスのメソッド (操作) を呼び出すメソッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ed730-108">A WCF client class whose methods can be used to invoke the service methods (operations) exposed by the WCF service contract.</span></span>  
  
 <span data-ttu-id="ed730-109">生成されたこの構造についてのヘルプのコードを参照してください「生成されたクライアント コードを理解する」で[http://go.microsoft.com/fwlink/?LinkId=98365](http://go.microsoft.com/fwlink/?LinkId=98365)です。</span><span class="sxs-lookup"><span data-stu-id="ed730-109">For help in understanding the structure of this generated code, see "Understanding Generated Client Code" at [http://go.microsoft.com/fwlink/?LinkId=98365](http://go.microsoft.com/fwlink/?LinkId=98365).</span></span> <span data-ttu-id="ed730-110">このトピックでは、コード svcutil.exe が生成されますが、そのコンテンツがコードに該当するも特にについて説明する、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]が生成されます。</span><span class="sxs-lookup"><span data-stu-id="ed730-110">This topic specifically describes code that svcutil.exe generates, but its content is also applicable to the code that the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] generates.</span></span>  
  
 <span data-ttu-id="ed730-111">ターゲットの WCF クライアント クラスを生成する方法の詳細および svcutil.exe の相違点について、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください[WCF クライアントまたは WCF サービス コントラクトを Siebel ソリューションの成果物の生成](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md)</span><span class="sxs-lookup"><span data-stu-id="ed730-111">For information about how to generate a WCF client class for target operations and about the differences between svcutil.exe and the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], see [Generate a WCF Client or a WCF service contract for for Siebel solution Artifacts](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed730-112">参照</span><span class="sxs-lookup"><span data-stu-id="ed730-112">See Also</span></span>  
 [<span data-ttu-id="ed730-113">WCF サービス モデルを使用して Siebel アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="ed730-113">Develop Siebel applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md)