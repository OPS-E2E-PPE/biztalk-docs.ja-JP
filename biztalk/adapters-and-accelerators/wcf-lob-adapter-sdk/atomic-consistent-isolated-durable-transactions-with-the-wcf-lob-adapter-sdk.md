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
# <a name="configure-atomic-consistent-isolated-and-durable-transactions-using-the-wcf-lob-adapter-sdk"></a>WCF LOB Adapter SDK を使用して原子性、一貫性のある、分離、および持続性のあるトランザクションを設定します。
[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]によって公開される機能に依存することにより、トランザクションをサポートする、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]します。 によって公開される API を使用して[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]アダプターはトランザクションとは操作をサポートできます。  
  
- **アトミック**、か、保留中の更新すべてがコミットされるかがコミットされ、以前の状態にロールバックなし。  
  
- **一貫性のある**、加えられた変更は、1 つの一貫性のある状態からことを確認します。  
  
- **分離**、他の保留中のトランザクションのコミットされていない変更にアクセスするトランザクションを防止します。  
  
- **持続性のある**、コミットすると、更新プログラムがなる障害発生時に永続的なを意味します。  
  
  アダプター開発者がリレーショナルを対象とするシステムのデータベースまたはトランザクションをサポート (または予想される) その他の基幹業務システムが、ターゲット システムがどのようにサポートし、トランザクションのサポートが公開されますを特定し、適切なを特定する必要があります[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]トランザクション モデルを使用します。  
  
  詳細については[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]トランザクション、 [Windows Communication Foundation のトランザクションの概要](https://msdn.microsoft.com/library/ms733904.aspx)します。 
  
## <a name="see-also"></a>参照  
 [計画し、WCF LOB Adapter SDK を使用して、アダプターの設計](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-your-adapter-using-the-wcf-lob-adapter-sdk.md)