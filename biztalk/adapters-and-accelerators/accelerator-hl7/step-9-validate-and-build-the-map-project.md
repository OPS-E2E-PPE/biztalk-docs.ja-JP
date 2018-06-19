---
title: '手順 9: 検証プロジェクトをビルド マップ |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- validating, maps
- message enrichment tutorial, maps
- maps, building
- maps, validating
ms.assetid: 10716b0b-702c-48bb-85a9-d58d8f33b68b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1eb4580a9c89534204e492aebdd21988a6ce0e6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206474"
---
# <a name="step-9-validate-and-build-the-map-project"></a>手順 9: 検証プロジェクトをビルド マップ
このステップで使用して、**マップの検証**コマンドをマップ、内部不整合があるかによってマッピング スキーマを効果的に使用されないようにするその他の問題があるかを確認します。 作成したリソース (スキーマおよびマップ) が含まれているアセンブリを生成するプロジェクトを作成します。 またこれにより、これまでに完了した作業ではコンパイル エラーがないこと。  
  
### <a name="to-validate-the-map-project"></a>マップのプロジェクトを検証するには  
  
1.  ソリューション エクスプ ローラーで右クリックし、 **DoorbellMap.btm**マップ、およびクリックして**マップの検証**です。  
  
2.  成功メッセージが出力ウィンドウに表示されることを確認します。 送信先スキーマ内のすべての利用可能な要素にマップしているのではないために、いくつかの警告が表示されます。  
  
     成功メッセージが表示されない場合は、マップのプロジェクトをトラブルシューティングします。  
  
### <a name="to-build-the-map-project"></a>マップのプロジェクトをビルドするには  
  
-   ソリューション エクスプ ローラーで右クリック**BTAHL7 プロジェクト**、クリックして**ビルド**です。 成功メッセージが出力ウィンドウに表示されることを確認します。  
  
     成功メッセージが表示されない場合は、マップのプロジェクトをトラブルシューティングします。  
  
 進みます[手順 10: オーケストレーションを作成](../../adapters-and-accelerators/accelerator-hl7/step-10-create-an-orchestration.md)です。  
  
## <a name="see-also"></a>参照  
 [メッセージの強化のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)