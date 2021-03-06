---
title: WCF アダプターに関する FAQ:一般的な概念 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bbeac135-3ba8-4b0b-a8ca-4eb5eb3d3ca3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d3611a5e12cbbe52946630404c3ed6eb36f886c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393600"
---
# <a name="wcf-adapter-faq-general-conceptual"></a>WCF アダプターに関する FAQ:一般的な概念
以下はいくつかに関してよく寄せられる一般的なと概念に関する質問 Windows® Communication Foundation (WCF) アダプター。  
  
## <a name="what-is-a-wcf-adapter"></a>WCF アダプターとは何ですか。  
 BizTalk アダプターは、Microsoft® BizTalk® Server が外部と通信する方法の重要な部分です。 WCF アダプターは、BizTalk アプリケーションとメッセージを送信して、WCF エンドポイントからメッセージを受信する必要がある間の通信プロセスを管理するコンポーネントです。 BizTalk Server では、WCF アダプターは WCF バインドとして公開されます。 これは、WCF バインドを使用できる任意の WCF アプリケーションと通信できること、WCF アダプタを直接 BizTalk Server を介さずにしなくても意味します。 ただし、WCF アダプターを BizTalk Server を使用する BizTalk Server が提供するアプリケーションのインフラストラクチャのメリットが多数します。 これらの Faq のフォーカスは、BizTalk Server 環境から WCF アダプターを使用して主にします。  
  
 WCF アダプターでは、WCF メッセージの送受信に WCF バインドを使用する BizTalk Server によりできます。 WCF クライアント アプリケーション アダプターを受信する送信 WCF メッセージを BizTalk 受信場所、WCF によって、メッセージを受信します。 アダプターは WCF メッセージを取得し、BizTalk メッセージに変換します。 変換が行われると、BizTalk Server 管理コンソールを使用して構成されている特定のアダプター構成の設定に依存します。 アダプターでは、内部の BizTalk メッセージ ボックス データベースを BizTalk メッセージを送信します。 同様に、BizTalk は、ポートには、WCF アダプターできますメッセージの種類へのサブスクライブ、BizTalk メッセージを取得、WCF メッセージに変換およびサポートされている WCF プロトコルのいずれかを使用して WCF サービス エンドポイントに WCF メッセージの送信を使用して送信します。  
  
 BizTalk Server 内から WCF アダプターを使用するには、非表示選択との通信プロトコル、セキュリティの問題、およびトランザクション操作の実装など、BizTalk WCF アプリケーション ソリューションの複雑さが抽象化します。  
  
## <a name="what-are-the-wcf-adapter-bindings"></a>WCF アダプター バインドとは  
 WCF バインドは、2 つのカテゴリのいずれかに分類されます。  
  
- **カスタム バインド:** バインドの柔軟性を向上させますは、特別なカスタム バインドが存在します。 これには、標準バインディングからの逸脱を必要とする通信状況について説明します。 Wcf-custom および Wcf-customisolated アダプターでは、広範なバインドのカスタマイズの開発を許可します。 これは、既存のバインド要素 (BindingElement クラス) の構成と動作 (Behavior クラス) のアプリケーションを許可することで行います。  
  
- **標準バインド:** マイクロソフトの目標、最も一般的な通信シナリオに焦点を当てたアダプターを開発することです。 標準バインディングを使用すると、通信プロトコルの多くの詳細を非表示にして、開発者のエクスペリエンスが簡略化します。 BizTalk Server の WCF アダプターのセットには、.NET Framework 4.0 WCF ライブラリで使用可能なバインドのセットが反映されます。 標準バインドは、一般的なバインドのパターンを使いやすくするために、.NET WCF ライブラリについて紹介しました。 最もよく使用される通信シナリオに対応が含まれます。  
  
  -   Wcf-wshttp  
  
  -   WCF-BasicHttp  
  
  -   WCF-NetTcp  
  
  -   WCF-NetMsmg  
  
  -   WCF-NetNamedPipe  
  
  BizTalk Server R2 では、次の WCF アダプターが付属しています。  
  
1.  **Wcf-wshttp アダプター:** Ws-* 標準 HTTP トランスポート経由でサポートされています。 Wcf-wshttp アダプタは、次の仕様を実装します。WS トランザクションの外部アプリケーションとメッセージ ボックス データベースでは、Ws-security とは、メッセージ セキュリティと認証のトランザクション対話を処理します。 トランスポートは HTTP または HTTPS、およびメッセージのエンコードは、テキストまたは Message Transmission Optimization Mechanism (MTOM) エンコードします。  
  
2.  **Wcf-basichttp アダプター:** ASMX ベースの Web サービスとクライアント、および、WS に準拠するその他のサービスと通信の基本プロファイル 1.1。 トランスポートは HTTP または HTTPS、およびメッセージのエンコードは text エンコードです。  
  
3.  **Wcf-nettcp アダプター:** Ws-* 標準 TCP トランスポート経由でサポートされています。 Wcf-nettcp アダプターは、効率的な通信を提供し、仕様を実装します。WS トランザクションの外部アプリケーションとメッセージ ボックス データベースでは、Ws-security とは、メッセージ セキュリティと認証のトランザクション対話を処理します。 トランスポートは TCP、およびメッセージのエンコードはバイナリ エンコードです。  
  
4.  **Wcf-netmsmq アダプター:** メッセージ キュー (MSMQ とも呼ばれます) を使用するトランスポートとして使用したキューのサポートを提供し、疎結合アプリケーション、エラーの分離、負荷平準化、および切断操作のサポートを有効にします。  
  
5.  **Wcf-netnamedpipe アダプター:** セキュリティで保護されたコンピューター上のプロセス間通信の最適化を提供します。 Wcf-netnamedpipe アダプタは、メッセージの配信、およびバイナリ メッセージ エンコーディングの名前付きパイプ、転送セキュリティ用トランスポート セキュリティを使用します。  
  
     先ほど説明した 5 つのアダプタのそれぞれは、1 対 1 リレーションシップでの WCF バインドを 1 つに対応します。 2 つのカスタム アダプターの構造からは少し外れます、WCF モデルが実際には 2 つのカスタム アダプター 1 つの WCF CustomBinding に対応します。  
  
6.  **Wcf-custom アダプター:** WCF の拡張機能を使用できるようにします。 アダプターを選択し、WCF バインドと受信場所または送信ポートが BizTalk Server プロセスでホストされている動作情報を構成することができます。  
  
7.  **Wcf-customisolated アダプター:** HTTP トランスポート経由で WCF 拡張機能を使用できるようにします。 アダプターを選択し、WCF バインドと分離ホストのインターネット インフォメーション サービス (IIS) で実行されている受信場所の動作情報を構成することができます。  
  
## <a name="what-is-the-difference-between-the-wcf-xxx-adapter-and-the-wcf-xxx-binding"></a>Wcf-xxx アダプターと wcf-xxx バインドの違いは何ですか。  
 各 WCF アダプターは、組み込みの WCF バインドのいずれかに対応しています。 上位のレベルで、これらの用語は wcf-xxx アダプターは wcf-xxx バインドを使用しているという場合にほぼ同じ意味で使用されます。 たとえば、Wcf-basichttp アダプターは WCF BasicHttpBinding クラスを使用します。 WCF バインドは、WCF エンドポイントの定義の一部です。 これは参照されます"abc"、WCF エンドポイントのアドレス、バインディングおよびコントラクトのこれらの文字がスタンド アロンします。  
  
 バインディングは、バインド要素のコレクションで構成をされます。 各要素には、エンドポイントがクライアントと通信する方法の一部の側面について説明します。 バインドを含める必要があります。  
  
- 少なくとも 1 つのトランスポート バインド要素。  
  
- 少なくとも 1 つメッセージ エンコーディング バインド要素 (トランスポート バインド要素は、既定で提供できます)。  
  
- その他のプロトコル バインド要素の任意の数。  
  
  この記述からランタイム環境を構築するプロセスは、その環境にコードを投稿するには、各バインド要素を使用します。 通常はクライアントが同じバインドの種類と呼び出し先の WCF サービスをサポートするアダプターと一致するために必要になります。 WCF レベルでは、バインドを定義できます宣言によって構成ファイルで、またはコードによって明示的にします。 WCF アダプターを特定の WCF バインドを使用して通信を容易にして、用語「アダプター」と「バインド」がほぼ同じ意味で使用する傾向がそのため。  
  
## <a name="when-using-the-wcf-adapters-how-do-you-decide-which-wcf-binding-to-use"></a>WCF アダプタを使用する場合を決める方法を使用する WCF バインドしますか。  
 メッセージング パターン、外部の制約、およびその順序でのパフォーマンスに基づいてこの決定を行うことができます。  
  
1.  **メッセージング パターン:** 通信のパターンは、通信のメッセージのフローに基づく処理方法です。 たとえば、メッセージ可能性があります (要求) または双方向 (要求-応答)、そのトランザクションが行われる可能性があります、キューします。  
  
    -   キューに配置する場合は、キューに登録されたトランザクションの一方向通信をサポートする Wcf-netmsmq アダプターを使用する必要があります。  
  
    -   パターンが双方向の要求-応答と 2 台のコンピューター間のフローの場合、(パフォーマンスを懸念がある) 場合、HTTP (懸念される限り柔軟な場合) または Wcf-nettcp を使用します。  
  
    -   メッセージは、1 台のコンピューターに残りますが、単にプロセス間のフローする場合、は、Wcf-netnamedpipe バインドを使用できます。  
  
2.  **外部の制約:** 特定のバインディングを使用するよう指示する問題である可能性があります。 たとえば、外部システムは、Web サービスの SOAP バージョン 1.2 とアドレス指定 1.0 が必要です。 この場合、バインドが最適です WSHttpBinding、Wcf-wshttp アダプターを使用します。 多くの場合、外部システムは、特定のセキュリティ モードを構成する要件もがあります。 外部システムには、Soap Web サービス 1.1 が必要な場合は、HTTP バインディングの Wcf-basichttp アダプタを使用します。  
  
3.  **パフォーマンス:** 速度、呼び出しが行われるバインドの使用を選択する、アプリケーションでの決定要因があります。  
  
    -   WCF サービスが BizTalk Server と同じコンピューター上にある場合は、最適のパフォーマンスは、Wcf-netnamedpipe アダプタを使用します。  
  
    -   WCF サービスが、ローカル ネットワーク上にある場合は、Wcf-nettcp には、最適なパフォーマンスが得られます。  
  
    -   パフォーマンスが大きな問題ではない場合、呼び出しが、HTTP ベース アダプターのいずれかと、インターネット経由で、(Wcf-wshttp または Wcf-basichttp) は、適切なアダプター。  
  
         HTTP ベース アダプターの種類が、高度な HTTP 機能 (Wcf-wshttp) を使用しているか (Wcf-basichttp) の基本的な機能が決まるかどうかを使用する最適な選択肢になります。  
  
## <a name="when-do-you-use-one-of-the-two-custom-wcf-adapters"></a>使用するは 2 つのカスタム WCF アダプターのいずれかですか。  
 BizTalk Server に付属する 2 つのカスタム WCF アダプターがあります。 2 つのカスタム アダプターは BizTalk Server では、特定のアダプターの種類のホストは、システムとその登録の一部である必要がある必要があるためにがある理由です。 2 つのカスタム アダプターが、WCF フレームワークのバインドの種類を 1 つだけですが、既存の BizTalk アダプターのモデルでのこの制限に対応するために BizTalk Server であります。 実際には、使用するこれらのアダプターとは、実際にアダプターのみが必要になった WCF チャネル スタックの構成を完全に制御できるためです。  
  
 カスタム アダプターへの唯一の欠点は、こともが必要になる WCF 構成とさまざまな機能拡張技法に関する詳しい知識がユーザーです。  Microsoft 標準の WCF バインドのアダプターを提供するため、効率化の構成。 標準のバインディングは、一般的なユース ケースのほとんどに対応し、できるだけ簡単に BizTalk Server を経由してメッセージを送受信することを定義済みです。 通常、これらのカスタム アダプターのいずれかを使用する必要は、標準バインディングまたは完全に正確には、送信ポートの要件を満たすまたは受信場所に失敗する場合にのみ発生します。 たとえば、そのメッセージに独自の圧縮スキームを使用して、アプリケーションがあります。 これをサポートするには、カスタム バインド要素が書き込まれる必要があります。 2 つの標準カスタム アダプターのいずれかを使用すると、転送要求を処理するカスタム バインドの構成ができます。 そのため、カスタム アダプターにより、高いレベルのチャネル スタックを通じてその通信プロセスのバインドの構成を制御します。  
  
 カスタム プロパティとカスタム分離アダプターの主な違いは、ホストの 1 つと、BizTalk Server の受信側にのみ影響をホストしています。 のみ、受信場所および送信ポートではなく、Wcf-customisolated アダプターが使用されます。 「分離」という用語を参照すると、BizTalk Server の BtsNtSvc.exe プロセスの外部でホストされている BizTalk フレーズです。 そのため、Wcf-customisolated アダプターは、トランスポートが標準の BtsNtSvc.exe プロセス内でインターネット インフォメーション サービス (IIS)、HTTP トランスポートを使用して外部ホストされている場合に使用されます。 Wcf-custom アダプターは、受信場所または送信ポートのいずれかで使用できます。 トランスポートが標準の BtsNtSvc.exe プロセス内でホストされている場合に使用されます。  
  
## <a name="how-does-a-wcf-endpoint-relate-to-biztalk-server"></a>BizTalk Server には、WCF エンドポイントはどのように関連しますか。  
 WCF エンドポイントは、アドレス、バインディング、およびコントラクト (ABC) で構成されます。 BizTalk Server 内で、ユーザーは、受信場所のアドレスを指定または送信ポート。 バインディングは、ユーザーが選択した WCF アダプターによって指定されます。 コントラクトは、プログラマーが決定ことで、エンドポイントによって公開されるインターフェイスを指定します。  
  
 メッセージを送信する wcf 受信場所として、実際のエンドポイントが存在します。  BizTalk Server アプリケーションで WCF エンドポイントを公開する複数の方法はあります。  
  
- BizTalk WCF サービス公開ウィザードを使用すると、BizTalk オーケストレーションを WCF エンドポイントとして公開します。  
  
- BizTalk WCF サービス公開ウィザードを使用して、既存の BizTalk アプリケーションで受信場所を作成することができます。  
  
- コードで受信場所のバインドとアドレスを構成することで、WCF エンドポイントを手動で作成することができます。  この場合、受信場所は、実際に指定されていないかではありません。  メッセージ ボックス データベースに任意の形式のメッセージを受信することができます、WCF メッセージ クラスの純粋な観点から指定されたコントラクトがあります。  
  
  各 BizTalk 受信場所を WCF を使用するアダプターは WCF クライアントが呼び出しを行うことができます、WCF エンドポイントとして公開されます。  受信場所は、有効になっているまたはそれぞれ個別に無効にする別の受信場所を許可するのに独自の WCF ServiceHost を内部的に使用します。 サービス エンドポイントの有効期間に限り、その受信場所が存在するが有効になっています。 この有効期間の問題により、WCF ServiceHosts がポートを受信するのではなく、受信場所に対応しています。 WCF の設計により、個々 の Servicehost はランタイムのリソースの観点から安価同じ問題なく実行可能ファイル内で実行できる多くなります。  
  
  WCF アダプタを使用する各 BizTalk 送信ポートは、WCF サービスに対して行われた呼び出しに対応します。 送信するメッセージが存在する場合、BizTalk Server では、アダプター対応するメッセージに BizTalk WCF アダプター内で WCF クライアント プロキシの作成。 メッセージを送信した後、WCF クライアント プロキシは解放されます。 送信ポートで WCF の有効期間は常にはし、プロキシの作成、使用、および破棄が通過します。