---
title: Oracle データベースからメタデータをプログラムで取得 |Microsoft ドキュメント
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
ms.openlocfilehash: c36fcd6a791f1d960a4dd4dfd78ca199d2e49cb5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214274"
---
# <a name="get-metadata-programmatically-from-the-oracle-database"></a><span data-ttu-id="12666-102">Oracle データベースからメタデータをプログラムで取得します。</span><span class="sxs-lookup"><span data-stu-id="12666-102">Get Metadata Programmatically from the Oracle Database</span></span>
<span data-ttu-id="12666-103">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]は、WCF サービスとして Oracle データベースを公開するカスタムの WCF バインディング。</span><span class="sxs-lookup"><span data-stu-id="12666-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] is a custom WCF binding that exposes an Oracle database as a WCF service.</span></span> <span data-ttu-id="12666-104">アダプターは、自己記述型のサービスとして、Oracle データベースを公開します。サポートされる操作に関するメタデータを公開できるサービスは、します。</span><span class="sxs-lookup"><span data-stu-id="12666-104">The adapter exposes the Oracle database as a self-describing service; that is, a service that is capable of publishing metadata about the operations that it supports.</span></span> <span data-ttu-id="12666-105">メタデータは、WCF サービス; を論理インターフェイスを説明します。つまり、サービス コントラクト、メッセージ、およびメッセージ スキーマ、サービスと対話するために使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="12666-105">Metadata describes the logical interface to a WCF service; that is, the service contract, messages, and message schemas that must be used to interact with the service.</span></span>  
  
 <span data-ttu-id="12666-106">このメタデータがなどのツールによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="12666-106">This metadata is used by tools such as:</span></span>  
  
-   <span data-ttu-id="12666-107">[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]マネージ コードを表す、サービス コントラクトの生成と</span><span class="sxs-lookup"><span data-stu-id="12666-107">The [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] to generate managed code representations of the service contract, and</span></span>  
  
-   <span data-ttu-id="12666-108">[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]メッセージ スキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="12666-108">The [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] to generate message schemas.</span></span>  
  
 <span data-ttu-id="12666-109">ただし、ことができますもメタデータを取得するプログラムで、アダプターからです。</span><span class="sxs-lookup"><span data-stu-id="12666-109">However, you can also retrieve metadata programmatically from the adapter.</span></span> <span data-ttu-id="12666-110">たとえば、既存のアプリケーションで使用するカスタム メタデータ取得ツールを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="12666-110">For example, you might want to do this to create a custom metadata retrieval tool to use in an existing application.</span></span>  
  
 <span data-ttu-id="12666-111">アダプターは、2 つのエンドポイントを介してメタデータを公開します。</span><span class="sxs-lookup"><span data-stu-id="12666-111">The adapter publishes metadata through two endpoints:</span></span>  
  
-   <span data-ttu-id="12666-112">Ws-metadata Exchange (MEX) エンドポイント。</span><span class="sxs-lookup"><span data-stu-id="12666-112">A WS-Metadata Exchange (MEX) endpoint.</span></span> <span data-ttu-id="12666-113">WCF では、すべての WCF バインドの MEX エンドポイントが自動的に用意されています。</span><span class="sxs-lookup"><span data-stu-id="12666-113">WCF automatically provides a MEX endpoint for all WCF bindings.</span></span> <span data-ttu-id="12666-114">メタデータ交換を使用すると、基になる Oracle データベースで、アダプターでサポートされる操作のメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="12666-114">You can use metadata exchange to retrieve metadata for operations supported by the adapter on the underlying Oracle database.</span></span>  
  
-   <span data-ttu-id="12666-115">**IMetadataRetrievalContract**エンドポイント。</span><span class="sxs-lookup"><span data-stu-id="12666-115">An **IMetadataRetrievalContract** endpoint.</span></span> <span data-ttu-id="12666-116">**IMetadataRetrievalContract**インターフェイスは、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="12666-116">The **IMetadataRetrievalContract** interface is implemented by the [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)].</span></span> <span data-ttu-id="12666-117">複数の論理レベルでの Oracle データベースの成果物を分類し、それらがメタデータのノードのツリーとして表示します。</span><span class="sxs-lookup"><span data-stu-id="12666-117">It categorizes Oracle database artifacts at multiple logical levels and presents them as a tree of metadata nodes.</span></span> <span data-ttu-id="12666-118">によって公開されるメソッドを使用することができます、 **IMetadataRetrievalContract**インターフェイスを参照して、このツリーのノードを検索しの関心がある操作のメタデータを返します。</span><span class="sxs-lookup"><span data-stu-id="12666-118">You can use methods exposed by the **IMetadataRetrievalContract** interface to browse and search the nodes of this tree and to return metadata for operations in which you are interested.</span></span>  
  
 <span data-ttu-id="12666-119">このセクションのトピックでは、MEX を使用する方法を説明し、 **IMetadataRetrievalContract**アダプターからメタデータをプログラムから取得するエンドポイント。</span><span class="sxs-lookup"><span data-stu-id="12666-119">The topics in this section describe how to use MEX and **IMetadataRetrievalContract** endpoints to retrieve metadata programmatically from the adapter.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="12666-120">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="12666-120">In This Section</span></span>  
  
-   [<span data-ttu-id="12666-121">Ws-metadata Exchange を使用して Oracle データベースでメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="12666-121">Get Metadata Using WS-Metadata Exchange in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-using-ws-metadata-exchange-in-oracle-database.md)  
  
-   [<span data-ttu-id="12666-122">IMetadataRetrievalContract を使用して Oracle データベース内のメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="12666-122">Get Metadata in Oracle Database Using IMetadataRetrievalContract</span></span>](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-in-oracle-database-using-imetadataretrievalcontract.md)  
  
## <a name="see-also"></a><span data-ttu-id="12666-123">参照</span><span class="sxs-lookup"><span data-stu-id="12666-123">See Also</span></span>  
[<span data-ttu-id="12666-124">Oracle データベース アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="12666-124">Develop your Oracle Database applications</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-your-oracle-database-applications.md)