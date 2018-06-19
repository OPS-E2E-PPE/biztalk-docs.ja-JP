---
title: メタデータと、WCF サービスの SAP とモデル |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1900cf66-a0d0-46f4-896b-7f6de3b51875
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f06cd33c0776df70e5ff2554d355915908012abb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216778"
---
# <a name="metadata-and-the-wcf-service-model-with-sap"></a><span data-ttu-id="2f044-102">メタデータと SAP と WCF サービスのモデル</span><span class="sxs-lookup"><span data-stu-id="2f044-102">Metadata and the WCF Service Model with SAP</span></span>
<span data-ttu-id="2f044-103">WCF サービス モデルで使用して、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または、ServiceModel メタデータ ユーティリティ ツール (svcutile.exe) プロキシ クラス生成に使用するコードはできますか。</span><span class="sxs-lookup"><span data-stu-id="2f044-103">In the WCF service model, you use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].or the ServiceModel Metadata Utility Tool (svcutile.exe) to generate proxy classes through which your code can either:</span></span>  
  
-   <span data-ttu-id="2f044-104">アダプター (WCF クライアント クラス) に対する操作を呼び出す</span><span class="sxs-lookup"><span data-stu-id="2f044-104">Invoke operations on the adapter (a WCF client class)</span></span>  
  
-   <span data-ttu-id="2f044-105">受信アダプター (WCF サービス コントラクト) からの操作</span><span class="sxs-lookup"><span data-stu-id="2f044-105">Receive operations from the adapter (a WCF service contract)</span></span>  
  
 <span data-ttu-id="2f044-106">これらのツールによって公開されるメタデータから操作を指定 (だけでなく、メッセージ コントラクトをサポートする、操作コントラクト、およびデータ コントラクト) のサービス コントラクトを表す .NET クラスを生成する、[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="2f044-106">These tools generate .NET classes that represent a service contract for target operations (as well as the supporting message contracts, operation contracts, and data contracts) from the metadata exposed by the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)].</span></span> <span data-ttu-id="2f044-107">ヘルプについては、この生成されたコードの構造を理解するうえで、次を参照してください。[生成されたクライアント コードを理解する](https://msdn.microsoft.com/library/ms733881.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="2f044-107">For help in understanding the structure of this generated code, see [Understanding Generated Client Code](https://msdn.microsoft.com/library/ms733881.aspx).</span></span> <span data-ttu-id="2f044-108">このトピックでは、コード svcutil.exe が生成されますが、そのコンテンツがコードに該当するも特にについて説明する、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]が生成されます。</span><span class="sxs-lookup"><span data-stu-id="2f044-108">This topic specifically describes code that svcutil.exe generates, but its content is also applicable to the code that the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] generates.</span></span> <span data-ttu-id="2f044-109">WCF クライアント クラスまたは WCF サービス コントラクト (インターフェイス) のターゲットの操作を生成する方法の詳細および svcutil.exe の相違点について、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください[for SAP の WCF クライアントまたは WCF サービス コントラクトの生成ソリューションの成果物](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)です。</span><span class="sxs-lookup"><span data-stu-id="2f044-109">For information about how to generate a WCF client class or WCF service contract (interface) for target operations and about the differences between svcutil.exe and the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], see [Generate a WCF client or a WCF service contract for SAP solution artifacts](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f044-110">参照</span><span class="sxs-lookup"><span data-stu-id="2f044-110">See Also</span></span>  
[<span data-ttu-id="2f044-111">WCF サービス モデルを使用して SAP アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="2f044-111">Develop SAP applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)