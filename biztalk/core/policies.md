---
title: ポリシー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4d46929ab985008e826bab36ab6e1648d8602e9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394976"
---
# <a name="policies"></a>ポリシー
ポリシーは、ルールの論理的なグループです。 ポリシーのバージョンを作成、保存、ファクトに適用してテストを結果に満足したら、発行し、運用環境にデプロイします。  
  
## <a name="policy-composition"></a>ポリシーの作成  
 ファクトと定義からルールを構築して、ビジネス ルール作成ツールでポリシーを作成できます。 ポリシーは、サイズの大きい任意の規則のセットを含めることができますが、通常、ポリシーを使用するアプリケーションのコンテキスト内で特定のビジネス ドメインに関連するルールからポリシーを作成します。  
  
## <a name="policy-testing"></a>ポリシーのテスト  
 ポリシーのテストの実行は、公開および実稼働環境に展開する前に効果的に行うことができます。 ビジネス ルール作成ツールは、ポリシーのファクトのインスタンスを指定することができます、ポリシーを実行し、その出力を表示します。 出力には、ファクト アクティビティ、ルールの実行、条件の評価、および議題への更新が含まれています。  
  
## <a name="policy-versions"></a>ポリシーのバージョン  
 ポリシーでは、すべてのルールを定義した後は、ポリシーのバージョンを発行できます。 この方法で、ポリシーがロック ダウンされてし、その動作は明確に定義します。  
  
 特定のポリシー バージョンを特定のビジネス環境での状況で使用し、条件が変化したときに、別のバージョンで置き換えられます。 また、新旧両方のバージョンは、さまざまなアプリケーションで同時に使用することができます。  
  
## <a name="policy-deployment"></a>ポリシーの展開  
 ポリシーの運用環境で実行する準備ができたら、ホストするアプリケーションで使用できるようにするデプロイできます。  
  
## <a name="dynamic-policy-updates"></a>ポリシーの動的更新  
 ポリシーの動的更新が、実行中とは別にポリシーを変更することを許可するビジネス プロセス。 作成して、ポリシーの更新バージョンを展開し、ホスト アプリケーションは、ほぼリアルタイムで更新プログラムを組み込むことができます。 この更新プログラム、コードの変更は不要し、そのため、再開発およびアプリケーションを再展開のオーバーヘッドを回避できます。  
  
## <a name="see-also"></a>参照  
 [ビジネス ルール エンジン](../core/business-rules-engine.md)