---
title: WCF LOB Adapter SDK を使用して原子性、一貫性のある、分離、および持続性のあるトランザクションの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c20d2613-c77d-4b0d-b2e2-3ed28a8fb36c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37b39ec0e240a2d4ee9ba1239cf27d7b118ca0ad
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007707"
---
# <a name="configure-atomic-consistent-isolated-and-durable-transactions-using-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="22eb7-102">WCF LOB Adapter SDK を使用して原子性、一貫性のある、分離、および持続性のあるトランザクションを設定します。</span><span class="sxs-lookup"><span data-stu-id="22eb7-102">Configure atomic, consistent, isolated, and durable transactions using the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="22eb7-103">[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]によって公開される機能に依存することにより、トランザクションをサポートする、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="22eb7-103">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] supports transactions by relying on functionality exposed by the [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)].</span></span> <span data-ttu-id="22eb7-104">によって公開される API を使用して[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]アダプターはトランザクションとは操作をサポートできます。</span><span class="sxs-lookup"><span data-stu-id="22eb7-104">By using the API exposed by [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)], your adapter can support transactions and operations that are:</span></span>  
  
- <span data-ttu-id="22eb7-105">**アトミック**、か、保留中の更新すべてがコミットされるかがコミットされ、以前の状態にロールバックなし。</span><span class="sxs-lookup"><span data-stu-id="22eb7-105">**Atomic**, ensuring that either all pending updates are committed or none are committed and are rolled back to their previous state.</span></span>  
  
- <span data-ttu-id="22eb7-106">**一貫性のある**、加えられた変更は、1 つの一貫性のある状態からことを確認します。</span><span class="sxs-lookup"><span data-stu-id="22eb7-106">**Consistent**, ensuring that changes made are from one consistent state to another.</span></span>  
  
- <span data-ttu-id="22eb7-107">**分離**、他の保留中のトランザクションのコミットされていない変更にアクセスするトランザクションを防止します。</span><span class="sxs-lookup"><span data-stu-id="22eb7-107">**Isolated**, preventing a transaction to access uncommitted changes in other pending transactions.</span></span>  
  
- <span data-ttu-id="22eb7-108">**持続性のある**、コミットすると、更新プログラムがなる障害発生時に永続的なを意味します。</span><span class="sxs-lookup"><span data-stu-id="22eb7-108">**Durable**, meaning that once committed, updates will be persistent in the face of failures.</span></span>  
  
  <span data-ttu-id="22eb7-109">アダプター開発者がリレーショナルを対象とするシステムのデータベースまたはトランザクションをサポート (または予想される) その他の基幹業務システムが、ターゲット システムがどのようにサポートし、トランザクションのサポートが公開されますを特定し、適切なを特定する必要があります[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]トランザクション モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="22eb7-109">Adapter developers targeting relational database systems or other line-of-business systems that support (or expect) transactions will need to identify how the target system supports and exposes transaction support and then identify an appropriate [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] transaction model to use.</span></span>  
  
  <span data-ttu-id="22eb7-110">詳細については[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]トランザクション、 [Windows Communication Foundation のトランザクションの概要](https://msdn.microsoft.com/library/ms733904.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="22eb7-110">For more information about [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] transactions, see [Windows Communication Foundation Transactions Overview](https://msdn.microsoft.com/library/ms733904.aspx).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="22eb7-111">参照</span><span class="sxs-lookup"><span data-stu-id="22eb7-111">See Also</span></span>  
 [<span data-ttu-id="22eb7-112">計画し、WCF LOB Adapter SDK を使用して、アダプターの設計</span><span class="sxs-lookup"><span data-stu-id="22eb7-112">Plan and Design your Adapter using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-your-adapter-using-the-wcf-lob-adapter-sdk.md)