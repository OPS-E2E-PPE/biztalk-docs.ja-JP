---
title: "TIBCO Rendezvous の制限事項 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: TIBCO Rendezvous, limitations
ms.assetid: 8e210457-2887-43f9-a249-be1daa6ee4eb
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 717188e42450d13dee92364cd9c673aaaf48eaf6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="tibco-rendezvous-limitations"></a>TIBCO Rendezvous の制限事項
TIBCO Rendezvous では、フィールド名が一意であるとは限りません。 TIBCO Rendezvous メッセージに 2 つの同じフィールド名がある場合、生成される XML は無効になります。  
  
 他にも次の制限があります。  
  
-   フィールドを並べ替えることはできません。  
  
-   TIBCO Rendezvous のドキュメントによると、サブジェクト名には印刷できない文字を使用できないことになっていますが、そのような文字を使用することはできます。 BizTalk Adapter for TIBCO Rendezvous では印刷できない文字が入ったサブジェクト名をサポートしていません。  
  
-   デーモンへのセキュリティで保護された接続はサポートされていません。  
  
-   カスタム データ型はサポートされていません。  
  
-   認定メッセージングは送信側ではサポートされていません。  
  
## <a name="see-also"></a>参照  
 [TIBCO Rendezvous の概念](../core/tibco-rendezvous-concepts.md)   
 [作業の開始](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)