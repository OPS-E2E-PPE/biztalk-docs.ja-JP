---
title: "ポリシー |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Business Rules Engine, policies
- policies, about policies
- policies, deploying
- policies, Business Rules Engine
- policies
- business rules, policies
- policies, versioning
- policies, testing
- policies, creating
- policies, updating
ms.assetid: 2e0ae081-938d-4e2a-947e-1c0ecfebb4b8
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0bd05d6cf67d89ee811cac45ac3950697db74f59
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="policies"></a>ポリシー
ポリシーはルールの論理的なグループです。 あるバージョンのポリシーを作成し、保存し、ファクトに適用してテストし、目的の結果が得られた場合には、公開して実稼働環境に展開することができます。  
  
## <a name="policy-composition"></a>ポリシーの作成  
 ビジネス ルール作成ツールで、ファクトおよび定義からルールを構築することによりポリシーを作成できます。 ポリシーには、任意の大きさのルールのセットを含めることができますが、通常は、ポリシーを使用するアプリケーションのコンテキスト内で特定のビジネス ドメインに関連するポリシーを作成します。  
  
## <a name="policy-testing"></a>ポリシーのテスト  
 ポリシーを実稼働環境で公開および展開する前に、ポリシーのテスト実行を効果的に行うことができます。 ビジネス ルール作成ツールを使用して、ファクトのインスタンスをポリシーに提供し、ポリシーを実行し、その出力を表示することができます。 出力に含まれるのは、ファクト アクティビティ、ルールの実行、条件の評価、および議題への更新です。  
  
## <a name="policy-versions"></a>ポリシー バージョン  
 ポリシーのルールをすべて定義した後で、ポリシー バージョンを公開できます。 この方法では、ポリシーがロック ダウンされ、動作が厳密に定義されます。  
  
 ビジネス環境の特定の条件セットの下で、特定のポリシー バージョンを使用できます、条件が変化した場合には別のバージョンで置き換えることができます。 また、新旧バージョンの両方を異なるアプリケーションで同時に使用することもできます。  
  
## <a name="policy-deployment"></a>ポリシーの展開  
 ポリシーを実稼働環境で実行する準備が整ったら、ポリシーを展開し、ホストするアプリケーションで利用できるようにすることができます。  
  
## <a name="dynamic-policy-updates"></a>ポリシーの動的更新  
 ポリシーの動的更新により、実行中のビジネス プロセスとは別にポリシーを修正できます。 ポリシーの更新済みバージョンを作成および展開できます。ホストするアプリケーションは、ほとんどリアルタイムで更新を組み込むことができます。 この更新ではコードを変更する必要がないため、アプリケーションの再開発および再展開のオーバーヘッドを回避できます。  
  
## <a name="see-also"></a>参照  
 [ビジネス ルール エンジン](../core/business-rules-engine.md)