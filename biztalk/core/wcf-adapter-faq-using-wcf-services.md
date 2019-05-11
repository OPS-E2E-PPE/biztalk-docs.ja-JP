---
title: WCF アダプターに関する FAQ:WCF サービスの使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: befa2268-8a65-465f-8086-70a66808845e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65dc8427321d148430bcf3eb888c645ab4117937
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393586"
---
# <a name="wcf-adapter-faq-using-wcf-services"></a>WCF アダプターに関する FAQ:WCF サービスの使用
## <a name="how-does-biztalk-server-use-its-wcf-adapters-to-access-wcf-services"></a>BizTalk Server の使い方が WCF アダプター WCF サービスにアクセスするでしょうか。  
 BizTalk WCF アダプターが、WCF を通じて BizTalk Server で構成されている受信場所または送信ポート。 WCF アダプターを使用して受信場所を有効にすると、1 つの ServiceHost インスタンスがインスタンス化され、各受信場所用に初期化します。 ServiceHost は、受信 WCF メッセージを受け取るし、BizTalk メッセージ ボックス データベースに公開する前に BizTalk メッセージに変換する汎用サービスを実行します。 汎用的な ServiceHost サービスは WCF BizTalk の内部アダプターの実装を受け取り、型宣言不要なコントラクトを公開します。 WCF では、型宣言不要なコントラクトは WCF System.ServiceModel.Channel.Message 型の 1 つのパラメーターを使用する操作署名で構成されます。  
  
 WCF サービスの操作を IsOneWay としてマークする必要がありますが返すデータがない場合でも、BizTalk 送信ポートでアクセスする場合は、false を = です。 クライアント側コントラクトに対する操作は IsOneWay で注釈を付ける必要があります = false および ReplyAction ="*"。  さらに、クライアントからのすべての呼び出しは、IsOneWay でマークする必要があります ="false"。 双方向サービス操作には、メッセージ型の値を返す可能性があります。 MSMQ のキューにメッセージを投稿する一方向の操作を実行するため、この例外は、Wcf-netmsmq アダプターを使用しています。 ここで、送信ポートが一方向にすることができ、サービス操作が IsOneWay としてマークされている = true。  
  
 IsOneWay を定義する WCF では、また少し混乱を招く可能性がある = false OperationContract に実際に void を返すメソッド。 このような状況での WCF ランタイムによって作成されたネットワーク上で返される実際にメッセージが表示されます。  
  
 BizTalk WCF アダプターを使用するこの機能を使用します。 IsOneWay を持つ void メソッドを実際に取得する一方向の BizTalk ポートを指定すると、WCF アダプターの実装内で指定します。 BizTalk 一方向のポート、HTTP や net.tcp などの直接チャネルを使用する場合は、isOneWay を実際に対応している点は、= false OperationContract します。 Net.msmq などのキューに置かれたチャネルが異なる = true OperationContract の isOneWay との対話に一方向の BizTalk ポートは行われることにします。 WCF ディスパッチャーがチャネルに対してトランザクションを使用するためには、状況が異なります。  
  
## <a name="how-do-you-create-and-use-a-custom-binding-with-a-wcf-custom-adapter"></a>実行の作成方法と WCF カスタム アダプターを使用したカスタム バインドを使用しますか。  
 WCF CustomBinding は Bindingelement のコレクションで構成されます。 (たとえば、別のソースからの既存のエンコーダーを使用して既存のトランスポートを組み合わせること) の既存の Bindingelement を集めて、CustomBinding を作成できます。 または、既存の BindingElement と新規に作成されたカスタム BindingElement を組み合わせることで作成できます。 コード プログラムで追加することによって、CustomBinding を BindingElements のこれらのコンポーネントから構築できます。 WCF では、.NET 構成 (config ファイル) を使用して構築こともできます。 BizTalk Server を使用して、BizTalk WCF カスタム アダプターを介してこの CustomBinding を作成できます。  
  
 BizTalk WCF カスタム アダプターでは、Bindingelement から新しいバインドを作成するためだけでなく、直接新しいバインディングを構成することもできます。 標準バインドでの動作を構成することもできます。 カスタム動作の作成は、新しい BindingElement オブジェクトの作成より簡単なため、これは特に便利です。  
  
 BindingElement の構築は複雑な開発作業は、参照することの最適なソース ハイパーリンクで WCF サンプル "<http://go.microsoft.com/fwlink/?LinkId=142449>" \t "_blank" http://go.microsoft.com/fwlink/?LinkId=142449 します。 カスタム BindingElement を作成するには、BindingElement から派生するクラスを作成します。 新しい BindingElement は新しいアセンブリである必要があります。 このアセンブリをインストールする必要があります、管理用コンピューターで、BizTalk ホストの送信ポートと受信場所のグローバル アセンブリ キャッシュ (GAC) に構成されます。 カスタム バインドを関連付ける特定の送信ポートまたは受信場所は、まずに追加する、 \<bindingElementExtensions\>同じコンピューター上の machine.config ファイルのセクション。  
  
 開くことができますし、その変更を行った後、**トランスポートのプロパティの構成**バインディングを構成するダイアログ ボックス。  
  
1. **バインド**] タブの [バインドの種類、select **customBinding**します。  
  
2. **バインド**ウィンドウで、右クリック**CustomBindingElement**を選択し、**拡張機能の追加**します。  
  
3. Machine.config ファイルで指定したバインド要素を選択し、必要に応じて、バインディングを構成します。 場合によっては、メッセージの送信または受信に使用する準備ができました。  
  
   BizTalk ではカスタム バインドの検証を非常に限定された、この方法で追加されたとき。 したがって、バインド要素が正しい順序で表示されていることを確認する重要なは。 ダイアログ ボックスの CustomBindingElement バインド ツリーの下部にある実行時に最初に呼び出さ バインド要素があります。 Bindingelement の一覧は、トランスポートを含める必要があり、そのトランスポートは一覧の下部にある必要があります。 一連の Bindingelement にエンコーダーが含めることもできます。 詳細については、バインドの要素で、WCF ドキュメントを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=142449](http://go.microsoft.com/fwlink/?LinkId=142449)します。  
  
## <a name="what-is-a-wcf-custom-behavior-and-how-do-i-use-one-with-biztalk-server"></a>WCF カスタム動作と BizTalk Server のいずれかの使用方法について  
 メッセージ通信メカニズムとして WCF を使用する利点の 1 つは、カスタム コードを使用してそのサービスの機能を拡張することです。 カスタム動作拡張機能は、WCF の市場での他の Web サービス テクノロジから差別化機能の 1 つです。  
  
 インターセプトし、メッセージの最終的な送信先に到達する前に、カスタム処理を実行するには、WCF メッセージのフロー内のさまざまなポイントがあります。 WCF カスタム動作拡張機能は、このような 1 つの種類の傍受メカニズムでさまざまなレベルの粒度の WCF サービスまたはクライアント機能を拡張するために使用できます。 カスタム動作拡張機能は、WCF サービスとクライアント レベルの両方に存在できます。 WCF サービスへの呼び出し履歴で動作を構成しても、呼び出しに使用される通信バインドに影響がありません。 実際には、サービスが公開するメタデータに表示されないため、動作は通常、クライアントに表示されません。 通常、クライアントには、動作が WCF 操作の呼び出し中に実行するという考えがありません。  
  
 WCF サービスへの呼び出しでカスタム処理を簡単に実装する機能は、WCF がこのような機能豊富なプログラミング パラダイムと比較する他の Web アプリケーション間の通信方法の主な理由の 1 つです。 このカスタム処理で、Web アプリケーション内での拡張の要件に従い、ほぼすべての形式がかかる場合があります。 開発者は、検査、サービス構成を検証し、WCF クライアントとサービス アプリケーションのランタイム動作を変更またはカスタムの拡張機能を作成できます。 動作できます通常のメッセージの処理を補完、処理中にメッセージを変更、特定の構成条件を吟味したいと適切なアクションを実行、呼び出し元の id を検証および成功した場合など、メッセージを渡します。完全にカスタムために処理メカニズムがどのような機能拡張を実装するアプリケーションに必要があります。  
  
 BizTalk Server で WCF カスタム動作を使用する構成を使用して、**動作**受信場所または送信ポートの Wcf-custom または Wcf-customisolated アダプターのタブ。