---
title: サービスの実装の要点指向のソリューション |Microsoft Docs
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
ms.openlocfilehash: 47cc270e442964d46307a81c097df18085696107
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332501"
---
# <a name="implementation-highlights-of-the-service-oriented-solution"></a>サービスの実装の要点指向のソリューション
ソリューションでは、特定のコンテキストで特定の問題は解決します。 サービス指向ソリューションは例外ではありませんし、Microsoft に固有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]とシナリオ。 Woodgrove Bank シナリオの詳細については、次を参照してください。[サービス指向ソリューションを理解する](../core/understanding-the-service-oriented-solution.md)します。  
  
 シナリオの開発中に、いくつかの領域は、応答時間を許容できるレベルに削減するためにボトルネックになることがわかりました。 アダプターを使用して、バックエンド システムにメッセージを送信すると、応答の取得に長い待ち時間が導入されています。 一般的に、アダプタ自体は非常に低待機時間を提供します。 ただし、BizTalk の分散アーキテクチャでは、メッセージ ボックスを使用してオーケストレーションのホスト インスタンスとの通信にアダプターが必要です。 このため、データベースへのラウンド トリップが発生して、待機時間が影響を受けます。 このため、ソリューション (最速のバージョン) ビルドのインライン バージョン、オーケストレーション自体のアダプター機能は、バックエンド システムを直接呼び出します。 次の 3 つの異なるバックエンド システムでは、可能性のあるバックエンド システムとの通信に次の 3 つの異なるメカニズムを意味します。  
  
 パフォーマンスの問題のことを証明した別の領域は、構成データからエンタープライズ シングル サインオン (SSO) を取得されました。 取得時間を短縮する一方、利便性や一般性を保持するには、ソリューションは、構成値をローカル キャッシュを使用します。 SSO を使用すると、構成データの簡単な管理もできます。 待機時間とパフォーマンス要件を満たすホスト インスタンスを追加では、ホスト インスタンスを実行するサーバー上の設定を変更する必要はありません。  
  
 コードから直接パイプラインの呼び出しは、ソリューションの別の例外的な要素です。 これにより、カスタム パイプライン コンポーネントの再利用できます。  
  
 最後に、でも上げたい場合は、ソリューションの速度の最後のビットを変更することがいくつかの BizTalk Server の設定があります。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [バックエンドの呼び出しのインライン化](../core/inlining-back-end-invocation.md)  
  
-   [サービスで効率的に SSO を使用して指向ソリューション](../core/using-sso-efficiently-in-the-service-oriented-solution.md)  
  
-   [サービスからのパイプラインを使用して指向ソリューション](../core/using-pipelines-from-the-service-oriented-solution.md)  
  
-   [チューニング、サービス指向ソリューション](../core/tuning-the-service-oriented-solution.md)  
  
-   [トランスポートの種類の分離と処理](../core/decoupling-transport-type-and-processing.md)