---
title: Oracle E-business Suite でのモデルをサービス メタデータと WCF |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 95d3fcba-c72f-4ae9-82bd-abbfc2a0c2c4
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91c698e0083ffc636c21a39e62edd0d9d7a39234
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375374"
---
# <a name="metadata-and-the-wcf-service-model-with-oracle-e-business-suite"></a><span data-ttu-id="36437-102">メタデータと Oracle E-business Suite での WCF サービス モデル</span><span class="sxs-lookup"><span data-stu-id="36437-102">Metadata and the WCF Service Model with Oracle E-Business Suite</span></span>
<span data-ttu-id="36437-103">WCF サービス モデルを使用して、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または、以下の ServiceModel メタデータ ユーティリティ ツール (svcutile.exe)。</span><span class="sxs-lookup"><span data-stu-id="36437-103">In the WCF service model, you use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutile.exe) to do the following:</span></span>  
  
- <span data-ttu-id="36437-104">サービス コントラクトの生成: WCF サービス コントラクト: により、コードは、アダプターから操作を受信できます。</span><span class="sxs-lookup"><span data-stu-id="36437-104">Generate a service contract—the WCF service contract—through which your code can receive operations from the adapter.</span></span> <span data-ttu-id="36437-105">この .NET インターフェイスでは、ターゲットのサービス コントラクトを表します。</span><span class="sxs-lookup"><span data-stu-id="36437-105">This .NET interface represents the service contract for target operations.</span></span>  
  
- <span data-ttu-id="36437-106">プロキシ クラスを生成、WCF クライアント クラス-コードにより、アダプターでの操作を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="36437-106">Generate proxy classes—the WCF client class—through which your code can invoke operations on the adapter.</span></span>  
  
- <span data-ttu-id="36437-107">サポートのメッセージ コントラクト、操作のコントラクト、およびサービス コントラクト用のデータ コントラクトを表す注釈クラス。</span><span class="sxs-lookup"><span data-stu-id="36437-107">Annotated classes that represent the supporting message contracts, operation contracts, and data contracts for the service contract.</span></span>  
  
  <span data-ttu-id="36437-108">生成されたこの構造を理解したりコードは、「生成されたクライアント コードを理解する」をご覧[ http://go.microsoft.com/fwlink/?LinkId=98365](http://go.microsoft.com/fwlink/?LinkId=98365)します。</span><span class="sxs-lookup"><span data-stu-id="36437-108">For help in understanding the structure of this generated code, see "Understanding Generated Client Code" at [http://go.microsoft.com/fwlink/?LinkId=98365](http://go.microsoft.com/fwlink/?LinkId=98365).</span></span> <span data-ttu-id="36437-109">このトピックでは、svcutil.exe が生成されますが、そのコンテンツがコードに該当するものコードを具体的に説明する[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]が生成されます。</span><span class="sxs-lookup"><span data-stu-id="36437-109">This topic specifically describes code that svcutil.exe generates, but its content is also applicable to the code that the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] generates.</span></span>  
  
  <span data-ttu-id="36437-110">WCF クライアント クラスまたはターゲットの操作のための WCF サービス コントラクトを生成する方法について、および svcutil.exe の相違点について、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください[Oracle E-business の WCF クライアントまたは WCF サービス コントラクトを生成Suite ソリューションの成果物](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)します。</span><span class="sxs-lookup"><span data-stu-id="36437-110">For information about how to generate a WCF client class or WCF service contract for target operations and about the differences between svcutil.exe and the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], see [Generate a WCF Client or a WCF Service Contract for Oracle E-Business Suite Solution Artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36437-111">参照</span><span class="sxs-lookup"><span data-stu-id="36437-111">See Also</span></span>  
 [<span data-ttu-id="36437-112">WCF サービス モデルを使用して Oracle E-business Suite のアプリケーションの開発します。</span><span class="sxs-lookup"><span data-stu-id="36437-112">Develop Oracle E-Business Suite Applications by Using the WCF service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)