---
title: オーケストレーションについて |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations
- Orchestration Designer
- orchestrations, about orchestrations
- Orchestration Designer, about Orchestration Designer
ms.assetid: c0d9a3fb-da87-42cc-9e9e-e2c37232e606
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8517433777e57b9811ec16ce08bb12ada139ee4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362321"
---
# <a name="about-orchestrations"></a>オーケストレーションについて
オーケストレーションは、xlang/s 言語に基づいて、実行可能なビジネス プロセスを表す、柔軟で強力なツールです。 一部の式の機能を備えたメッセージング言語として XLANG/秒を表示できますC#します。 フローの設計、解釈し、データを生成、カスタム コードの呼び出しの直感的なビジュアルの描画では、プロセス全体を整理したりできます、実行時に、BizTalk オーケストレーション エンジンはいる実行可能なビジネス プロセスである xlang/s ファイルを実行しますBizTalk オーケストレーション デザイナーによって生成されます。  
  
 メッセージ、送信と、それを操作するアクションを受け取るし、転送されるポートはオーケストレーションのすべての基本的な要素です。 メッセージは、外部および e ビジネスが実施して、オーケストレーションが通信中です。  
  
 **受信**と**送信**図形をオーケストレーションにメッセージを受信し、そこからメッセージを送信する必要がある機能をカプセル化します。 オーケストレーションの論理フローを表すオーケストレーション デザイナーを提供するさまざまな図形を理解する必要があります。  
  
 Web サービス、相関、および実行時間の長いトランザクションなどの高度なオーケストレーションの概念を理解する必要があります。 すべてのこれらの機能を使用する必要はありませんを実行できるかを把握することをお勧めします。  
  
 Web サービスは、Web サービス記述言語 (WSDL) で規定されている標準に準拠しているインターフェイスを持つプログラムです。 標準的な方法でメッセージの種類、ポート、ポートの種類、および操作を定義すると、異種システムと通信できる効果的に相互します。  
  
 相関関係は、多くのインスタンスが実行され、多くのメッセージが前後へ送信されるときに、ビジネス プロセスが適切な情報を取得できるようにするメッセージが、オーケストレーションの実行中の特定のインスタンスに関連付けられたメカニズムです。  
  
 トランザクションでは、予期しない問題が発生した場合、オーケストレーションの状態を適切に維持することができます。 オーケストレーション デザイナーには、制御され、予測可能な方法でエラーを処理するための例外を処理するさまざまな方法が用意されています。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [オーケストレーション デザイン サーフェイス](../core/the-orchestration-design-surface.md)  
  
-   [[BizTalk オーケストレーション] タブ (ツールボックス)](../core/biztalk-orchestrations-tab-toolbox.md)  
  
-   [オーケストレーションの開発手順](../core/steps-in-orchestration-development.md)  
  
-   [オーケストレーションを開発する際のセキュリティ上の注意](../core/security-considerations-for-developing-orchestrations.md)  
  
-   [XLANG-s 言語](../core/xlang-s-language.md)  
  
-   [BizTalk オーケストレーション エンジンについて](../core/about-the-biztalk-orchestration-engine.md)