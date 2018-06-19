---
title: オーケストレーションに関する |Microsoft ドキュメント
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
ms.openlocfilehash: 0bd3c1abeeb2c42c399a54aea4ba0128cc19bcd8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225138"
---
# <a name="about-orchestrations"></a>オーケストレーションについて
オーケストレーションは、XLANG/s 言語に基づいて実行可能なビジネス プロセスを示すための、柔軟で強力なツールです。 XLANG/s は、C# の表現機能を備えたメッセージング言語と見なすことができます。 フローの設計、データの解釈および生成、カスタム コードの呼び出しが可能であり、直感的に見てわかる図で、プロセス全体を編成できます。また実行時には、BizTalk オーケストレーション エンジンが、BizTalk オーケストレーション デザイナーで生成された実行可能なビジネス プロセスである XLANG/s ファイルを実行します。  
  
 オーケストレーションで送受信されるメッセージと、送受信されるメッセージが通過するポートは、オーケストレーションの基本的な要素です。 メッセージは、オーケストレーションが外部と通信するための手段です。このメッセージに基づいて、e ビジネスが実施されます。  
  
 **受信**と**送信**図形をオーケストレーションにメッセージを受信し、そこからメッセージを送信する必要がある機能をカプセル化します。 オーケストレーションの論理的なフローを作成するためには、オーケストレーション デザイナーに用意されているさまざまな図形について理解する必要があります。  
  
 Web サービス、関連付け、長時間実行されるトランザクションなど、オーケストレーションの高度な概念を理解してください。 これらの機能をすべて使用する必要はありませんが、どのような機能を持つか理解しておくと便利です。  
  
 Web サービスは、WSDL (Web Services Description Language) に規定されている標準準拠のインターフェイスを備えたプログラムです。 メッセージの種類、ポート、ポートの種類、および標準的な操作方法を定義することで、異種システムの相互通信を効率的に実行できます。  
  
 関連付けは、実行中のオーケストレーションの特定インスタンスに、メッセージを関連付けるためのメカニズムです。関連付けを使用すると、多くのインスタンスが実行され多くのメッセージが送受信されている場合に、ビジネス プロセスで適切な情報を得ることができます。  
  
 トランザクションを使用すると、予期しない問題が発生した場合にも、オーケストレーションの状態を適切に維持することができます。 オーケストレーション デザイナーでは、さまざまな例外処理機能を利用できます。これにより、適切に設定された、わかりやすい方法でエラーを処理できます。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [オーケストレーション デザイン画面](../core/the-orchestration-design-surface.md)  
  
-   [BizTalk オーケストレーション タブ、ツールボックス](../core/biztalk-orchestrations-tab-toolbox.md)  
  
-   [オーケストレーションの開発手順](../core/steps-in-orchestration-development.md)  
  
-   [オーケストレーションを開発するためのセキュリティに関する考慮事項](../core/security-considerations-for-developing-orchestrations.md)  
  
-   [XLANG の言語](../core/xlang-s-language.md)  
  
-   [BizTalk オーケストレーション エンジンについて](../core/about-the-biztalk-orchestration-engine.md)