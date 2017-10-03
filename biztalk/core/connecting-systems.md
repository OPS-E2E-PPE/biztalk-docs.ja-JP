---
title: "システム接続 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4c4895e5-7272-415f-a0de-905256fa0a43
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67d042d067fa68c6d54d95f3b0e658c20db4961d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="connecting-systems"></a>システムの接続
異なるコンピュータ上の異なるソフトウェアの間で効率的にメッセージを交換することは、統合に必要な絶対条件です。 通信方式が多様化している現在、多種多様なプロトコルとメッセージ形式に対応できることが [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] の必須条件となります。 次に説明するように、この通信の実現にはエンジンのかなりの部分が充てられていますが、 エンジンが機能するには、内部で XML ドキュメントを使用する必要があるということも重要なポイントです。 メッセージはどのような形式で届いた場合も、受信後に XML ドキュメントに変換される必要があります。 同様に、受信者がドキュメントを XML 形式で受信できない場合、ドキュメントはエンジンによって受信先に必要な形式に変換されます。  
  
## <a name="sending-and-receiving-messages-adapters"></a>メッセージの送受信: アダプター  
 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] と他のさまざまなソフトウェアとの通信を実現するには、アダプターが必要です。 アダプタは、特定プロトコルなどの通信メカニズムを実装したものです。 開発者は、状況に応じて使用するアダプタを決定します。 たとえば、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] には組み込みのアダプターが用意されているので、その中から必要なアダプターを選択できます。また、Windows SharePoint Services などの一般的な製品用に作成されたアダプターを使用したり、カスタム アダプターを作成することもできます。 いずれの場合も、アダプタはアダプタ フレームワークという標準を基盤に構築されます。 このフレームワークでは、アダプタを作成および実行するための共通の方法が提供され、あらゆる種類のアダプタを同じツールで管理できるようになっています。  
  
 Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] には次のネイティブ アダプターが含まれます。  
  
-   ファイル アダプター: から読み取ると、Windows ファイル システムのファイルへの書き込みをサポートします。 ビジネス プロセスに関連するアプリケーションは、ローカルまたはネットワーク上で、頻繁に同じファイル システムにアクセスする可能性があり、ファイル経由のメッセージ交換は、便利な選択肢になると考えられます。  
  
-   FTP アダプター: ファイル転送プロトコル (FTP) サーバーと BizTalk Server 間で情報の送受信をサポートしています。  
  
-   HTTP アダプター: HTTP を使用して情報の送受信をサポートしています。 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] では、1 つ以上の URL を公開して、他のアプリケーションからエンジンにデータを送信できるようにします。また、このアダプターを使用して、他の URL にデータを送信できます。  
  
-   MSMQ アダプター: Microsoft メッセージ キュー (MSMQ) を使用してメッセージの送受信をサポートしています。  
  
-   WebSphere MQ アダプター: (旧称 MQSeries)、IBM WebSphere MQ を使用してメッセージの送受信をサポートしています。  
  
-   POP3 アダプター: 電子メール メッセージと Post Office Protocol (POP3) のバージョン 3 を使用してその添付ファイルの受信をサポートします。  
  
-   SMTP アダプター: SMTP を使用してメッセージの送信をサポートします。 パーティの識別には標準の電子メール アドレスが使用されます。  
  
-   SOAP アダプター: Web サービス要求の送受信をサポートし、BizTalk Server が Web サービスに接続できるようにします。  
  
-   WCF アダプター: Windows Communication Foundation を使用した情報の送受信をサポートします。  
  
-   Windows SharePoint Services (WSS) アダプター: にアクセスして、Microsoft Windows SharePoint ドキュメント ライブラリに格納されているドキュメントの公開をサポートします。  
  
 次のような一般的に使用されているビジネス ソフトウェア用のアダプタも Microsoft から入手できます。  
  
-   Microsoft BizTalk Adapter for JD Edwards OneWorld  
  
-   Microsoft BizTalk Adapter for JD Edwards EnterpriseOne  
  
-   Microsoft BizTalk Adapter for PeopleSoft Enterprise  
  
-   Microsoft BizTalk Adapter for TIBCO Rendezvous  
  
-   Microsoft BizTalk Adapter for TIBCO Enterprise Message Service  
  
 これらのアダプターの詳細については、次を参照してください。 [BizTalk Server のアダプター](../core/adapters-in-biztalk-server.md)です。  
  
 データ受信に使用されるアダプタの種類に関係なく、受信されたメッセージにオーケストレーションがアクセスするには、通常その前に処理が必要です。 同様に、オーケストレーションで生成された送信メッセージをアダプタから送信するには、多くの場合、その前に処理が必要です。  
  
## <a name="processing-messages-pipelines"></a>メッセージの処理: パイプライン  
 ビジネス プロセスを基になるアプリケーションは、さまざまな種類のドキュメントを交換して通信します。 例については、注文や請求書を購入します。 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] アプリケーションでビジネス プロセスを実行するには、これらのドキュメントを含むメッセージを適切に処理できる必要があります。 この処理には複数のステップが含まれる場合があるため、処理はメッセージ パイプラインによって実行されます。 受信メッセージは受信パイプラインで処理され、送信メッセージは送信パイプラインで処理されます。  
  
 たとえば、たとえより多くのアプリケーションが設計されて、XML ドキュメントを理解する多く — おそらく大半今日-ことはできません。 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] は内部で XML ドキュメントのみを使用するため、他のアプリケーションに対して、XML とそれ以外の形式の間の変換手段を提供する必要があります。 また、メッセージの送信者の認証など、その他のサービスも必要になる場合があります。 これらのタスクおよびその他のタスクをモジュール単位のカスタマイズ可能な方法で処理できるよう、パイプラインは複数のステージから構築されています。各ステージには、1 つ以上の有効な .NET コンポーネントまたはコンポーネント オブジェクト モデル (COM) コンポーネントが含まれ、 それぞれのコンポーネントで特定部分のメッセージ処理が行われます。 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]最も一般的なケースに対処するいくつかの標準的なコンポーネントを提供します。 これらのコンポーネントで十分でない場合、開発者は受信パイプラインと送信パイプラインの両方に、カスタム コンポーネントを作成することもできます。  
  
 ![](../core/media/understandingbts-05-pipelinereceive.gif "UnderstandingBTS_05_PipelineReceive")  
  
 上の図は、受信パイプラインのステージと、各ステージに用意されている標準のコンポーネントを示しています。 各ステージとその関連コンポーネントは次のとおりです。  
  
-   デコード:[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]この段階では、MIME/SMIME デコーダーの 1 つの標準的なコンポーネントを提供します。 MIME または Secure MIME (S/MIME) 形式のメッセージとその添付ファイルを処理できます。 このコンポーネントはこの 2 種類の形式のメッセージを XML に変換します。また、S/MIME メッセージの暗号化を解読し、メッセージのデジタル署名を確認することもできます。  
  
-   逆アセンブルします。 次の 3 つの標準的なコンポーネントが提供されます。 1 つ目は "フラット ファイル逆アセンブラ" コンポーネントで、フラット ファイルを XML ドキュメントに変換します。 フラット ファイルは位置が指定されている (各レコードの長さと構造が同じ) か、ファイル内で指定された文字によりレコードが区切られています。 2 つ目は "XML 逆アセンブラ" コンポーネントで、既に XML で記述されている受信メッセージを解析します。 3 つ目は "BizTalk Framework 逆アセンブラ" コンポーネントで、現在ではあまり使用されていません。 これは、BizTalk Server 2000 で実装された BizTalk フレームワークによって定義された信頼性の高いメッセージング メカニズムを使用して送信されるメッセージを受け取ります。  
  
-   検証:[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]このステージの XML 検証コンポーネントを提供します。 名前のとおりこのコンポーネントは、逆アセンブル ステージで作成された XML ドキュメントを特定のスキーマまたはスキーマ グループと照合して検証し、ドキュメントがこれらのスキーマの 1 つに準拠していない場合はエラーを返します。  
  
-   パーティの解決: この段階では、パーティの解決の唯一の標準のコンポーネントは、このメッセージの送信者の id の決定を試みます。 メッセージがデジタル署名されている場合は、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] の管理データベース内の Windows ID を検索するのに署名が使用されます  (後で説明するように、このデータベースは BizTalk Server の管理ツールでも使用されます)。メッセージに Windows ユーザーの認証済みセキュリティ識別子 (SID) が指定されている場合は、SID が使用されます。 どちらの方法でも成功しない場合は、メッセージ送信者に既定の匿名 ID が割り当てられます。  
  
 ![](../core/media/understandingbts-06-pipelinesend.gif "UnderstandingBTS_06_PipelineSend")  
  
 送信メッセージも移動できます複数の段階を使用して、送信パイプラインによって定義されています。 上の図は、送信パイプラインのステージと標準のコンポーネントを示しています。 これらは次のとおりです。  
  
-   プリアセンブル: 標準的なコンポーネントは提供されません。 代わりに、このステージには必要に応じてカスタム コンポーネントを挿入できます。  
  
-   アセンブリ: 受信パイプラインの逆アセンブル ステージと並行して、このステージも、次の 3 つの標準的なコンポーネントを持っています。 1 つ目は "フラット ファイル アセンブラ" コンポーネントで、XML メッセージを位置指定のフラット ファイルか区切られたフラット ファイルに変換します。2 つ目は "XML アセンブラ" コンポーネントで、送信 XML メッセージへのエンベロープの追加やその他の変更をサポートします。 3 つ目は "BizTalk Framework アセンブラ" コンポーネントで、BizTalk Framework メッセージング テクノロジを使用して、信頼できる送信を行うためにメッセージをパッケージ化します。  
  
-   エンコード:[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]このステージでは、MIME/SMIME エンコーダーは、1 つだけの標準的なコンポーネントを定義します。 送信メッセージを MIME または S/MIME 形式でパッケージ化します。 S/MIME を使用する場合は、メッセージにデジタル署名を追加したりメッセージを暗号化できます。  
  
 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] では、既定のパイプラインがいくつか定義されています。たとえば、既に XML で記述されているメッセージを処理するための、1 組の単純な受信パイプラインと送信パイプラインが用意されています。 開発者は、パイプライン デザイナを使用して、カスタム パイプラインを作成することもできます。 このツールは [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 内で実行します。開発者は提供されるグラフィカル インターフェイスを使用して、コンポーネントをドラッグ アンド ドロップし、必要な動作のパイプラインを作成できます。  
  
## <a name="choosing-messages-subscriptions"></a>メッセージの選択: サブスクリプション  
 アダプタと受信パイプラインでメッセージを受け渡した後のステップは、メッセージの送信先を決定することです。 メッセージは多くの場合オーケストレーションに送信されますが、送信パイプラインに直接送信することもできます。こうすると、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] エンジンを純粋なメッセージング システムとして使用できます。 どちらの場合も、メッセージと送信先の照合には、サブスクリプションが使用されます。  
  
 受信パイプラインでメッセージが処理されると、メッセージのさまざまなプロパティを含むメッセージ コンテキストが作成されます。 オーケストレーションまたは送信パイプラインでは、これらのプロパティの値を基にメッセージをサブスクライブできます。 たとえば、オーケストレーションが「請求書」の種類のすべてのメッセージまたは QwickBank 社から受信した「請求書」の種類のすべてのメッセージまたは QwickBank 社から受信した「請求書」の種類のすべてのメッセージに一致するサブスクリプションを作成できます。$10,000 を超えることです。 ただし、これを指定すると、サブスクリプションのサブスクライバーにサブスクリプションを定義する条件を満たすメッセージのみを返します。 受信したメッセージによって、一部のオーケストレーションがインスタンス化されビジネス プロセスが開始される場合や、既に実行されているビジネス プロセスの別のステップがアクティブになる場合があります。 同様に、オーケストレーションからメッセージが送信されると、送信パイプラインのサブスクリプションを基に、送信されたメッセージと送信パイプラインが照合されます。  
  
-   [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] では、特定のエラー状態をサブスクライブすることもできます。 たとえば、エラー メッセージを特定の方法で処理したり、Windows SharePoint Services フォルダなどの特定の送信先にルーティングすることができます。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server メッセージング エンジン](../core/the-biztalk-server-messaging-engine.md)   
 [パブリッシュ/サブスクライブ アーキテクチャ](../core/publish-and-subscribe-architecture.md)   
 [アダプター](../core/adapters.md)   
 [パイプライン](../core/pipelines.md)