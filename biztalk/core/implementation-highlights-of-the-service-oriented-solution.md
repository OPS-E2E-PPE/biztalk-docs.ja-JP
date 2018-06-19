---
title: サービスの実装の要点指向ソリューション |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service solution tutorial, performance
- performance, service solutions
- service solution tutorial, implementing
ms.assetid: 3dbd8dfd-45b7-4290-ba07-b0c5e6264629
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c593c24c72e5666525001e6a52e2b0bf6eac2de
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257754"
---
# <a name="implementation-highlights-of-the-service-oriented-solution"></a>指向ソリューションのサービスの実装の要点
ソリューションは、特定のコンテキストの特定の問題を解決します。 サービス指向ソリューションも例外ではなく、Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] とそのシナリオに固有のソリューションです。 Woodgrove Bank シナリオの詳細については、次を参照してください。[サービス指向ソリューションを理解する](../core/understanding-the-service-oriented-solution.md)です。  
  
 シナリオを開発する際、応答時間を許容できるレベルに減らす上でボトルネックになる領域がいくつかあります。 アダプタを使用してメッセージをバックエンド システムに送信すると、応答を返す待機時間が長くなります。 通常、アダプタ自体の待機時間は非常に短いものです。 ただし、BizTalk の分散アーキテクチャには、メッセージ ボックスを使用してオーケストレーションのホスト インスタンスと通信するアダプタが必要です。 このため、データベースへのラウンド トリップが発生して、待機時間が影響を受けます。 そのため、インライン バージョンのソリューション (最速のバージョン) は、オーケストレーション自体がバックエンド システムを直接呼び出すようにアダプタの機能を構築します。 バックエンド システムが 3 種類あるため、3 つの異なるメカニズムを使用して、バックエンド システムと通信する可能性があります。  
  
 パフォーマンスの問題が発生した別の領域では、エンタープライズ シングル サインオン (SSO) から構成データを取得していました。 取得時間を短縮する一方で利便性や一般性を保持するため、このソリューションでは、構成値にローカル キャッシュを使用します。 SSO を使用しても、構成データを簡単に管理できます。 待機時間とパフォーマンスの要件を満たすホスト インスタンスを追加する場合、ホスト インスタンスを実行するサーバーの設定を変更する必要はありません。  
  
 このソリューションの他の例外的な要素では、コードから直接パイプラインを呼び出します。 このため、カスタム パイプライン コンポーネントを再利用できます。  
  
 最後に、このソリューションの速度を少しでも上げたい場合、複数の BizTalk Server 設定を変更できます。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [バック エンド呼び出しのインライン展開](../core/inlining-back-end-invocation.md)  
  
-   [指向ソリューションのサービスで SSO の効率的な使用](../core/using-sso-efficiently-in-the-service-oriented-solution.md)  
  
-   [サービスからパイプラインを使用して指向ソリューション](../core/using-pipelines-from-the-service-oriented-solution.md)  
  
-   [チューニング サービス指向ソリューション](../core/tuning-the-service-oriented-solution.md)  
  
-   [トランスポートの種類の分離と処理](../core/decoupling-transport-type-and-processing.md)