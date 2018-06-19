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
# <a name="configure-atomic-consistent-isolated-and-durable-transactions-using-the-wcf-lob-adapter-sdk"></a>WCF LOB Adapter SDK を使用して分割不可能な一貫性、分離性、および持続性のあるトランザクションを構成します。
[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]によって公開される機能に依存してトランザクションをサポートする、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]です。 によって公開されている API を使用して[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]トランザクションとが操作には、アダプターをサポートできます。  
  
-   **アトミック**、か、保留中の更新すべてがコミットされるかはコミットされず、前の状態にロールバックされます。  
  
-   **一貫性のある**、行われた変更は、一貫性のある状態から、ことを確認します。  
  
-   **分離**、他の保留中のトランザクションのコミットされていない変更にアクセスするトランザクションを防止します。  
  
-   **持続性のある**、コミット後の更新プログラムになる障害発生した場合に永続的なを意味します。  
  
 アダプター開発者にとってリレーショナル データベース システムまたは他の基幹業務システム トランザクションをサポート (または期待) が、ターゲット システムがどのようにサポートし、トランザクションのサポートが公開を特定し、適切なを識別する必要があります[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]トランザクション モデルを使用します。  
  
 詳細については[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]トランザクションを参照してください[Windows Communication Foundation トランザクション概要](https://msdn.microsoft.com/library/ms733904.aspx)です。 
  
## <a name="see-also"></a>参照  
 [計画し、WCF LOB Adapter SDK を使用して、アダプターの設計](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-your-adapter-using-the-wcf-lob-adapter-sdk.md)