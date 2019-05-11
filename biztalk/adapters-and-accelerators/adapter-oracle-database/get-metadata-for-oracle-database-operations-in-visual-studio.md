---
title: Visual Studio での Oracle データベース操作のメタデータを取得 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- metadata, retrieving in Visual Studio
- metadata
ms.assetid: d903b408-1144-4625-909d-710826e37769
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2c563d635c3f303cca800feef6c703de67002b9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376572"
---
# <a name="get-metadata-for-oracle-database-operations-in-visual-studio"></a><span data-ttu-id="ee5a6-102">Visual Studio での Oracle データベース操作のメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="ee5a6-102">Get metadata for Oracle Database operations in Visual Studio</span></span>
<span data-ttu-id="ee5a6-103">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] 3 つ提供[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]アダプターを使用してソリューションを開発するために使用できるコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="ee5a6-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] provides three [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] components that you can use to help you develop solutions using the adapter.</span></span>  
  
- <span data-ttu-id="ee5a6-104">[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]と[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]は BizTalk Server プロジェクトで使用できます。</span><span class="sxs-lookup"><span data-stu-id="ee5a6-104">The [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] and the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] are available in BizTalk Server projects.</span></span> <span data-ttu-id="ee5a6-105">使用する、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] 、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] BizTalk ソリューションのターゲットに操作のメッセージ スキーマ (Xsd) を生成します。</span><span class="sxs-lookup"><span data-stu-id="ee5a6-105">You use the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] and the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] to generate message schemas (XSDs) for operations that you want to target in your BizTalk solution.</span></span> <span data-ttu-id="ee5a6-106">BizTalk server ソリューションの開発に関する詳細については、次を参照してください[Oracle データベース アダプターを使用して開発の BizTalk アプリケーション。](../../adapters-and-accelerators/adapter-oracle-database/develop-biztalk-applications-using-the-oracle-database-adapter.md)</span><span class="sxs-lookup"><span data-stu-id="ee5a6-106">For more information about developing solutions with BizTalk Server, see [Develop BizTalk applications using the Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/develop-biztalk-applications-using-the-oracle-database-adapter.md)</span></span>  
  
- <span data-ttu-id="ee5a6-107">[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]は非 BizTalk プログラミング プロジェクトで使用できます。</span><span class="sxs-lookup"><span data-stu-id="ee5a6-107">The [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] is available in non-BizTalk programming projects.</span></span> <span data-ttu-id="ee5a6-108">使用する、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF サービス モデルを使用してソリューションを開発するときに、WCF クライアント クラスまたは WCF サービスのコールバック インターフェイスを生成します。</span><span class="sxs-lookup"><span data-stu-id="ee5a6-108">You use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to generate a WCF client class or a WCF service callback interface when you develop solutions using the WCF service model.</span></span> <span data-ttu-id="ee5a6-109">WCF サービス モデルを使用したソリューションの開発に関する詳細については、次を参照してください。[開発 Oracle データベースを使用してアプリケーション、WCF サービス モデル](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)します。</span><span class="sxs-lookup"><span data-stu-id="ee5a6-109">For more information about developing solutions with the WCF service model, see [Develop Oracle Database Applications using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md).</span></span>  
  
  <span data-ttu-id="ee5a6-110">これら 3 つすべて[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]コンポーネントで開発を簡略化します。</span><span class="sxs-lookup"><span data-stu-id="ee5a6-110">All these three [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] components simplify development by:</span></span>  
  
- <span data-ttu-id="ee5a6-111">ソリューションで使用する操作を参照および検索は、Microsoft Windows インターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="ee5a6-111">Providing a Microsoft Windows interface through which you can browse and search for operations that you want to use in your solution.</span></span>  
  
- <span data-ttu-id="ee5a6-112">これらの操作のターゲットのアダプターによって公開されているメタデータを取得しています。</span><span class="sxs-lookup"><span data-stu-id="ee5a6-112">Retrieving metadata exposed by the adapter for these target operations.</span></span>  
  
- <span data-ttu-id="ee5a6-113">そのメタデータを変換するには、これによって表されます Web サービス記述言語 (WSDL) ドキュメントとしてアダプターは、ソリューション (BizTalk プロジェクトのメッセージ スキーマを XSD または wcf サービス コントラクトの .NET オブジェクトの表現で使用できる形式にサービス モデル)、プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="ee5a6-113">Converting that metadata, which is expressed as a Web Services Description Language (WSDL) document by the adapter, into a form that you can use in your solution (XSD message schemas for BizTalk projects or a .NET object representation of a service contract for the WCF service model) and adding it to your project.</span></span>  
  
  <span data-ttu-id="ee5a6-114">このセクションでは使用する方法について説明[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="ee5a6-114">This section provides instructions about how to use [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], and [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ee5a6-115">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ee5a6-115">In This Section</span></span>  
  
-   [<span data-ttu-id="ee5a6-116">Consume Adapter Service を使用して Visual Studio での Oracle データベースへの接続します。</span><span class="sxs-lookup"><span data-stu-id="ee5a6-116">Connect to the Oracle Database in Visual Studio using the Consume Adapter Service</span></span>](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio-using-the-consume-adapter-service.md) 
  
-   [<span data-ttu-id="ee5a6-117">参照、検索、および Oracle データベース操作のメタデータを取得</span><span class="sxs-lookup"><span data-stu-id="ee5a6-117">Browse, search, and get metadata for Oracle Database operations</span></span>](../../adapters-and-accelerators/adapter-oracle-database/browse-search-and-get-metadata-for-oracle-database-operations.md)  
  
## <a name="see-also"></a><span data-ttu-id="ee5a6-118">参照</span><span class="sxs-lookup"><span data-stu-id="ee5a6-118">See Also</span></span>  
[<span data-ttu-id="ee5a6-119">Oracle データベース アプリケーションの開発</span><span class="sxs-lookup"><span data-stu-id="ee5a6-119">Develop your Oracle Database applications</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-your-oracle-database-applications.md)