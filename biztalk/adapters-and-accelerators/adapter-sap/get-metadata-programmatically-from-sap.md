---
title: SAP からメタデータをプログラムで取得 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IMetadataRetrievalContract endpoint
- metadata, retrieving programmatically
- WS-Metadata Exchange (MEX) endpoint
ms.assetid: 8d75332e-c103-4bd5-a9a2-56d21747a04e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c856b3629d7d7dcd3f9aa5431c0406f6c822e54
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216834"
---
# <a name="get-metadata-programmatically-from-sap"></a><span data-ttu-id="04124-102">SAP からメタデータをプログラムで取得します。</span><span class="sxs-lookup"><span data-stu-id="04124-102">Get Metadata Programmatically from SAP</span></span>
<span data-ttu-id="04124-103">[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]は、WCF サービスとして SAP システムを公開するカスタムの WCF バインディング。</span><span class="sxs-lookup"><span data-stu-id="04124-103">The [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] is a custom WCF binding that exposes an SAP system as a WCF service.</span></span> <span data-ttu-id="04124-104">アダプターは、自己記述型のサービスとして SAP システムを公開します。サポートされる操作に関するメタデータを公開できるサービスは、します。</span><span class="sxs-lookup"><span data-stu-id="04124-104">The adapter exposes the SAP system as a self-describing service; that is, a service that is capable of publishing metadata about the operations that it supports.</span></span> <span data-ttu-id="04124-105">メタデータは、WCF サービス; を論理インターフェイスを説明します。つまり、サービス コントラクト、メッセージ、およびメッセージ スキーマ、サービスと対話するために使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04124-105">Metadata describes the logical interface to a WCF service; that is, the service contract, messages, and message schemas that must be used to interact with the service.</span></span>  
  
 <span data-ttu-id="04124-106">このメタデータがなどのツールによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="04124-106">This metadata is used by tools such as:</span></span>  
  
-   <span data-ttu-id="04124-107">[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]マネージ コードを表す、サービス コントラクトの生成と</span><span class="sxs-lookup"><span data-stu-id="04124-107">The [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] to generate managed code representations of the service contract, and</span></span>  
  
-   <span data-ttu-id="04124-108">[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]メッセージ スキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="04124-108">The [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] to generate message schemas.</span></span>  
  
 <span data-ttu-id="04124-109">ただし、ことができますもメタデータを取得するプログラムで、アダプターからです。</span><span class="sxs-lookup"><span data-stu-id="04124-109">However, you can also retrieve metadata programmatically from the adapter.</span></span> <span data-ttu-id="04124-110">たとえば、既存のアプリケーションで使用するカスタム メタデータ取得ツールを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="04124-110">For example, you might want to do this to create a custom metadata retrieval tool to use in an existing application.</span></span>  
  
 <span data-ttu-id="04124-111">アダプターは、2 つのエンドポイントを介してメタデータを公開します。</span><span class="sxs-lookup"><span data-stu-id="04124-111">The adapter publishes metadata through two endpoints:</span></span>  
  
-   <span data-ttu-id="04124-112">Ws-metadata Exchange (MEX) エンドポイント。</span><span class="sxs-lookup"><span data-stu-id="04124-112">A WS-Metadata Exchange (MEX) endpoint.</span></span> <span data-ttu-id="04124-113">WCF では、すべての WCF バインドの MEX エンドポイントが自動的に用意されています。</span><span class="sxs-lookup"><span data-stu-id="04124-113">WCF automatically provides a MEX endpoint for all WCF bindings.</span></span> <span data-ttu-id="04124-114">メタデータ交換を使用すると、基になる SAP システム上のアダプターによってサポートされる操作のメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="04124-114">You can use metadata exchange to retrieve metadata for operations supported by the adapter on the underlying SAP system.</span></span>  
  
-   <span data-ttu-id="04124-115">**IMetadataRetrievalContract**エンドポイント。</span><span class="sxs-lookup"><span data-stu-id="04124-115">An **IMetadataRetrievalContract** endpoint.</span></span> <span data-ttu-id="04124-116">**IMetadataRetrievalContract**インターフェイスは、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="04124-116">The **IMetadataRetrievalContract** interface is implemented by the [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)].</span></span> <span data-ttu-id="04124-117">複数の論理レベルでの SAP システムの成果物を分類し、それらがメタデータのノードのツリーとして表示します。</span><span class="sxs-lookup"><span data-stu-id="04124-117">It categorizes SAP system artifacts at multiple logical levels and presents them as a tree of metadata nodes.</span></span> <span data-ttu-id="04124-118">によって公開されるメソッドを使用することができます、 **IMetadataRetrievalContract**インターフェイスを参照して、このツリーのノードを検索しの関心がある操作のメタデータを返します。</span><span class="sxs-lookup"><span data-stu-id="04124-118">You can use methods exposed by the **IMetadataRetrievalContract** interface to browse and search the nodes of this tree and to return metadata for operations in which you are interested.</span></span>  
  
 <span data-ttu-id="04124-119">このセクションのトピックでは、MEX を使用する方法を説明し、 **IMetadataRetrievalContract**アダプターからメタデータをプログラムから取得するエンドポイント。</span><span class="sxs-lookup"><span data-stu-id="04124-119">The topics in this section describe how to use MEX and **IMetadataRetrievalContract** endpoints to retrieve metadata programmatically from the adapter.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="04124-120">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="04124-120">In This Section</span></span>  
  
-   [<span data-ttu-id="04124-121">SAP で Ws-metadata Exchange を使用してメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="04124-121">Retrieving Metadata Using WS-Metadata Exchange in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/get-metadata-using-ws-metadata-exchange-in-sap.md)  
  
-   [<span data-ttu-id="04124-122">IMetadataRetrievalContract を使用して SAP のメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="04124-122">Retrieving Metadata in SAP Using IMetadataRetrievalContract</span></span>](../../adapters-and-accelerators/adapter-sap/get-metadata-in-sap-using-imetadataretrievalcontract.md)  
  
## <a name="see-also"></a><span data-ttu-id="04124-123">参照</span><span class="sxs-lookup"><span data-stu-id="04124-123">See Also</span></span>  
[<span data-ttu-id="04124-124">SAP アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="04124-124">Develop your SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/develop-your-sap-applications.md)