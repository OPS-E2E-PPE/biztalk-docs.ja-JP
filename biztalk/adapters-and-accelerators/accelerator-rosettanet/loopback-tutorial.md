---
title: Loopback チュートリアル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- loopbacks, tutorial
- loopback tutorial, about the loopback tutorial
- loopback tutorial
- tutorials, loopback tutorial
ms.assetid: 0f69c1f1-4039-4949-8eed-127ceabbc3cc
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97714d5f7e604acbb798739fc4eb545a07968980
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010099"
---
# <a name="loopback-tutorial"></a>Loopback チュートリアル
このチュートリアルには、Microsoft® を使用する方法を説明する詳細な手順が含まれています。[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]を 1 台のコンピューターをホームとパートナーの組織間のプロセスの実装をシミュレートします。  
  
 実際の運用環境では、取引先組織はリモート コンピューターに実装されます。 このチュートリアルでは、ループバック ユーティリティを使用して、同じコンピューター上で取引先をシミュレートするためのミラー取引アグリーメントを作成します。 1 台のコンピューターでループバックを行うシナリオの使用は、開発とテストを目的としたものです。 運用環境ではループバック ユーティリティを使用しないことをお勧めします。  
  
 このループバック シナリオでは署名メッセージはサポートされないため、否認不可もサポートされません。  
  
 証明機関が構成されており、テスト目的に使用できる暗号化用の秘密キーがある場合は、このシナリオではメッセージの暗号化がサポートされます。  
  
 このチュートリアルでは、ホーム組織、取引先組織、取引アグリーメントを作成し、ループバック ユーティリティを使用してミラー アグリーメントを作成し、次にサンプル プロセスを実行してループバック シナリオを検証します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [チュートリアルの準備](../../adapters-and-accelerators/accelerator-rosettanet/preparing-for-the-tutorial.md)  
  
-   [手順 1: ホーム組織の作成](../../adapters-and-accelerators/accelerator-rosettanet/step-1-create-the-home-organization.md)  
  
-   [手順 2: 取引先組織の作成](../../adapters-and-accelerators/accelerator-rosettanet/step-2-create-the-partner-organization.md)  
  
-   [手順 3: Partner Interface Process の編集](../../adapters-and-accelerators/accelerator-rosettanet/step-3-edit-the-partner-interface-process.md)  
  
-   [手順 4: 取引先アグリーメントの作成](../../adapters-and-accelerators/accelerator-rosettanet/step-4-create-a-trade-agreement.md)  
  
-   [手順 5: ミラー アグリーメントの作成](../../adapters-and-accelerators/accelerator-rosettanet/step-5-create-a-mirror-agreement.md)  
  
-   [手順 6: オーケストレーションの開始](../../adapters-and-accelerators/accelerator-rosettanet/step-6-start-orchestrations.md)  
  
-   [手順 7: サンプル LOB メッセージの作成](../../adapters-and-accelerators/accelerator-rosettanet/step-7-create-a-sample-lob-message.md)  
  
-   [手順 8: BTARN データベース内のメッセージの表示](../../adapters-and-accelerators/accelerator-rosettanet/step-8-view-messages-in-the-btarn-databases.md)