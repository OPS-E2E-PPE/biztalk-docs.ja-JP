---
title: メタデータと、WCF サービス モデルで Siebel |Microsoft Docs
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
ms.openlocfilehash: bb47a69efc6522eb6868ce2ecda5c608d2652c99
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752786"
---
# <a name="metadata-and-the-wcf-service-model-with-siebel"></a><span data-ttu-id="1c407-102">メタデータと Siebel と WCF サービス モデル</span><span class="sxs-lookup"><span data-stu-id="1c407-102">Metadata and the WCF Service Model with Siebel</span></span>
<span data-ttu-id="1c407-103">WCF サービス モデルを使用して、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]またはプロキシ クラスを生成する ServiceModel メタデータ ユーティリティ ツール (svcutile.exe): WCF クライアント クラス-するコードは操作を呼び出してから、 [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1c407-103">In the WCF service model, you use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutile.exe) to generate a proxy class—the WCF client class—through which your code can invoke operations on the [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)].</span></span>  
  
 <span data-ttu-id="1c407-104">これらのツールでは、アダプターによって公開されているメタデータを使用して、生成します。</span><span class="sxs-lookup"><span data-stu-id="1c407-104">These tools use the metadata exposed by the adapter to generate:</span></span>  
  
- <span data-ttu-id="1c407-105">ターゲットのサービス コントラクトを表す注釈付き .NET インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="1c407-105">An annotated .NET interface that represents the service contract for target operations.</span></span> <span data-ttu-id="1c407-106">このインターフェイスは、WCF サービス コントラクトと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="1c407-106">This interface is called the WCF service contract.</span></span>  
  
- <span data-ttu-id="1c407-107">サポートのメッセージ コントラクト、操作のコントラクト、およびサービス コントラクト用のデータ コントラクトを表す注釈クラス。</span><span class="sxs-lookup"><span data-stu-id="1c407-107">Annotated classes that represent the supporting message contracts, operation contracts, and data contracts for the service contract.</span></span>  
  
- <span data-ttu-id="1c407-108">WCF クライアント クラス メソッドを持つ WCF サービス コントラクトによって公開されているサービス メソッド (操作) の呼び出しに使用できます。</span><span class="sxs-lookup"><span data-stu-id="1c407-108">A WCF client class whose methods can be used to invoke the service methods (operations) exposed by the WCF service contract.</span></span>  
  
  <span data-ttu-id="1c407-109">生成されたこの構造を理解したりコードは、「生成されたクライアント コードを理解する」をご覧[ http://go.microsoft.com/fwlink/?LinkId=98365](http://go.microsoft.com/fwlink/?LinkId=98365)します。</span><span class="sxs-lookup"><span data-stu-id="1c407-109">For help in understanding the structure of this generated code, see "Understanding Generated Client Code" at [http://go.microsoft.com/fwlink/?LinkId=98365](http://go.microsoft.com/fwlink/?LinkId=98365).</span></span> <span data-ttu-id="1c407-110">このトピックでは、svcutil.exe が生成されますが、そのコンテンツがコードに該当するものコードを具体的に説明する[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]が生成されます。</span><span class="sxs-lookup"><span data-stu-id="1c407-110">This topic specifically describes code that svcutil.exe generates, but its content is also applicable to the code that the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] generates.</span></span>  
  
  <span data-ttu-id="1c407-111">操作の対象の WCF クライアント クラスを生成する方法について、および svcutil.exe の相違点について、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください[WCF クライアントまたは Siebel ソリューションの成果物の WCF サービス コントラクトの生成](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md)</span><span class="sxs-lookup"><span data-stu-id="1c407-111">For information about how to generate a WCF client class for target operations and about the differences between svcutil.exe and the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], see [Generate a WCF Client or a WCF service contract for Siebel solution Artifacts](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c407-112">参照</span><span class="sxs-lookup"><span data-stu-id="1c407-112">See Also</span></span>  
 [<span data-ttu-id="1c407-113">WCF サービス モデルを使用して Siebel アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="1c407-113">Develop Siebel applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md)
