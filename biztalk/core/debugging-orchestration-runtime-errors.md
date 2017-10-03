---
title: "オーケストレーションの実行時エラーのデバッグ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7be9ee5a-b9fa-428b-8b92-0fa0f801c724
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36e881f8449e7aaac7aeade12c36c3c6d942ef12
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="debugging-orchestration-runtime-errors"></a>オーケストレーションの実行時エラーのデバッグ
このセクションでは、オーケストレーションに関する実行時の問題の解決に役立つ一連の質問と回答を示します。  
  
## <a name="why-do-i-get-intermittent-subscription-errors-when-sending-to-a-child-orchestration-that-was-just-started-by-the-parent"></a>親によって開始された直後の子オーケストレーションに送信を行うと、断続的なサブスクリプション エラーが発生するのはなぜでしょうか。  
 サブスクリプションが見つかりませんでした、というサブスクリプション エラーは、競合状態の結果です。 競合状態は、プロセスの結果が実行順序によって変わる場合に発生します。 この場合、競合状態が発生するのは、親によって送信されたメッセージを受信する時点で、まだ子オーケストレーションが開始されていないときです。  
  
 この問題を回避するには、子オーケストレーションが開始されてメッセージを受信できる状態になったときに、子オーケストレーションから親にメッセージを返すようにします。 この方法にすれば、子オーケストレーションを開始した親オーケストレーションが、メッセージを送信する前に受信者の存在を認識できます。  
  
## <a name="why-do-i-get-errors-when-i-attach-a-dynamic-send-port-to-a-logical-port"></a>動的送信ポートを論理ポートに接続すると、エラーが発生するのはなぜでしょうか。  
 動的ポートは、割り当てるポートの属性と特性のすべてを継承するようには設計されていません。 動的ポートは、アドレスを取得するだけであり、論理ポートに関連付けられているその他の情報は継承しません。  
  
 たとえば、"配信通知 = 送信済み" 状態の論理ポートに動的送信ポートを接続した場合、ランタイムは配信通知を配信しません。 XLANGs ランタイムが配信通知を待機するのは、実際にポートがそのように静的に設定されている場合のみです。  
  
> [!NOTE]
>  XLANGs では、ポートは静的に構成されているものとしてのみ動作します。  
  
## <a name="when-i-try-to-run-my-application-after-deploying-an-orchestration-with-custom-components-why-do-i-get-the-error-file-or-assembly-name-or-one-of-its-dependencies-not-found"></a>カスタム コンポーネントを含むオーケストレーションの展開後にアプリケーションを実行しようとすると、ファイルまたはアセンブリ名、あるいはその依存関係の 1 つが見つかりません、というエラーが発生するのはなぜでしょうか。  
 このエラーは、通常、BizTalk オーケストレーション エンジンがカスタム コンポーネントを見つけられないことを示しています。 アプリケーションをホストするコンピューターのグローバル アセンブリ キャッシュに、BizTalk アプリケーションに含まれているすべてのアセンブリをインストールする必要があります。  
  
## <a name="an-assemblyname-context-property-was-not-valid-error-occurs-when-submitting-a-document-to-a-web-service-via-an-orchestration"></a>オーケストレーション経由で Web サービスにドキュメントを送信する際に、AssemblyName コンテキスト プロパティが無効でした、というエラーが発生します。  
  
### <a name="problem"></a>問題  
 オーケストレーション経由でドキュメントを Web サービスに送信すると、AssemblyName コンテキスト プロパティが無効です、というエラーが発生します。  
  
### <a name="cause"></a>原因  
 BizTalk アプリケーションでは、介在するオーケストレーションなし「メッセージング」アプローチを使用してもともとです。 このようなソリューションでは、送信ポート フィルターを使用して受信ポートと送信ポートをリンクするので、ドキュメントは受信時に送信ポートに渡されます。 その後、ソリューションは、送信ポートにバインドされているオーケストレーションを含むように変更されました。  
  
### <a name="resolution"></a>解決策  
 送信ポートのフィルターを削除します。 オーケストレーションにバインドされている送信ポートにフィルターを適用すると、多くの場合、メッセージがオーケストレーションをバイパスするので、コンテキスト プロパティ エラーが発生します。  
  
## <a name="a-wrongbodypartexception-occurs-when-handling-a-multipart-mime-message-in-an-orchestration"></a>オーケストレーションでマルチパート MIME メッセージを処理する際に、"WrongBodyPartException" が発生します。  
  
### <a name="problem"></a>問題  
 結果をオーケストレーションにマルチパート MIME メッセージの受信、 **WrongBodyPartException**例外。  
  
### <a name="cause"></a>原因  
 このエラーは、部分の順序が誤って指定された場合、または指定された部分の位置にメッセージが準拠していない場合に発生します。 たとえば、3 番目の部分にボディ部を指定している場合に、到着したメッセージの 3 番目の位置がヘッダー部であるときなどです。  
  
### <a name="resolution"></a>解決策  
 ボディ部のインデックス設定が正しいことを確認し、アダプター経由で到着するすべてのメッセージがその設定と一致するようにします。 オーケストレーションを停止することで (ただし参加は継続)、オーケストレーション内で失敗する MIME メッセージのコンテンツを調査できます。この方法では、メッセージが強制的に公開されるので、管理コンソールを使用してメッセージを調べて、部分の順序を確認することができます。  
  
## <a name="multipart-mime-message-part-cannot-be-found"></a>マルチパート MIME メッセージ部分が見つかりません。  
  
### <a name="problem"></a>問題  
 MIME を取得したメッセージのようなエラーをスロー、BizTalk Server ランタイムで結果が 0 より大きいインデックス値を持つ部分"のインデックスでのマルチパート メッセージを見つけることができません =\<値 >"です。  
  
### <a name="cause"></a>原因  
 このエラーの最も一般的な原因を次に示します。  
  
-   MIME メッセージの部分が想定された数に足りません。  
  
-   MIME メッセージが正常に解析できませんでした。  
  
### <a name="resolution"></a>解決策  
 この問題は、メッセージ ソースから取得するメッセージ部分が、想定される範囲内の部分のみになるようにすることで解決できます。 解析の問題の場合、元の MIME メッセージの構造に誤りがなく、正しく構築されているか確認する必要があります。 不定期に解析の問題が起こる場合、オーケストレーションに適切な例外ハンドラーがあるか確認します。  
  
## <a name="you-receive-a-the-file-send-adapter-cannot-open-file-for-writing-error-when-sending-using-a-dynamic-send-port"></a>動的送信ポートを使用して送信を行うと、"FILE 送信アダプターがファイルを書き込み用に開けません" というエラーが表示されます。  
  
### <a name="problem"></a>問題  
 表示されたら、"ファイル送信アダプターがファイルを開くことができません*\<ファイル名 >*書き込み用"動的なを使用して送信するときに、BizTalk Server のイベント ログにエラーが送信ポート。  
  
 この問題が発生したときに、 **BTS です。OutBoundTransportLocation**プロパティがオーケストレーションの式で定義されていると、ファイル トランスポートを指定すると、たとえば、次の式では実行時にこのエラーが発生します。  
  
```  
Message2=Message1;  
Message2(BTS.OutboundTransportLocation) = "file:///c:/test/out";  
MySendPort(Microsoft.XLANGs.BaseTypes.Address)=Message2(BTS.OutboundTransportLocation);  
```  
  
 \-または、  
  
```  
Message2=Message1;  
Message2(BTS.OutboundTransportLocation) = "file://mymachine/test/out";  
MySendPort(Microsoft.XLANGs.BaseTypes.Address)=Message2(BTS.OutboundTransportLocation);  
```  
  
### <a name="cause"></a>原因  
 この問題は、オーケストレーション エンジンは実行時にテキストを削除すると、"**file://"**指定した URL からです。 したがって、先ほどの例では、"file:///c:/test/out" は \c:\test\out と評価され、"file://mymachine/test/out" は mymachine\test\out と評価されます。  
  
### <a name="resolution"></a>解決策  
 URL を指定する場合、 **BTS です。OutBoundTransportLocation**を式でプロパティを追加または削除「/」文字がします。 上記の例を使用して、 **BTS です。OutBoundTransportLocation**プロパティを"file://c:/test/out がまたはに評価される c:\test\out"file:///mymachine/test/out"\\mymachine\test\out として定義すべき\\\mymachine\test\out です。