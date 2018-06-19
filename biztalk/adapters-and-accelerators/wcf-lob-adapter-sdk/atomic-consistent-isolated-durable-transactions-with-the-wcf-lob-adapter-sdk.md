---
title: WCF LOB Adapter SDK を使用して分割不可能な一貫性、分離性、および持続性のあるトランザクションの構成 |Microsoft ドキュメント
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
ms.openlocfilehash: 58cf80a70b04e20aeb25b27210d88dfd861d7539
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224242"
---
# <a name="configure-atomic-consistent-isolated-and-durable-transactions-using-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="57484-102">WCF LOB Adapter SDK を使用して分割不可能な一貫性、分離性、および持続性のあるトランザクションを構成します。</span><span class="sxs-lookup"><span data-stu-id="57484-102">Configure atomic, consistent, isolated, and durable transactions using the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="57484-103">[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]によって公開される機能に依存してトランザクションをサポートする、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="57484-103">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] supports transactions by relying on functionality exposed by the [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)].</span></span> <span data-ttu-id="57484-104">によって公開されている API を使用して[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]トランザクションとが操作には、アダプターをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="57484-104">By using the API exposed by [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)], your adapter can support transactions and operations that are:</span></span>  
  
-   <span data-ttu-id="57484-105">**アトミック**、か、保留中の更新すべてがコミットされるかはコミットされず、前の状態にロールバックされます。</span><span class="sxs-lookup"><span data-stu-id="57484-105">**Atomic**, ensuring that either all pending updates are committed or none are committed and are rolled back to their previous state.</span></span>  
  
-   <span data-ttu-id="57484-106">**一貫性のある**、行われた変更は、一貫性のある状態から、ことを確認します。</span><span class="sxs-lookup"><span data-stu-id="57484-106">**Consistent**, ensuring that changes made are from one consistent state to another.</span></span>  
  
-   <span data-ttu-id="57484-107">**分離**、他の保留中のトランザクションのコミットされていない変更にアクセスするトランザクションを防止します。</span><span class="sxs-lookup"><span data-stu-id="57484-107">**Isolated**, preventing a transaction to access uncommitted changes in other pending transactions.</span></span>  
  
-   <span data-ttu-id="57484-108">**持続性のある**、コミット後の更新プログラムになる障害発生した場合に永続的なを意味します。</span><span class="sxs-lookup"><span data-stu-id="57484-108">**Durable**, meaning that once committed, updates will be persistent in the face of failures.</span></span>  
  
 <span data-ttu-id="57484-109">アダプター開発者にとってリレーショナル データベース システムまたは他の基幹業務システム トランザクションをサポート (または期待) が、ターゲット システムがどのようにサポートし、トランザクションのサポートが公開を特定し、適切なを識別する必要があります[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]トランザクション モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="57484-109">Adapter developers targeting relational database systems or other line-of-business systems that support (or expect) transactions will need to identify how the target system supports and exposes transaction support and then identify an appropriate [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] transaction model to use.</span></span>  
  
 <span data-ttu-id="57484-110">詳細については[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]トランザクションを参照してください[Windows Communication Foundation トランザクション概要](https://msdn.microsoft.com/library/ms733904.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="57484-110">For more information about [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] transactions, see [Windows Communication Foundation Transactions Overview](https://msdn.microsoft.com/library/ms733904.aspx).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="57484-111">参照</span><span class="sxs-lookup"><span data-stu-id="57484-111">See Also</span></span>  
 [<span data-ttu-id="57484-112">計画し、WCF LOB Adapter SDK を使用して、アダプターの設計</span><span class="sxs-lookup"><span data-stu-id="57484-112">Plan and Design your Adapter using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-your-adapter-using-the-wcf-lob-adapter-sdk.md)