---
title: "SharePoint での Siebel アダプターの使用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9f659b80-ec62-4797-adc3-b43cb0d79506
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d95dd9e1ae158dfa4612d0fc9fa86c896f4cff2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="use-the-siebel-adapter-with-sharepoint"></a><span data-ttu-id="74a95-102">SharePoint での Siebel アダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="74a95-102">Use the Siebel Adapter with SharePoint</span></span>
<span data-ttu-id="74a95-103">ほとんどの基幹業務 (LOB) アプリケーションは、必要な特定の分野専門知識と比較的少数のユーザーがアクセスできる専用のインターフェイスを持っています。</span><span class="sxs-lookup"><span data-stu-id="74a95-103">Most line-of-business (LOB) applications have proprietary interfaces that are accessible to relatively few people with the required subject matter expertise.</span></span> <span data-ttu-id="74a95-104">ただし、関連する情報のワーカーが必要、すべてのレベル、組織の領域の専門家であるために、インフォメーション ワーカーが、情報を使用する上で Microsoft Excel などの他の一般的なアプリケーションに必要なデータをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="74a95-104">However, because information workers need relevant information at all levels in an organization, the subject matter experts have to export required data into more familiar applications, like Microsoft Excel, for information workers to consume the information.</span></span>  
  
 <span data-ttu-id="74a95-105">Microsoft Office クライアント アプリケーションと機能の新しいコレクションは、インフォメーション ワーカーが、Microsoft Office の最も一般的なインターフェイスにバックエンド ビジネス データを戻すことによってこの時間差を結びます。</span><span class="sxs-lookup"><span data-stu-id="74a95-105">The new collection of Microsoft Office client applications and features bridges this gap by bringing backend business data into the most common interface for information workers, Microsoft Office.</span></span> <span data-ttu-id="74a95-106">Microsoft Office クライアント アプリケーションは、インフォメーション ワーカーに使い慣れたインターフェイスを通じて、LOB アプリケーションからデータをシームレスに提示します。</span><span class="sxs-lookup"><span data-stu-id="74a95-106">Microsoft Office client applications seamlessly present data from LOB applications through interfaces familiar to information workers.</span></span> <span data-ttu-id="74a95-107">1 つの例は、Microsoft sharepoint ビジネス データ カタログです。</span><span class="sxs-lookup"><span data-stu-id="74a95-107">One example is the Business Data Catalog in Microsoft  SharePoint.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="74a95-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="74a95-108">In This Section</span></span>  
  
-   [<span data-ttu-id="74a95-109">Siebel アダプターとビジネス データ カタログについて</span><span class="sxs-lookup"><span data-stu-id="74a95-109">About Business Data Catalog with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/about-business-data-catalog-with-the-siebel-adapter.md)  
  
-   [<span data-ttu-id="74a95-110">ビジネス データと Siebel システムを統合する Siebel アダプターの構成カタログと SharePoint</span><span class="sxs-lookup"><span data-stu-id="74a95-110">Configure the Siebel Adapter to Integrate the Siebel System with the Business Data Catalog and SharePoint</span></span>](../../adapters-and-accelerators/adapter-siebel/configure-the-siebel-adapter-to-use-the-business-data-catalog-in-sharepoint.md)  
  
-   [<span data-ttu-id="74a95-111">SharePoint で Siebel アダプターの使用時の考慮事項</span><span class="sxs-lookup"><span data-stu-id="74a95-111">Considerations when Using the Siebel Adapter with SharePoint</span></span>](../../adapters-and-accelerators/adapter-siebel/considerations-when-using-the-siebel-adapter-with-sharepoint.md)  
  
-   <span data-ttu-id="74a95-112">[カスタム Web パーツの使用方法](https://msdn.microsoft.com/library/dd450993(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="74a95-112">[How Do I Use a Custom Web Part?](https://msdn.microsoft.com/library/dd450993(v=bts.10).aspx)</span></span>