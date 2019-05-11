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
ms.openlocfilehash: f96d81e59686759300e996e2f257da5afbc91ed0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283286"
---
# <a name="loopback-tutorial"></a>Loopback チュートリアル
このチュートリアルには、Microsoft® を使用する方法を説明する詳細な手順が含まれています。[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]を 1 台のコンピューターをホームとパートナーの組織間のプロセスの実装をシミュレートします。  
  
 実際の運用環境で、パートナー組織の実装は、リモート コンピューターに存在します。 このチュートリアルでは、同じコンピューター上で取引をシミュレートするためのアグリーメントを取引先ミラーを作成するのに、Loopback ユーティリティを使用します。 1 台のコンピューターのループバック シナリオを使用して開発およびテスト目的に適しています。 運用環境で、Loopback ユーティリティを使用しないようにすることをお勧めします。  
  
 このループバック シナリオは、メッセージの署名をサポートしていませんし、ため、否認不可はサポートされません。  
  
 このシナリオは、テスト目的で使用できる暗号化用の秘密キーを使用して、構成されている証明機関がある場合、メッセージの暗号化をサポートしています。  
  
 このチュートリアルでは、Loopback ユーティリティを使用してミラー アグリーメントを作成するや、ループバック シナリオを確認するサンプル プロセスを実行し、ホーム組織、取引先組織、取引先アグリーメントを作成します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [チュートリアルの準備](../../adapters-and-accelerators/accelerator-rosettanet/preparing-for-the-tutorial.md)  
  
-   [ステップ 1: ホーム組織の作成](../../adapters-and-accelerators/accelerator-rosettanet/step-1-create-the-home-organization.md)  
  
-   [手順 2:取引先組織の作成](../../adapters-and-accelerators/accelerator-rosettanet/step-2-create-the-partner-organization.md)  
  
-   [ステップ 3:PIP (Partner Interface Process) の編集](../../adapters-and-accelerators/accelerator-rosettanet/step-3-edit-the-partner-interface-process.md)  
  
-   [手順 4:取引契約の作成](../../adapters-and-accelerators/accelerator-rosettanet/step-4-create-a-trade-agreement.md)  
  
-   [手順 5:ミラー アグリーメントの作成](../../adapters-and-accelerators/accelerator-rosettanet/step-5-create-a-mirror-agreement.md)  
  
-   [手順 6:オーケストレーションの開始](../../adapters-and-accelerators/accelerator-rosettanet/step-6-start-orchestrations.md)  
  
-   [手順 7:サンプル LOB メッセージの作成](../../adapters-and-accelerators/accelerator-rosettanet/step-7-create-a-sample-lob-message.md)  
  
-   [手順 8:BTARN データベース内のメッセージの表示](../../adapters-and-accelerators/accelerator-rosettanet/step-8-view-messages-in-the-btarn-databases.md)