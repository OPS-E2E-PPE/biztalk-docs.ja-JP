---
title: メタデータと、WCF サービス モデルで SAP |Microsoft Docs
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
ms.openlocfilehash: f120d2d93dcfe56595c020a4032c4d714afc5c90
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373191"
---
# <a name="metadata-and-the-wcf-service-model-with-sap"></a><span data-ttu-id="1e24b-102">メタデータと SAP を含む WCF サービス モデル</span><span class="sxs-lookup"><span data-stu-id="1e24b-102">Metadata and the WCF Service Model with SAP</span></span>
<span data-ttu-id="1e24b-103">WCF サービス モデルを使用して、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または、ServiceModel メタデータ ユーティリティ ツール (svcutile.exe) プロキシ クラスを生成するコードでは使用できますか。</span><span class="sxs-lookup"><span data-stu-id="1e24b-103">In the WCF service model, you use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].or the ServiceModel Metadata Utility Tool (svcutile.exe) to generate proxy classes through which your code can either:</span></span>  
  
- <span data-ttu-id="1e24b-104">操作 (WCF クライアント クラス) のアダプターを呼び出す</span><span class="sxs-lookup"><span data-stu-id="1e24b-104">Invoke operations on the adapter (a WCF client class)</span></span>  
  
- <span data-ttu-id="1e24b-105">受信アダプター (WCF サービス コントラクト) からの操作</span><span class="sxs-lookup"><span data-stu-id="1e24b-105">Receive operations from the adapter (a WCF service contract)</span></span>  
  
  <span data-ttu-id="1e24b-106">これらのツールによって公開されているメタデータからのターゲットの操作 (だけでなく、サポートのメッセージ コントラクト、操作コントラクト、およびデータ コントラクト) のサービス コントラクトを表す .NET クラスの生成、[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="1e24b-106">These tools generate .NET classes that represent a service contract for target operations (as well as the supporting message contracts, operation contracts, and data contracts) from the metadata exposed by the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)].</span></span> <span data-ttu-id="1e24b-107">この生成されたコードの構造を理解したり、次を参照してください。[生成されたクライアント コードを理解する](https://msdn.microsoft.com/library/ms733881.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="1e24b-107">For help in understanding the structure of this generated code, see [Understanding Generated Client Code](https://msdn.microsoft.com/library/ms733881.aspx).</span></span> <span data-ttu-id="1e24b-108">このトピックでは、svcutil.exe が生成されますが、そのコンテンツがコードに該当するものコードを具体的に説明する[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]が生成されます。</span><span class="sxs-lookup"><span data-stu-id="1e24b-108">This topic specifically describes code that svcutil.exe generates, but its content is also applicable to the code that the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] generates.</span></span> <span data-ttu-id="1e24b-109">WCF クライアント クラスまたは WCF サービス コントラクト (インターフェイス) のターゲットの操作を生成する方法について、および svcutil.exe の相違点について、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください[for SAP の WCF クライアントまたは WCF サービス コントラクトの生成ソリューションの成果物](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)します。</span><span class="sxs-lookup"><span data-stu-id="1e24b-109">For information about how to generate a WCF client class or WCF service contract (interface) for target operations and about the differences between svcutil.exe and the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], see [Generate a WCF client or a WCF service contract for SAP solution artifacts](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e24b-110">参照</span><span class="sxs-lookup"><span data-stu-id="1e24b-110">See Also</span></span>  
[<span data-ttu-id="1e24b-111">WCF サービス モデルを使用して SAP アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="1e24b-111">Develop SAP applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)