---
title: ソリューションのテスト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- testing solutions
- private process tutorial, testing solutions
ms.assetid: 90faf959-bac6-4695-8cb7-ecabe52baf1a
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b43ab300fefbe1916b58e9c606c2541dfd0a10e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280602"
---
# <a name="testing-the-solution"></a>ソリューションのテスト
このセクションでは、完全なソリューションをテストします。 Fabrikam ソリューションで作成した LOBWebApplication ツールを使用して、Contoso LOB アプリケーションに 3 a 2 PIP 要求を送信します。 作成した Contoso のプライベート オーケストレーションは、BizTalk Server の SQL アダプターを使用して、ERP システムに Contoso のに基づいて 3 a 2 Price and Availability 要求を送信します。 ERP システムからの応答が受信されると、オーケストレーションを呼び出して、緊急にビジネス ルール エンジンでは、ビジネス ポリシーを作成する必要です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [Fabrikam サンプルを使用した Price and Availability 要求の作成](../../adapters-and-accelerators/accelerator-rosettanet/creating-a-price-and-availability-request-with-the-fabrikam-sample.md)