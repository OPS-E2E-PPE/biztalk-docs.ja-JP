---
title: オーケストレーションの実行時エラーのデバッグ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7be9ee5a-b9fa-428b-8b92-0fa0f801c724
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b74291083afc5c25df0723bcbdf105ba51016a1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389762"
---
# <a name="debugging-orchestration-runtime-errors"></a>オーケストレーションの実行時エラーのデバッグ
このセクションには、一連質問と回答では、オーケストレーションの実行時の問題を解決するために設計されていますにはが含まれています。  
  
## <a name="why-do-i-get-intermittent-subscription-errors-when-sending-to-a-child-orchestration-that-was-just-started-by-the-parent"></a>親によって開始された直後の子オーケストレーションに送信するときに断続的なサブスクリプション エラーするはなぜですか。  
 サブスクリプション エラー「が見つかりませんでしたサブスクリプション」は、競合状態の結果です。 競合状態は、プロセスの結果は、処理が行われる特定の順序に依存する場合に発生します。 この場合、条件は、親によって送信されたメッセージを受信する時点で、子オーケストレーションが開始されていないときに発生します。  
  
 この問題を回避するには、ことが起動し、メッセージを受信する準備がとき、子オーケストレーションはでした、親に戻るメッセージを送信します。 この方法でを起動した親オーケストレーションにメッセージを送信する前に、受信側があることは認識。  
  
## <a name="why-do-i-get-errors-when-i-attach-a-dynamic-send-port-to-a-logical-port"></a>論理ポートを動的送信ポートを接続したときにエラーするはなぜですか。  
 動的なポートは、すべての属性とそれに割り当てられているポートの特性を継承するように設計されていません。 動的なポートのみで、アドレスを取得します。論理ポートに関連付けられたその他の情報は継承されません。  
  
 たとえば、配信通知の論理ポートに動的送信ポートを接続する場合は、= 送信済み、ランタイムは配信通知を配信しません。 XLANGs ランタイムはのみに、ポートが実際に設定されているように静的にする場合、配信通知をリッスンします。  
  
> [!NOTE]
>  XLANGs では、ポートは静的に構成されている場合にのみ動作します。  
  
## <a name="when-i-try-to-run-my-application-after-deploying-an-orchestration-with-custom-components-why-do-i-get-the-error-file-or-assembly-name-or-one-of-its-dependencies-not-found"></a>カスタム コンポーネントを使用したオーケストレーションを展開した後にアプリケーションを実行しようとするとなぜ、エラー「ファイルまたはアセンブリの名前またはその依存関係が見つかりません。 いずれかの」でしょうか。  
 このエラーは通常、BizTalk オーケストレーション エンジンは、カスタム コンポーネントを見つけることはできませんを意味します。 アプリケーションをホストするコンピューターのグローバル アセンブリ キャッシュ内の BizTalk アプリケーションに含まれるすべてのアセンブリをインストールする必要があります。  
  
## <a name="an-assemblyname-context-property-was-not-valid-error-occurs-when-submitting-a-document-to-a-web-service-via-an-orchestration"></a>オーケストレーション経由で Web サービスへのドキュメントを送信するときに、「AssemblyName コンテキスト プロパティが無効です」エラーが発生しました。  
  
### <a name="problem"></a>問題  
 「AssemblyName コンテキスト プロパティが無効です」エラーで、オーケストレーションの結果を使用して Web サービスへのドキュメントを送信しています。  
  
### <a name="cause"></a>原因  
 BizTalk アプリケーションは、介在するオーケストレーションなし「メッセージング」アプローチを使用してもともと設計されました。 この種のソリューションは、送信ポート フィルターを使用して、受信ポートと送信ポートをリンクして、ドキュメントを受信すると、送信ポートに渡されます。 後で、ソリューションは、送信ポートにバインドされたオーケストレーションを含むに変更されました。  
  
### <a name="resolution"></a>解決策  
 送信ポートでフィルターを削除します。 オーケストレーションにバインドされている送信ポートにフィルターを適用する場合メッセージは多くの場合、オーケストレーションをバイパス コンテキスト プロパティのエラーが発生します。  
  
## <a name="a-wrongbodypartexception-occurs-when-handling-a-multipart-mime-message-in-an-orchestration"></a>"WrongBodyPartException"は、オーケストレーションでマルチパート MIME メッセージを処理するときに発生します。  
  
### <a name="problem"></a>問題  
 結果をオーケストレーションにマルチパート MIME メッセージの受信、 **WrongBodyPartException**例外。  
  
### <a name="cause"></a>原因  
 このエラーは、要素の順序が正しく指定されていない、またはメッセージ部分の指定した位置に準拠していない場合に発生することができます。 などのことを指定する場合は、3 番目の部分がボディ部がメッセージを受け取るまでに 3 番目の位置でのヘッダー部分。  
  
### <a name="resolution"></a>解決策  
 ボディ部のインデックス設定が正しいことを確認して、し、アダプター経由で到着するすべてのメッセージが整合性の設定があることを確認してください。 オーケストレーションを停止することで、オーケストレーション内で失敗する MIME メッセージの内容を検査することができます (ただし、参加を維持する)。これで、メッセージが公開されるので、管理コンソールを使用してチェックし、要素の順序を確認できます。  
  
## <a name="multipart-mime-message-part-cannot-be-found"></a>マルチパート MIME メッセージ部分が見つかりません  
  
### <a name="problem"></a>問題  
 メッセージのようなエラーをスローする BizTalk Server ランタイムに結果が 0 より大きいインデックス値を持つパーツの MIME を取得すると"インデックスを持つ、マルチパート メッセージを見つけることができません =\<値\>"。  
  
### <a name="cause"></a>原因  
 このエラーの最も一般的な原因は次のとおりです。  
  
-   MIME メッセージは、予想よりも少ない部分です。  
  
-   MIME メッセージを完全に解析できませんでした。  
  
### <a name="resolution"></a>解決策  
 コードは、メッセージ ソースから予想される範囲内にあるメッセージ部分のみを取得することによってこの問題を解決することができます。 解析の問題の場合は、元の MIME メッセージは、構造的なサウンドと適切に構築されたことを確認してください。 不定期の解析の問題を想定する場合は、オーケストレーションが適切な例外ハンドラーを持つことを確認します。  
  
## <a name="you-receive-a-the-file-send-adapter-cannot-open-file-for-writing-error-when-sending-using-a-dynamic-send-port"></a>送信ポートの動的なを使用して送信する場合に"ファイル送信アダプターはファイルを書き込み用に開けません"というエラーが発生します。  
  
### <a name="problem"></a>問題  
 表示されたら、"ファイル送信アダプターがファイルを開くことができません*\<filename\>* 書き込み用"、dynamic の使用を送信するときに、BizTalk Server イベント ログにエラーの送信ポート。  
  
 この問題が発生したときに、 **BTS します。OutBoundTransportLocation**プロパティがオーケストレーションの式で定義されていると、ファイル トランスポートを指定すると、たとえば、次の式では実行時に、このエラーが発生します。  
  
```  
Message2=Message1;  
Message2(BTS.OutboundTransportLocation) = "file:///c:/test/out";  
MySendPort(Microsoft.XLANGs.BaseTypes.Address)=Message2(BTS.OutboundTransportLocation);  
```  
  
 \- または -  
  
```  
Message2=Message1;  
Message2(BTS.OutboundTransportLocation) = "file://mymachine/test/out";  
MySendPort(Microsoft.XLANGs.BaseTypes.Address)=Message2(BTS.OutboundTransportLocation);  
```  
  
### <a name="cause"></a>原因  
 この問題は、実行時にオーケストレーション エンジンは、テキストを削除するために発生します。"**file://"** から指定された URL。 そのため、上記の例を使用して、"file:///c:/test/out"が \c:\test\out として評価され、"file://mymachine/test/out"は \c: として評価されます。  
  
### <a name="resolution"></a>解決策  
 URL を指定する場合、 **BTS します。OutBoundTransportLocation**プロパティを指定する式を追加または削除「/」文字です。 上記の例を使用して、 **BTS します。OutBoundTransportLocation**として"file://c:/test/out"これに評価される c:\test\out または"file:///mymachine/test/out"に評価されるプロパティを定義する必要があります\\\mymachine\test\out します。