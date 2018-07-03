---
title: メタデータと、WCF サービスの Oracle Database によるモデル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service model, metadata
- WCF client class
- WCF service contract
ms.assetid: b55cf4ed-c41a-4986-bbaf-88e80c32b01f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3b1c3eed2ab71282a50ccbb6709601aa69ca733
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973299"
---
# <a name="metadata-and-the-wcf-service-model-with-oracle-database"></a><span data-ttu-id="661e5-102">メタデータと Oracle Database による WCF サービス モデル</span><span class="sxs-lookup"><span data-stu-id="661e5-102">Metadata and the WCF Service Model with Oracle Database</span></span>
<span data-ttu-id="661e5-103">WCF サービス モデルを使用して、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または、ServiceModel メタデータ ユーティリティ ツール (svcutile.exe) プロキシ クラスを生成するコードでは使用できますか。</span><span class="sxs-lookup"><span data-stu-id="661e5-103">In the WCF service model, you use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].or the ServiceModel Metadata Utility Tool (svcutile.exe) to generate proxy classes through which your code can either:</span></span>  
  
- <span data-ttu-id="661e5-104">操作 (WCF クライアント クラス) のアダプターを呼び出す</span><span class="sxs-lookup"><span data-stu-id="661e5-104">Invoke operations on the adapter (a WCF client class)</span></span>  
  
- <span data-ttu-id="661e5-105">受信アダプター (WCF サービス コントラクト) からの操作</span><span class="sxs-lookup"><span data-stu-id="661e5-105">Receive operations from the adapter (a WCF service contract)</span></span>  
  
  <span data-ttu-id="661e5-106">これらのツールによって公開されているメタデータからのターゲットの操作 (だけでなく、サポートのメッセージ コントラクト、操作コントラクト、およびデータ コントラクト) のサービス コントラクトを表す .NET クラスの生成、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="661e5-106">These tools generate .NET classes that represent a service contract for target operations (as well as the supporting message contracts, operation contracts, and data contracts) from the metadata exposed by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="661e5-107">生成されたこの構造を理解したりコードは、「生成されたクライアント コードを理解する」をご覧[ http://go.microsoft.com/fwlink/?LinkId=98365](http://go.microsoft.com/fwlink/?LinkId=98365)します。</span><span class="sxs-lookup"><span data-stu-id="661e5-107">For help in understanding the structure of this generated code, see "Understanding Generated Client Code" at [http://go.microsoft.com/fwlink/?LinkId=98365](http://go.microsoft.com/fwlink/?LinkId=98365).</span></span> <span data-ttu-id="661e5-108">このトピックでは、svcutil.exe が生成されますが、そのコンテンツがコードに該当するものコードを具体的に説明する[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]が生成されます。</span><span class="sxs-lookup"><span data-stu-id="661e5-108">This topic specifically describes code that svcutil.exe generates, but its content is also applicable to the code that the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] generates.</span></span> <span data-ttu-id="661e5-109">WCF クライアント クラスまたはターゲットの操作のための WCF サービス コントラクトを生成する方法について、および svcutil.exe の相違点について、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください[Oracle データベースの WCF クライアントまたは WCF サービス コントラクトを生成します。ソリューションの成果物](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)します。</span><span class="sxs-lookup"><span data-stu-id="661e5-109">For information about how to generate a WCF client class or WCF service contract for target operations and about the differences between svcutil.exe and the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], see [Generate a WCF Client or a WCF Service Contract for Oracle Database Solution Artifacts](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="661e5-110">参照</span><span class="sxs-lookup"><span data-stu-id="661e5-110">See Also</span></span>  
 [<span data-ttu-id="661e5-111">WCF サービス モデルを使用して Oracle データベースのアプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="661e5-111">Develop Oracle Database Applications by Using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)