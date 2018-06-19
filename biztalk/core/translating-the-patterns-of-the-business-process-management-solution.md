---
title: ビジネス プロセス管理ソリューションのパターンの変換 |Microsoft ドキュメント
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
ms.openlocfilehash: 23603e66e80461baecea88648100442eb9da0166
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279098"
---
# <a name="translating-the-patterns-of-the-business-process-management-solution"></a>ビジネス プロセス管理ソリューションのパターンの変換
このセクションでは、このソリューションでパターン ダイアグラムがどのように BizTalk Server のアイテムに変換されるかを説明します。  
  
 ![ビジネス プロセス管理ソリューション パターン](../core/media/bts-cp-business-process-management-patterns.gif "bts_cp_Business_Process_Management_Patterns")  
  
## <a name="connections"></a>接続  
 接続はソリューション コンポーネント間のメッセージ パスです。 サービス インターフェイスから始めるのが最も簡単です。 BizTalk Server ではオーケストレーションを簡単に Web サービスとして公開できます。 オーケストレーションを web サービスとして公開する方法については、次を参照してください。 [Web サービスにオーケストレーションをマップする方法](../core/how-to-map-orchestrations-to-web-services.md)です。  
  
 サービスと前処理セクションの間、前処理セクションとプロセス マネージャの間、およびプロセス マネージャと処理ステージの間にも接続があります。 ステージとバックエンド システムの間の接続、前処理と履歴データベースとサービス システムの間の接続もあります。  
  
> [!NOTE]
>  変換者は BizTalk マップに対応し、 マップは、さらに、パイプラインの一部または**変換**オーケストレーション図形です。  
  
 プロセス マネージャへの接続を同期接続と非同期接続のどちらにするかを決定するには、いくらか検討を要します。 たとえばクレジット チェックのような処理とは異なり、ケーブル サービスの注文などのプロセスに含まれる注文は、その場で終わらないのが普通です。 プロセス マネージャへの接続を非同期にした場合、それが関連付けを要する接続であれば、プロセス管理のロジックが複雑になります。 そのためこのソリューションでは、メッセージ ボックスにメッセージを発行することによって、プロセス マネージャに非同期接続します。  
  
 プロセス マネージャとステージの間の接続においても、サーバー リソースの節約とロジックの簡略化との間で同様のトレードオフが生じます。 ステージの処理時間はプロセス マネージャの処理時間より短く、 各ステージでの処理は次のステージに進む前に終了している必要があります。 ところが、ステージは変更される可能性もあるので、プロセス マネージャをステージに密結合することはできません。 アプリケーション内では、制限された公開/サブスクライブ モデルとして接続を記述できます。 プロセス マネージャは単一の専用ポートを介してメッセージをステージに送信します。 一方、各ステージは、フィルタを使用してそのステージに向けられたメッセージを識別します。  
  
## <a name="determining-orchestration-boundaries"></a>オーケストレーションの境界の決定  
 パターンは、次の 3 つの主要な領域: ビジネス プロセスとビジネス プロセス自体の管理、メッセージを前処理します。 前処理では、Web サービスへの接続、メッセージの応答メッセージへの変換、サービス システムへの通知、履歴データベースへの記入、およびプロセス マネージャへのメッセージの送信が行われます。 アプリケーションでは、前処理は単一のオーケストレーションによって行われます。 ビジネス プロセスの管理は別のオーケストレーションによって行われます。 ビジネス プロセスは適切なステージに分割されて管理されます。 各ステージは 1 つのオーケストレーションに対応します。これによって発注プロセスの変更に伴う追加や削除が可能になります。 注文処理ステージの設計に関する詳細についてを参照してください「ビジネス プロセスの分割」[ビジネス プロセス管理ソリューションで一部の設計原則](../core/some-design-principles-in-the-business-process-management-solution.md)です。  
  
## <a name="translating-the-components-into-orchestrations"></a>コンポーネントのオーケストレーションへの変換  
 最初のオーケストレーション**OrderBroker**、単に、直接、ダイアグラムを変換します。 このオーケストレーションでは主に、プロセス マネージャの通知メッセージと注文メッセージの作成に使用する図形をマップします。 オーケストレーション図形の一覧については、次を参照してください。[オーケストレーション図形](../core/orchestration-shapes.md)です。  
  
 プロセス マネージャとそのサテライト アセンブリのロジックは多少複雑です。 プロセス マネージャのオーケストレーションのロジックについて**OrderManager**を参照してください[プロセス マネージャのロジック](../core/process-manager-logic.md)です。  
  
## <a name="see-also"></a>参照  
 [ビジネス プロセス管理ソリューションのパターン](../core/patterns-in-the-business-process-management-solution.md)   
 [パターンを使用したデザイン: ビジネス プロセス管理ソリューション](../core/designing-with-patterns-the-business-process-management-solution.md)   
 [ビジネス プロセス管理ソリューションのパターン カタログ](../core/pattern-catalog-for-the-business-process-management-solution.md)