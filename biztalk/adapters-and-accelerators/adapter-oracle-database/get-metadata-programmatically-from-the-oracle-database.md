---
title: Oracle データベースからプログラムでメタデータの取得 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- metadata, retrieving programmatically from the Oracle database
ms.assetid: 28a55935-6078-41d0-abfa-ac86e9ca8471
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f8f3d6341e0f5d26d589f03dc0b93a3e5b0afa0
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529188"
---
# <a name="get-metadata-programmatically-from-the-oracle-database"></a><span data-ttu-id="c723c-102">Oracle データベースからメタデータをプログラムで取得します。</span><span class="sxs-lookup"><span data-stu-id="c723c-102">Get Metadata Programmatically from the Oracle Database</span></span>
<span data-ttu-id="c723c-103">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] WCF サービスとしての Oracle データベースを公開するカスタム WCF バインドします。</span><span class="sxs-lookup"><span data-stu-id="c723c-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] is a custom WCF binding that exposes an Oracle database as a WCF service.</span></span> <span data-ttu-id="c723c-104">アダプターは、サービスを自己記述型として、Oracle データベースを公開しますサポートされる操作についてのメタデータを公開できるサービスは、します。</span><span class="sxs-lookup"><span data-stu-id="c723c-104">The adapter exposes the Oracle database as a self-describing service; that is, a service that is capable of publishing metadata about the operations that it supports.</span></span> <span data-ttu-id="c723c-105">メタデータが、WCF サービスに論理インターフェイスについて説明しますつまり、サービス コントラクト、メッセージ、およびメッセージ スキーマ、サービスと対話するために使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c723c-105">Metadata describes the logical interface to a WCF service; that is, the service contract, messages, and message schemas that must be used to interact with the service.</span></span>  
  
 <span data-ttu-id="c723c-106">このメタデータがなどのツールによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="c723c-106">This metadata is used by tools such as:</span></span>  
  
- <span data-ttu-id="c723c-107">[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]サービス コントラクトのマネージ コードの表現で生成して</span><span class="sxs-lookup"><span data-stu-id="c723c-107">The [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] to generate managed code representations of the service contract, and</span></span>  
  
- <span data-ttu-id="c723c-108">[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]メッセージ スキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="c723c-108">The [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] to generate message schemas.</span></span>  
  
  <span data-ttu-id="c723c-109">ただしもメタデータを取得できますプログラムで、アダプターから。</span><span class="sxs-lookup"><span data-stu-id="c723c-109">However, you can also retrieve metadata programmatically from the adapter.</span></span> <span data-ttu-id="c723c-110">たとえば、既存のアプリケーションで使用するカスタム メタデータの取得ツールを作成することする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c723c-110">For example, you might want to do this to create a custom metadata retrieval tool to use in an existing application.</span></span>  
  
  <span data-ttu-id="c723c-111">アダプターは、2 つのエンドポイントからメタデータを発行します。</span><span class="sxs-lookup"><span data-stu-id="c723c-111">The adapter publishes metadata through two endpoints:</span></span>  
  
- <span data-ttu-id="c723c-112">Ws-metadata Exchange (MEX) エンドポイント。</span><span class="sxs-lookup"><span data-stu-id="c723c-112">A WS-Metadata Exchange (MEX) endpoint.</span></span> <span data-ttu-id="c723c-113">WCF では、すべての WCF バインドの MEX エンドポイントを自動的に提供します。</span><span class="sxs-lookup"><span data-stu-id="c723c-113">WCF automatically provides a MEX endpoint for all WCF bindings.</span></span> <span data-ttu-id="c723c-114">メタデータ交換を使用すると、基になる Oracle データベース アダプターによってサポートされる操作のメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="c723c-114">You can use metadata exchange to retrieve metadata for operations supported by the adapter on the underlying Oracle database.</span></span>  
  
- <span data-ttu-id="c723c-115">**IMetadataRetrievalContract**エンドポイント。</span><span class="sxs-lookup"><span data-stu-id="c723c-115">An **IMetadataRetrievalContract** endpoint.</span></span> <span data-ttu-id="c723c-116">**IMetadataRetrievalContract**インターフェイスによって実装されます、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="c723c-116">The **IMetadataRetrievalContract** interface is implemented by the [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)].</span></span> <span data-ttu-id="c723c-117">複数の論理レベルでの Oracle データベース成果物を分類し、それらをメタデータのノードのツリーとして表示します。</span><span class="sxs-lookup"><span data-stu-id="c723c-117">It categorizes Oracle database artifacts at multiple logical levels and presents them as a tree of metadata nodes.</span></span> <span data-ttu-id="c723c-118">によって公開されるメソッドを使用することができます、 **IMetadataRetrievalContract**インターフェイスを参照し、このツリーのノードの検索と操作している対象のメタデータを返します。</span><span class="sxs-lookup"><span data-stu-id="c723c-118">You can use methods exposed by the **IMetadataRetrievalContract** interface to browse and search the nodes of this tree and to return metadata for operations in which you are interested.</span></span>  
  
  <span data-ttu-id="c723c-119">このセクションのトピックでは、MEX を使用する方法を説明し、 **IMetadataRetrievalContract**アダプターからプログラムでメタデータを取得するエンドポイント。</span><span class="sxs-lookup"><span data-stu-id="c723c-119">The topics in this section describe how to use MEX and **IMetadataRetrievalContract** endpoints to retrieve metadata programmatically from the adapter.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c723c-120">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c723c-120">In This Section</span></span>  
  
-   [<span data-ttu-id="c723c-121">Ws-metadata Exchange を使用して Oracle データベースでメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="c723c-121">Get Metadata Using WS-Metadata Exchange in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-using-ws-metadata-exchange-in-oracle-database.md)  
  
-   [<span data-ttu-id="c723c-122">IMetadataRetrievalContract を使用して Oracle データベースでメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="c723c-122">Get Metadata in Oracle Database Using IMetadataRetrievalContract</span></span>](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-in-oracle-database-using-imetadataretrievalcontract.md)  
  
## <a name="see-also"></a><span data-ttu-id="c723c-123">参照</span><span class="sxs-lookup"><span data-stu-id="c723c-123">See Also</span></span>  
[<span data-ttu-id="c723c-124">Oracle データベース アプリケーションの開発</span><span class="sxs-lookup"><span data-stu-id="c723c-124">Develop your Oracle Database applications</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-your-oracle-database-applications.md)