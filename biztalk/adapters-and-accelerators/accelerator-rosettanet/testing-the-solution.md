---
title: "ソリューションのテスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- testing solutions
- private process tutorial, testing solutions
ms.assetid: 90faf959-bac6-4695-8cb7-ecabe52baf1a
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4692035aed17f8432eb2bb515fa75df61be8047f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="testing-the-solution"></a>ソリューションをテストします。
ここでは、完成したソリューションをテストします。 Fabrikam ソリューションで作成した LOBWebApplication ツールを使用して、Contoso LOB アプリケーションに 3A2 PIP 要求を送信します。 作成した Contoso のプライベート オーケストレーションは、SQL Adapter for [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] を使用して、Contoso ベースの 3A2 Price and Availability 要求を ERP システムに送信します。 ERP システムからの応答を受信すると、オーケストレーションはビジネス ルール エンジンを呼び出し、作成した緊急時に必要なビジネス ポリシーを実行します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [Fabrikam サンプルを使用して Price and Availability Request の作成](../../adapters-and-accelerators/accelerator-rosettanet/creating-a-price-and-availability-request-with-the-fabrikam-sample.md)