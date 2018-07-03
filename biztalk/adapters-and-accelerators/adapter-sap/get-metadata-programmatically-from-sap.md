---
title: SAP からプログラムでメタデータの取得 |Microsoft Docs
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
ms.openlocfilehash: c0bf41b8213afd1c1af00c113e4a5406e6289dac
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013851"
---
# <a name="get-metadata-programmatically-from-sap"></a><span data-ttu-id="f30e8-102">SAP からプログラムでメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="f30e8-102">Get Metadata Programmatically from SAP</span></span>
<span data-ttu-id="f30e8-103">[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] WCF サービスとしての SAP システムを公開するカスタム WCF バインドします。</span><span class="sxs-lookup"><span data-stu-id="f30e8-103">The [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] is a custom WCF binding that exposes an SAP system as a WCF service.</span></span> <span data-ttu-id="f30e8-104">アダプターは、自己記述型のサービスとしての SAP システムを公開しますサポートされる操作についてのメタデータを公開できるサービスは、します。</span><span class="sxs-lookup"><span data-stu-id="f30e8-104">The adapter exposes the SAP system as a self-describing service; that is, a service that is capable of publishing metadata about the operations that it supports.</span></span> <span data-ttu-id="f30e8-105">メタデータが、WCF サービスに論理インターフェイスについて説明しますつまり、サービス コントラクト、メッセージ、およびメッセージ スキーマ、サービスと対話するために使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f30e8-105">Metadata describes the logical interface to a WCF service; that is, the service contract, messages, and message schemas that must be used to interact with the service.</span></span>  
  
 <span data-ttu-id="f30e8-106">このメタデータがなどのツールによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="f30e8-106">This metadata is used by tools such as:</span></span>  
  
- <span data-ttu-id="f30e8-107">[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]サービス コントラクトのマネージ コードの表現で生成して</span><span class="sxs-lookup"><span data-stu-id="f30e8-107">The [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] to generate managed code representations of the service contract, and</span></span>  
  
- <span data-ttu-id="f30e8-108">[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]メッセージ スキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="f30e8-108">The [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] to generate message schemas.</span></span>  
  
  <span data-ttu-id="f30e8-109">ただしもメタデータを取得できますプログラムで、アダプターから。</span><span class="sxs-lookup"><span data-stu-id="f30e8-109">However, you can also retrieve metadata programmatically from the adapter.</span></span> <span data-ttu-id="f30e8-110">たとえば、既存のアプリケーションで使用するカスタム メタデータの取得ツールを作成することする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f30e8-110">For example, you might want to do this to create a custom metadata retrieval tool to use in an existing application.</span></span>  
  
  <span data-ttu-id="f30e8-111">アダプターは、2 つのエンドポイントからメタデータを発行します。</span><span class="sxs-lookup"><span data-stu-id="f30e8-111">The adapter publishes metadata through two endpoints:</span></span>  
  
- <span data-ttu-id="f30e8-112">Ws-metadata Exchange (MEX) エンドポイント。</span><span class="sxs-lookup"><span data-stu-id="f30e8-112">A WS-Metadata Exchange (MEX) endpoint.</span></span> <span data-ttu-id="f30e8-113">WCF では、すべての WCF バインドの MEX エンドポイントを自動的に提供します。</span><span class="sxs-lookup"><span data-stu-id="f30e8-113">WCF automatically provides a MEX endpoint for all WCF bindings.</span></span> <span data-ttu-id="f30e8-114">メタデータ交換を使用すると、基になる SAP システムのアダプターでサポートされる操作のメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="f30e8-114">You can use metadata exchange to retrieve metadata for operations supported by the adapter on the underlying SAP system.</span></span>  
  
- <span data-ttu-id="f30e8-115">**IMetadataRetrievalContract**エンドポイント。</span><span class="sxs-lookup"><span data-stu-id="f30e8-115">An **IMetadataRetrievalContract** endpoint.</span></span> <span data-ttu-id="f30e8-116">**IMetadataRetrievalContract**インターフェイスによって実装されます、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="f30e8-116">The **IMetadataRetrievalContract** interface is implemented by the [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)].</span></span> <span data-ttu-id="f30e8-117">複数の論理レベルでの SAP システムの成果物を分類し、それらをメタデータのノードのツリーとして表示します。</span><span class="sxs-lookup"><span data-stu-id="f30e8-117">It categorizes SAP system artifacts at multiple logical levels and presents them as a tree of metadata nodes.</span></span> <span data-ttu-id="f30e8-118">によって公開されるメソッドを使用することができます、 **IMetadataRetrievalContract**インターフェイスを参照し、このツリーのノードの検索と操作している対象のメタデータを返します。</span><span class="sxs-lookup"><span data-stu-id="f30e8-118">You can use methods exposed by the **IMetadataRetrievalContract** interface to browse and search the nodes of this tree and to return metadata for operations in which you are interested.</span></span>  
  
  <span data-ttu-id="f30e8-119">このセクションのトピックでは、MEX を使用する方法を説明し、 **IMetadataRetrievalContract**アダプターからプログラムでメタデータを取得するエンドポイント。</span><span class="sxs-lookup"><span data-stu-id="f30e8-119">The topics in this section describe how to use MEX and **IMetadataRetrievalContract** endpoints to retrieve metadata programmatically from the adapter.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f30e8-120">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f30e8-120">In This Section</span></span>  
  
-   [<span data-ttu-id="f30e8-121">SAP で Ws-metadata Exchange を使用してメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="f30e8-121">Retrieving Metadata Using WS-Metadata Exchange in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/get-metadata-using-ws-metadata-exchange-in-sap.md)  
  
-   [<span data-ttu-id="f30e8-122">IMetadataRetrievalContract を使用して sap メタデータの取得</span><span class="sxs-lookup"><span data-stu-id="f30e8-122">Retrieving Metadata in SAP Using IMetadataRetrievalContract</span></span>](../../adapters-and-accelerators/adapter-sap/get-metadata-in-sap-using-imetadataretrievalcontract.md)  
  
## <a name="see-also"></a><span data-ttu-id="f30e8-123">参照</span><span class="sxs-lookup"><span data-stu-id="f30e8-123">See Also</span></span>  
[<span data-ttu-id="f30e8-124">SAP アプリケーションを開発する</span><span class="sxs-lookup"><span data-stu-id="f30e8-124">Develop your SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/develop-your-sap-applications.md)