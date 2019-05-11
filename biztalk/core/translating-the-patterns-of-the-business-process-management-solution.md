---
title: ビジネス プロセス管理ソリューションのパターンの変換 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- artifacts, patterns
- patterns [process management solutions], orchestration boundaries
- patterns [process management solutions], translating patterns to artifacts
- orchestrations, patterns
- orchestrations, boundaries
ms.assetid: 69f37732-f235-4bbb-bc85-31b4971c95ce
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 31e9c850e7e73d95decc7eb610a575d8fd2135aa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243515"
---
# <a name="translating-the-patterns-of-the-business-process-management-solution"></a>ビジネス プロセス管理ソリューションのパターンの変換
このセクションでは、ソリューションが BizTalk Server アイテムにパターンの図に変換される方法について説明します。  
  
 ![ビジネス プロセス管理ソリューション パターン](../core/media/bts-cp-business-process-management-patterns.gif "bts_cp_Business_Process_Management_Patterns")  
  
## <a name="connections"></a>接続  
 接続は、ソリューション コンポーネント間のメッセージ パスです。 開始する最も簡単な場所は、サービス インターフェイスです。 BizTalk Server を簡単に Web サービスとしてのオーケストレーションを提示します。 オーケストレーションを web サービスとして公開する方法の詳細については、次を参照してください。 [Web サービスにオーケストレーションをマップする方法](../core/how-to-map-orchestrations-to-web-services.md)します。  
  
 その他の接続には、前処理セクションと、プロセス マネージャの間、プロセス マネージャと処理ステージ間およびサービスと前処理セクションがあります。 接続では、ステージとバックエンド システムの間と、前処理し履歴データベースとサービスのシステム間をも含まれます。  
  
> [!NOTE]
>  翻訳者は、BizTalk マップに対応します。 マップは、さらに、パイプラインの一部または**変換**オーケストレーション図形。  
  
 同期または非同期プロセス マネージャーに接続するための決定には、ある程度の配慮が必要です。 与信審査とは異なり、ケーブル サービス注文などのプロセスで注文の対象は迅速に完了はほとんどありません。 プロセス マネージャへの接続が非同期、相関関係が必要な場合、プロセスの管理のロジックは複雑です。 このソリューションは実際に、メッセージ ボックスにメッセージを発行することによって、プロセス マネージャに非同期接続を使用します。  
  
 プロセス マネージャとステージの間の接続は、サーバー リソースの節約とロジックを簡略化の間で同様のトレードオフを表します。 各ステージでは、プロセス マネージャーよりも短い処理時間があります。 各ステージでは、次の段階で、処理を続行する前にその処理が完了する必要があります。 ただし、各ステージを変更することがあります、ため、プロセス マネージャーことはできません密に結合するステージにします。 アプリケーションでは、限定的なパブリッシュ/サブスクライブ モデルとして、接続を記述できます。 プロセス マネージャーは、単一の専用ポートを介してステージにメッセージを送信します。 ステージは、専用のメッセージを認識するさらに、フィルター処理します。  
  
## <a name="determining-orchestration-boundaries"></a>オーケストレーションの境界を決定します。  
 パターンは次の 3 つの主要な領域に分類されます: ビジネス プロセスとビジネス プロセス自体の管理、メッセージを前処理します。 処理前は、web サービスへの接続を処理、メッセージの応答メッセージを変換すること、サービス システムに通知、履歴データベースにエントリを作成するおよびプロセス マネージャにメッセージを送信で構成されます。 アプリケーションでは、前処理、1 つのオーケストレーションによって処理されます。 ビジネス プロセスの管理は、別のオーケストレーションによって処理されます。 管理されているビジネス プロセスは、適切なステージに分割されます。 各ステージは、注文プロセスの変更に伴う追加や削除を許可するためのオーケストレーションに対応します。 注文処理ステージのデザインの詳細についてを参照してください「ビジネス プロセスの分割」 [、ビジネス プロセス管理ソリューションの一部の設計原則](../core/some-design-principles-in-the-business-process-management-solution.md)します。  
  
## <a name="translating-the-components-into-orchestrations"></a>コンポーネントのオーケストレーションへの変換  
 最初のオーケストレーション**OrderBroker**を直接単純にダイアグラムを変換します。 オーケストレーションは、主にマッピング図形がプロセス マネージャーの通知メッセージと注文メッセージを構築するために使用します。 オーケストレーション図形の一覧については、次を参照してください。[オーケストレーション図形](../core/orchestration-shapes.md)します。  
  
 プロセス マネージャとそのサテライト アセンブリのロジックは、やや複雑です。 プロセス マネージャのオーケストレーションのロジックについて**OrderManager**を参照してください[プロセス マネージャのロジック](../core/process-manager-logic.md)します。  
  
## <a name="see-also"></a>参照  
 [ビジネス プロセス管理ソリューションのパターン](../core/patterns-in-the-business-process-management-solution.md)   
 [パターンと設計: ビジネス プロセス管理ソリューション](../core/designing-with-patterns-the-business-process-management-solution.md)   
 [ビジネス プロセス管理ソリューションのパターン カタログ](../core/pattern-catalog-for-the-business-process-management-solution.md)