---
title: 'WCF アダプターに関する FAQ: WCF サービスの使用 |Microsoft Docs'
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
ms.openlocfilehash: f3dc7ae44fa6ef6722c0887f2c70a83f43d1bf5c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970051"
---
# <a name="wcf-adapter-faq-using-wcf-services"></a>WCF アダプターに関する FAQ: WCF サービスの使用
## <a name="how-does-biztalk-server-use-its-wcf-adapters-to-access-wcf-services"></a>BizTalk Server が WCF アダプターを使用して WCF サービスにアクセスするしくみ  
 BizTalk WCF アダプターは、WCF 受信場所または送信ポートを通じて BizTalk Server で構成されます。 WCF アダプターを使用する受信場所が有効になっている場合、各受信場所に対して 1 つの ServiceHost インスタンスがインスタンス化および初期化されます。 ServiceHost は受信 WCF メッセージを受け取る汎用サービスを実行し、受信 WCF メッセージを BizTalk メッセージに変換してから BizTalk メッセージ ボックス データベースサービスに公開します。 汎用的な ServiceHost サービスは WCF BizTalk 受信アダプター実装内部のサービスであり、型宣言が不要なコントラクトを公開します。 WCF では、型宣言不要なコントラクトは WCF System.ServiceModel.Channel.Message 型の 1 つのパラメーターを使用する操作署名で構成されます。  
  
 返されるデータがなくても、BizTalk 送信ポートからアクセスする場合は、WCF サービスの操作を IsOneWay=false としてマークする必要があります。 クライアント側コントラクトに対する操作には、IsOneWay=false および ReplyAction="*" で注釈を付ける必要があります。  また、クライアントからの呼び出しはすべて IsOneWay="false" でマークする必要があります。 双方向のサービス操作はメッセージ型の値を返す場合があります。 ただし、WCF-NetMsmq アダプターを使用する場合は例外です。これは、WCF-NetMsmq アダプターはメッセージを MSMQ キューに送信する一方向の操作を実行するためです。 この場合、送信ポートは一方向になり、サービス操作は IsOneWay=true としてマークされます。  
  
 WCF では実際に void を返すメソッドで isOneWay=false OperationContract も定義できることから、混乱が生じる可能性があります。 このような場合、実際には、WCF ランタイムによって作成されたメッセージが有線ネットワークで返されます。  
  
 BizTalk WCF アダプターはこの機能を利用します。 一方向の BizTalk ポートを指定すると、実際には WCF アダプターの実装内で isOneWay=false の void メソッドを受け取ります。 重要なのは、HTTP や net.tcp などの直接チャネルを使用する場合、一方向の BizTalk ポートは実際には isOneWay=false OperationContract に対応することです。 net.msmq などのキューに登録済みのチャネルでは、一方向の BizTalk ポートが isOneWay=true OperationContract と通信することがあるという点が異なります。 これは、WCF ディスパッチャーがチャネルに対してトランザクションを使用しているためです。  
  
## <a name="how-do-you-create-and-use-a-custom-binding-with-a-wcf-custom-adapter"></a>WCF カスタム アダプターを使用してカスタム バインドを作成および使用する方法  
 WCF CustomBinding は BindingElement のコレクションで構成されています。 CustomBinding を作成するには、既存の BindingElement をまとめます (たとえば、既存のトランスポートと別のソースの既存のエンコーダーを組み合わせます)。 既存の BindingElement と新規に作成されたカスタム BindingElement を組み合わせて作成することもできます。 コードでは、プログラムによって BindingElement を追加することで、これらのコンポーネントから CustomBinding を作成できます。 WCF では .NET 構成 (config ファイル) を使用して構築することもできます。 BizTalk Server を使用することで、BizTalk WCF カスタム アダプターでこの CustomBinding を作成できます。  
  
 BizTalk WCF カスタム アダプターでは、BindingElement から新しいバインドを作成できるだけでなく、新しいバインドを直接構成することもできます。 また、標準バインド上の動作を構成することもできます。 カスタム動作の作成は、新しい BindingElement オブジェクトの作成より簡単なため、これは特に便利です。  
  
 BindingElement の構築は複雑な開発作業は、参照することの最適なソース ハイパーリンクで WCF サンプル"<http://go.microsoft.com/fwlink/?LinkId=142449>"\t"_blank"http://go.microsoft.com/fwlink/?LinkId=142449します。 カスタム BindingElement を作成するには、BindingElement から派生するクラスを作成します。 新しい BindingElement は新しいアセンブリに含める必要があります。 このアセンブリは、BizTalk ホスト、送信ポート、および受信場所が構成される管理コンピューターのグローバル アセンブリ キャッシュ (GAC) にあらかじめインストールされている必要があります。 カスタム バインドを関連付ける特定の送信ポートまたは受信場所は、まずに追加する、 \<bindingElementExtensions\>同じコンピューター上の machine.config ファイルのセクション。  
  
 開くことができますし、その変更を行った後、**トランスポートのプロパティの構成**バインディングを構成するダイアログ ボックス。  
  
1. **バインド**] タブの [バインドの種類、select **customBinding**します。  
  
2. **バインド**ウィンドウで、右クリック**CustomBindingElement**を選択し、**拡張機能の追加**します。  
  
3. machine.config ファイルで指定したバインド要素を選択し、必要に応じてバインドを構成します。 これで、メッセージの送信または受信に使用する準備ができました。  
  
   この方法でカスタム バインドが追加された場合、BizTalk で行われる検証は非常に限られたものです。 このため、バインド要素が正しい順序で表示されるようにすることが重要です。 実行時に初めて呼び出すバインド要素は、ダイアログ ボックスの CustomBindingElement バインド ツリーの下部に配置する必要があります。 BindingElement の一覧にはトランスポートが含まれている必要があります。トランスポートは一覧の下部に配置する必要があります。 一連の BindingElement にエンコーダーが含まれる場合もあります。 詳細については、バインドの要素で、WCF ドキュメントを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=142449](http://go.microsoft.com/fwlink/?LinkId=142449)します。  
  
## <a name="what-is-a-wcf-custom-behavior-and-how-do-i-use-one-with-biztalk-server"></a>WCF カスタム動作についての説明と WCF カスタム動作の BizTalk Server における使用方法  
 WCF をメッセージ通信メカニズムとして使用する利点の 1 つは、カスタム コードを使用することでサービスの機能を拡張できる点です。 カスタム動作拡張機能は、市場の他の Web サービス テクノロジにはない、WCF の機能の 1 つです。  
  
 WCF メッセージのフロー内には、メッセージが最終送信先に到達する前にカスタム処理を傍受および実行する別のポイントもあります。 WCF カスタム動作拡張機能はこのような種類の傍受メカニズムの 1 つであり、細分化されたさまざまなレベルで WCF サービスまたはクライアント機能を拡張するために使用できます。 カスタム動作拡張機能は、WCF サービス レベルとクライアント レベルの両方で設定できます。 WCF サービスへのコール スタックで動作を構成しても、呼び出しに使用される通信バインドには影響しません。 実際には、動作はサービスが公開するメタデータ内に表示されないため、通常はクライアントに対しては表示されません。 通常、WCF 操作の呼び出し中に動作が実行されていることは、クライアントにはわかりません。  
  
 WCF サービスの呼び出しでカスタム処理を簡単に実装する機能は、Web アプリケーション間の他の通信方法と比較して、WCF が機能豊富なプログラミング パラダイムである主な理由の 1 つです。 このカスタム処理は、Web アプリケーション内の拡張機能要件で必要とされる、ほぼすべての形式に対応できます。 開発者は、サービス構成を調査および検証したり、WCF クライアント アプリケーションおよびサービス アプリケーションの実行時の動作を変更したりするカスタム拡張機能を作成できます。 動作では、通常のメッセージ処理を補完する、処理中にメッセージを変更する、特定の構成条件を精査して適切なアクションを実行する、呼び出し側の ID を確認して問題がなければメッセージを渡す、などを実行できます。これは完全にカスタム処理メカニズムであるため、アプリケーションに必要であればどのような拡張でも実装できます。  
  
 BizTalk Server で WCF カスタム動作を使用する構成を使用して、**動作**受信場所または送信ポートの Wcf-custom または Wcf-customisolated アダプターのタブ。