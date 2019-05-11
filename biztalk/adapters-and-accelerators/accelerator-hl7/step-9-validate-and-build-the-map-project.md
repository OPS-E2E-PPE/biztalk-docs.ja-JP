---
title: 手順 9:検証し、マップ プロジェクトのビルド |Microsoft Docs
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
ms.openlocfilehash: 0f41cc3bbe235dfda75563d94ae0173737a58c75
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65286635"
---
# <a name="step-9-validate-and-build-the-map-project"></a>手順 9:検証し、マップ プロジェクトのビルド
この手順で使用する、**マップの検証**コマンドをマップ、内部の不整合が含まれていますかを妨げる、マッピング スキーマを効果的に使用されているその他の問題があるかを判断します。 また、作成したリソース (スキーマおよびマップ) を含むアセンブリを生成するプロジェクトをビルドします。 またこれにより、これまでに完了した作業でコンパイル エラーがないこと。  
  
### <a name="to-validate-the-map-project"></a>マップのプロジェクトを検証するには  
  
1.  ソリューション エクスプ ローラーで右クリックし、 **DoorbellMap.btm**マップ、およびクリックして**マップの検証**です。  
  
2.  成功メッセージが出力ウィンドウに表示されることを確認します。 送信先スキーマ内のすべての利用可能な要素にマップしているのではないために、いくつかの警告が表示されます。  
  
     成功メッセージが表示されない場合は、マップのプロジェクトをトラブルシューティングします。  
  
### <a name="to-build-the-map-project"></a>マップのプロジェクトをビルドするには  
  
- ソリューション エクスプ ローラーで右クリックして**BTAHL7 プロジェクト**、 をクリックし、**ビルド**します。 成功メッセージが出力ウィンドウに表示されることを確認します。  
  
   成功メッセージが表示されない場合は、マップのプロジェクトをトラブルシューティングします。  
  
  続行する[手順 10。オーケストレーションを作成する](../../adapters-and-accelerators/accelerator-hl7/step-10-create-an-orchestration.md)します。  
  
## <a name="see-also"></a>参照  
 [メッセージ強化のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)