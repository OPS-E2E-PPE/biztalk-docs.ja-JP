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
ms.openlocfilehash: 7af2cab529344f499ff006a6cd99401ae63c4668
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="testing-the-solution"></a>ソリューションをテストします。
ここでは、完成したソリューションをテストします。 Fabrikam ソリューションで作成した LOBWebApplication ツールを使用して、Contoso LOB アプリケーションに 3A2 PIP 要求を送信します。 作成した Contoso のプライベート オーケストレーションは、BizTalk Server の SQL アダプタを使用して、ERP システムに Contoso のベース 3 a 2 Price and Availability 要求を送信します。 ERP システムからの応答を受信すると、オーケストレーションはビジネス ルール エンジンを呼び出し、作成した緊急時に必要なビジネス ポリシーを実行します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [Fabrikam サンプルを使用した Price and Availability 要求の作成](../../adapters-and-accelerators/accelerator-rosettanet/creating-a-price-and-availability-request-with-the-fabrikam-sample.md)