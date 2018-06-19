---
title: BizTalk Server メッセージング エンジン |Microsoft ドキュメント
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
ms.openlocfilehash: 2f8e0f4fa694699e2dfbc499b6f2fd3440656935
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279266"
---
# <a name="the-biztalk-server-messaging-engine"></a>BizTalk Server メッセージング エンジン
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] メッセージング エンジンでは、ユーザーが複数のアプリケーションにまたがるビジネス プロセスを作成できるように、次の 2 つの重要機能が提供されます。  
  
-   ビジネス プロセスを実行するロジックを指定および実装する方法  
  
-   ビジネス プロセスによって使用されるアプリケーション間の通信メカニズム  
  
 これらの機能を実現する、エンジンの主要なコンポーネントを次に示します。  
  
 ![](../core/media/understandingbts-04-engine4.gif "UnderstandingBTS_04_Engine4")  
  
 メッセージが受信した図が示すような**受信アダプター**です。 アダプターによって通信メカニズムが異なるので、Web サービスへのアクセス、ファイルからの読み取り、またはその他の方法によって、メッセージが取得されます。 メッセージを処理し、**受信パイプライン**です。 このパイプラインにはさまざまなコンポーネントが含まれ、メッセージをネイティブ形式から XML ドキュメントに変換したり、メッセージのデジタル署名を検証するなどの処理が行われます。 メッセージは、という名前のデータベースに配信されます、 **MessageBox**は実装されている Microsoft SQL Server を使用します。  
  
 ビジネス プロセスを実行するロジックは 1 つまたは複数として実装**オーケストレーション**、それぞれが、実行可能コードで構成されています。 C# などの言語でコードを記述して作成するのではなく、 ビジネス アナリスト、または多くの場合は開発者が、適切なツールを使用して定義済みの図形のグループをグラフィカルに体系化し、条件、ループ、およびその他の動作を指定することで作成します。 オーケストレーションを使用できます必要に応じて、**ビジネス ルール エンジン**、単純な提供し、複雑なビジネス プロセス内のルールのセットを表現する方法をより簡単に変更します。  
  
 各オーケストレーションを作成**サブスクリプション**を受信するメッセージの種類を示します。 メッセージ ボックスに配信されたメッセージは、適切なオーケストレーションに送信され、送信先のオーケストレーションでは、ビジネス プロセスに必要とされる操作が行われます。 この処理の結果は通常、オーケストレーションで別のメッセージとして生成され、メッセージ ボックスに保存されます。 このメッセージは、によって処理がさらに、**送信パイプライン**で使用される内部 XML 形式から変換することがあります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]送信先で必要とする形式、デジタル署名と詳細を追加します。 使用して、メッセージは送信し、**送信アダプター**、適切なメカニズムを使用して、このメッセージの送信先が対象のアプリケーションと通信します。  
  
 完全な**ソリューション**上に構築された、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]エンジンは、さまざまな部分を (成果物とも呼ばれます) を含めることができます: オーケストレーション、パイプライン、メッセージ スキーマ、および詳細。 これらの部分、または成果物をできますとして動作する 1 つの単位と呼ばれる、 **BizTalk アプリケーション**です。 BizTalk アプリケーションは、ソリューションに必要なすべての要素を 1 つの論理単位にまとめ、管理および展開の基礎として抽象化したものです。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] エンジンは、さまざまなユーザーの機能の実行に使用できます。 A**ビジネス アナリスト**、たとえば、定義、ルールとビジネス プロセスを構成する動作です。 ビジネス プロセスのフローを決定して、各アプリケーションに送信する情報や、ビジネス ドキュメント間のマッピング方法を定義することができます。 ビジネス アナリストがこのプロセスを定義した後、**開発者**それを実装する BizTalk アプリケーションを作成できます。 この作業には、使用するビジネス ドキュメント用の XML スキーマの定義、ビジネス ドキュメント間の詳細なマッピングの指定、ビジネス プロセスを実装するために必要なオーケストレーションの作成などが含まれます。 **管理者**パート間の通信を設定する、BizTalk アプリケーションの展開を適切かつスケーラブルな方法でおよびその他のタスクを実行する、重要な役割を果たします。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ソリューションを作成および管理するには、ビジネス アナリスト、開発者、および管理者という 3 つすべてのロールが必要です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [システムに接続します。](../core/connecting-systems.md)  
  
-   [ビジネス プロセスの定義](../core/defining-business-processes.md)  
  
-   [管理と監視](../core/management-and-monitoring.md)  
  
-   [エンタープライズ シングル サインオン](../core/enterprise-single-sign-on-sso.md)  
  
## <a name="see-also"></a>参照  
 [BizTalk Server アーキテクチャ](../core/biztalk-server-architecture.md)   
 [ランタイム アーキテクチャ](../core/runtime-architecture.md)