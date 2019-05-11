---
title: BizTalk Server メッセージング エンジン |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c0c8d3e6-953d-4a04-adfc-b77ef7173464
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2fef92690d569c36d5799e027090fcf4fa9a0f98
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65298819"
---
# <a name="the-biztalk-server-messaging-engine"></a>BizTalk Server メッセージング エンジン
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージング エンジンが 2 つの重要な機能を提供することで複数のアプリケーションにまたがるビジネス プロセスを作成できます。  
  
- 指定し、そのビジネス プロセスを促進するロジックを実装する方法  
  
- ビジネス プロセスを使用するアプリケーション間で通信するためのメカニズム  
  
  次の図は、これら 2 つの問題に対処する、エンジンの主要なコンポーネントを示しています。  
  
  ![](../core/media/understandingbts-04-engine4.gif "UnderstandingBTS_04_Engine4")  
  
  を通じてメッセージを受信、図に示すよう、**受信アダプター**します。 異なるアダプター提供通信メカニズムが異なるため、Web サービスにアクセスして、メッセージが取得されますまたはその他の何らかの方法で、ファイルからの読み取り。 経由でメッセージが処理されます、**受信パイプライン**します。 このパイプラインは、ネイティブ形式からメッセージをやメッセージのデジタル署名を検証する、XML ドキュメントに変換するなどの処理を実行するさまざまなコンポーネントを含めることができます。 メッセージがという名前のデータベースに配信し、**メッセージ ボックス**、Microsoft SQL Server を使用して実装されます。  
  
  ビジネス プロセスを実行するロジックは、1 つまたは複数として実装されます**オーケストレーション**、それぞれが、実行可能コードで構成されています。 などの言語でコードを記述することで、これらのオーケストレーションは作成されませんC#、ただしします。 代わりに、ビジネス アナリストまたは開発者の多くの場合は、適切なツールを使用して条件、ループ、およびその他の動作を表現する図形の定義済みグループをグラフィカルに体系化します。 オーケストレーションを使用できます必要に応じて、**ビジネス ルール エンジン**を簡単に提供して、複雑なビジネス プロセス内のルールのセットを表現する方法を簡単に変更の詳細は、します。  
  
  各オーケストレーションを作成します**サブスクリプション**を受信するメッセージの種類を示します。 メッセージ ボックスで、適切なメッセージが到着すると、そのメッセージは、目的のオーケストレーションをビジネス プロセスに必要なあらゆるアクションを受け取るにディスパッチされます。 この処理の結果は、一般的に別のメッセージをオーケストレーションによって生成され、メッセージ ボックス データベースに保存します。 このメッセージは、によって処理がさらに、**送信パイプライン**で使用される内部 XML 形式から変換することがあります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]送信先で必要な形式にし、デジタル署名を追加します。 使用して、メッセージが送信し、**送信アダプター**、このメッセージの送信先が対象のアプリケーションとの通信に適切なメカニズムを使用します。  
  
  完全な**ソリューション**上に構築された、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]エンジンは、さまざまな部分を (成果物とも呼ばれます) を含めることができます。 オーケストレーション、パイプライン、メッセージ スキーマ、およびします。 これらのパーツ、または成果物と呼ばれる 1 つの単位として協力できる、 **BizTalk アプリケーション**します。 BizTalk アプリケーションは、すべての管理および展開の基本的な抽象化を行うことの 1 つの論理単位をソリューションに必要な部分をラップします。  
  
  さまざまなユーザーを使用して別の関数の実行、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]エンジン。 A**ビジネス アナリスト**ルールやビジネス プロセスを構成する動作に、たとえば、定義可能性があります。 ユーザー フローを決定、ビジネス プロセスの各アプリケーションに送信する情報を定義して、1 つのビジネス ドキュメントは別にマップする方法。 ビジネス アナリストが、このプロセスを定義した後、**開発者**それを実装する BizTalk アプリケーションを作成できます。 これには、使用されるビジネス ドキュメントの XML スキーマの定義、間に、詳細なマッピングを指定して、オーケストレーションのプロセスを実装するために必要な作成などが含まれます。 **管理者**によって、各要素間の通信の設定、適切かつスケーラブルな方法で BizTalk アプリケーションの展開およびその他のタスクを実行する重要な役割を果たします。 3 つすべてのロール、ビジネス アナリスト、開発者、および管理者-作成および管理するために必要な[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューション。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [システムの接続](../core/connecting-systems.md)  
  
-   [ビジネス プロセスの定義](../core/defining-business-processes.md)  
  
-   [管理と監視](../core/management-and-monitoring.md)  
  
-   [Enterprise Single Sign-On](../core/enterprise-single-sign-on-sso.md)  
  
## <a name="see-also"></a>参照  
 [BizTalk Server アーキテクチャ](../core/biztalk-server-architecture.md)   
 [ランタイム アーキテクチャ](../core/runtime-architecture.md)