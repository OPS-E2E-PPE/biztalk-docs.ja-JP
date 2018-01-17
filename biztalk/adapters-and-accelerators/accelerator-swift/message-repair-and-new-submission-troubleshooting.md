---
title: "メッセージの修復と新しい送信のトラブルシューティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- troubleshooting, Message Repair and New Submission
- Message Repair and New Submission, troubleshooting
ms.assetid: bb07a286-6f02-4639-b5fa-a3647e356ac8
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d341a7f03c70e1ddcd242d7804b162338798e94
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="message-repair-and-new-submission-troubleshooting"></a>Message Repair and 新しい送信のトラブルシューティング
## <a name="a-repaired-message-cannot-be-submitted-if-the-envelope-schema-is-not-deployed"></a>エンベロープ スキーマが展開されていない場合は、修復されたメッセージを送信することはできません。  
  
### <a name="symptom"></a>現象  
 修復するメッセージを送信しようとする[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]次のメッセージをポストします。  
  
 "アダプターが送信する送信ポートにメッセージの移動に失敗しました"http://mrsrtest:80/StsWebReceive/default.aspx?PartnerId=Unparsed & FolderType MessagesInbox を ="です。 この送信ポートの指定された再試行間隔の後に再送信されます。 詳細:「80131600」です。 詳細については、ヘルプとサポート センターを参照してください[http://go.microsoft.com/fwlink/?LinkId=142493](http://go.microsoft.com/fwlink/?LinkId=142493)です。  
  
### <a name="possible-cause"></a>考えられる原因  
 エンベロープ スキーマは展開されません。 これは、MT に当てはまります*xxx*メッセージまたは解析が失敗したすべてのメッセージ。  
  
### <a name="solution"></a>解決方法  
 使用している各メッセージ スキーマをエンベロープ スキーマを展開 (\<ドライブ\>: \Program Files\Microsoft BizTalk Accelerator 用 SWIFT\<バージョン\>メッセージ パック \SWIFT Messages\ A4SWIFT SRG\<バージョン\>\Category n\MTxxx.xsd)、未解析のエンベロープ スキーマ (\<ドライブ\>: \Program Files\Microsoft BizTalk Accelerator 用 SWIFT\<バージョン\>メッセージ パック \SWIFT Messages\ A4SWIFT SRG\<バージョン\>\ 未解析 Message\EnvelopeUnparsedMessage.xsd)。 詳細については、次を参照してください。 [A4SWIFT のスキーマを展開する](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md)です。  
  
## <a name="you-cannot-submit-a-fixed-unparsed-message-from-a-mrsr-site-library-named-other-than-unparsed"></a>"Unparsed"以外の名前付き MRSR サイトのライブラリから固定未解析のメッセージを送信することはできません。  
  
### <a name="symptom"></a>現象  
 "Unparsed"名前が付いていない MRSR サイトのドキュメント ライブラリから修正した未解析のメッセージを送信しようとすると、操作は失敗します。  
  
### <a name="possible-cause"></a>考えられる原因  
 A4SWIFT は、"Unparsed"名前が指定されていない、ライブラリからのメッセージを正常に送信できません。 MRSR (メッセージ修復) 機能をインストールする前に、既存の「Unparsed」ドキュメント ライブラリを MRSR サイトにある、A4SWIFT セットアップは、サフィックスを持つ"Unparsed"というタイトル未解析のメッセージのライブラリを作成します。 A4SWIFT を解析できませんでしたメッセージを受信時にメッセージをルーティング作成したライブラリ。 ただし、そのライブラリからのメッセージを送信しようとすると、操作が失敗します。  
  
### <a name="solution"></a>解決方法  
 MRSR 機能を削除、未解析のライブラリを削除してから再インストール、MRSR 機能します。  
  
## <a name="cannot-loop-back-a-message-in-a-two-stage-workflow"></a>2 段階のワークフローでメッセージをループバックことはできません。  
  
### <a name="symptom"></a>現象  
 ワークフローを作成する段階のみ、および修復段階の修復段階でメッセージを拒否した場合、送信は失敗します。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]メッセージを MessageBox にルーティングし、次のエラー メッセージ。  
  
 「をリセットできませんでした、ワークフローの最初のステージにします。」  
  
### <a name="possible-cause"></a>考えられる原因  
 メッセージのループバックはワークフローを作成する段階のみ、および修復段階ではサポートされていません。  
  
### <a name="solution"></a>解決方法  
 2 段階のワークフローに別のステージを追加または送信をキャンセルします。  
  
## <a name="cannot-open-a-message-in-the-repair-inbox-in-mrsr"></a>MRSR で修復受信トレイにメッセージを開くことができません。  
  
### <a name="symptom"></a>現象  
 MRSR で修復の受信トレイでメッセージを開いたときに、ポップアップで、次のエラー メッセージが表示されます。  
  
 "ログイン 'A4SWIFT' で要求されたデータベースを開くことができません。 ログインに失敗しました。 ユーザー ' NT authority \network SERVICE' はログインできませんでした。  
  
### <a name="possible-cause"></a>考えられる原因  
 ログイン アカウント A4SWIFT_MRSR web サービスを実行する web アプリケーションは、ネットワーク サービス、ローカルではないか、ドメイン アカウントは、A4SWIFT Users グループです。  
  
### <a name="solution"></a>解決方法  
 A4SWIFT_MRSR web サービスを実行する web アプリケーションのログイン アカウントを変更します。  
  
##### <a name="to-change-the-login-account-for-the-web-application-that-the-a4swiftmrsr-web-service-runs-under"></a>A4SWIFT_MRSR web サービスを実行する web アプリケーションのログイン アカウントを変更するには  
  
1.  をクリックして **開始**, 、 をポイント **すべてのプログラム**, 、 をポイント **管理ツール**, 、 をクリックし、 **インターネット インフォメーション サービス (IIS) マネージャー**します。  
  
2.  IIS マネージャーで、展開、  ***\<サーバー名\>* (ローカル コンピューター)**  ノード、**アプリケーション プール**ノードおよび**Webサイト**ノード。 [Web サイト] ノードで、展開、 **Default Web Site**ノード。  
  
3.  [既定の Web サイト] ノードを右クリックして**A4SWIFT_MRSR**、クリックして**プロパティ**です。  
  
4.  A4SWIFT_MRSR プロパティ ダイアログ ボックスで、アプリケーション プールに注意してください。  
  
5.  IIS マネージャー ダイアログ ボックスの アプリケーション プール ノードの下で A4SWIFT_MRSR のアプリケーション プールを右クリックし、をクリックして**プロパティ**です。  
  
6.  \<アプリケーション プール名\>プロパティ ダイアログ ボックスをクリックして、 **Identity**注意してください。 場合**定義済み**がクリックされたと**Network Service**はクリックして選択すると、**構成可能**ローカルまたはドメイン アカウントを入力し、パスワードを入力します。 **[OK]**をクリックします。  
  
## <a name="a-message-created-in-mrsr-site-on-a-localized-computer-is-not-processed"></a>ローカライズされたコンピューター上の MRSR サイトで作成されたというメッセージが処理されません。  
  
### <a name="symptom"></a>現象  
 ローカライズされたプラットフォームで実行されている A4SWIFT の英語版に作業しているユーザーが内のメッセージを作成すると、 [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] MRSR の形式し、メッセージを正常に送信 Message Repair and New Submission が消費できるように、メッセージが表示されますオーケストレーションが正常に処理されるものはありません。 メッセージが送信トレイに送信されたけれども、BizTalk アダプタでは選択されません。 エラーまたは警告が発行されていなければ、イベント ビューアー、および HAT で実行中のオーケストレーション インスタンスのレコードがありません。  
  
### <a name="possible-cause"></a>考えられる原因  
 STS の URI として入力したパスです。送信トレイの受信場所には、ローカライズされた名前ではなく、英語名が含まれています。  
  
### <a name="solution"></a>解決方法  
 STS の URI アドレスを変更します。送信トレイの受信場所を次のようにします。  
  
1.  BizTalk Server 2009 の管理コンソールで、展開、 **BizTalk グループ**、**アプリケーション**、および**BizTalk アプリケーション 1 ノード**です。  
  
2.  をクリックして**受信場所**です。  
  
3.  ダブルクリックして**Sts.Outbox.Location**です。  
  
4.  [受信場所のプロパティ] ダイアログ ボックスで、**構成**です。  
  
5.  トランスポートのプロパティ ダイアログ ボックスの値を置き換える**SharePointSite URL**ローカライズ版に相当します。  
  
6.  をクリックして**[ok]**、順にクリック**OK**です。  
  
## <a name="removing-a-role-while-it-is-processing-a-message-results-in-incomplete-removal-of-documents-and-artifacts"></a>不完全な削除のドキュメントとの成果物、メッセージの結果を処理している間は、役割を削除します。  
  
### <a name="symptom"></a>現象  
 プロファイルの Web クライアント ロールを削除するときに、すべてのドキュメントと、ロールに関連付けられている成果物を削除することを示すダイアログ ボックスがポストされます。 ただし、ロールは、A4SWIFT 管理コンソールで、部門からは削除されず、MRSR から (受信トレイおよび送信済みアイテム) の役割のドキュメント フォルダーは削除されません。 パーティ、送信ポート、およびロールに関連付けられているアグリーメントが削除され、ロールのプロファイルは展開されていません。  
  
### <a name="possible-cause"></a>考えられる原因  
 メッセージは MRSR で、ロールの受信トレイに残っており、メッセージがで開かれて、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォーム。  
  
### <a name="solution"></a>解決方法  
 MRSR サイトの受信トレイからメッセージを手動で削除し、削除された役割に関連付けられているドキュメント ライブラリを削除します。 フォームを閉じて、もう一度の役割を削除します。  
  
## <a name="message-processing-fails-as-a-result-of-an-error-in-the-bic-master-policy"></a>エラーのために、BIC マスター ポリシーの結果としてメッセージの処理が失敗しました。  
  
### <a name="symptom"></a>現象  
 処理対象のメッセージを送信するときに、次のエラーが表示されます。  
  
 "、BicMasterPolicy の実行中にエラーが発生しました。 有効な値について、ポリシーを確認します。"  
  
### <a name="possible-cause"></a>考えられる原因  
 SQL サーバー名、BIC データベース名、および統合セキュリティ ファイル内の値、BIC_Master_Policy.xml で*\<ドライブ\>*: \Program Files\ Microsoft BizTalk Accelerator 用 SWIFT\<バージョン\>メッセージ Pack\SWIFT Messages\A4SWIFT SRG\<バージョン\>二重引用符で囲まれた \Base ポリシーが含まれています。 BIC 検証を有効にするこれらの文字列に入力既定 BIC_Master_Policy.xml ファイル」の説明に従って[有効にすると検証の銀行識別コード](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md)です。  
  
### <a name="solution"></a>解決方法  
 BIC マスター ポリシーを修復するには、手順に従います。  
  
> [!NOTE]
>  BIC マスター ポリシーの展開に関する詳細については、次を参照してください。 [BRE ルールの展開](../../adapters-and-accelerators/accelerator-swift/deploying-bre-rules.md)です。  
  
1.  ビジネス ルール作成ツールで、BIC_Master_Policy のバージョン 1.0 の展開を解除し、BIC_Master_Policy を削除します。  
  
2.  メモ帳などのテキスト エディターで開くで BIC_Master_Policy.xml *\<ドライブ\>*: \Program Files\ Microsoft BizTalk Accelerator 用 SWIFT\<バージョン\>メッセージ Pack\SWIFTMessages\A4SWIFT SRG\<バージョン\>\Base ポリシー。 SQL Server 名を囲む二重引用符を削除、BIC データベース名、およびセキュリティの値を統合します。  
  
3.  ビジネス ルール エンジン展開ウィザードで、BIC_Master_Policy.xml をインポートし、BIC_Master_Policy.xml を展開します。  
  
4.  Services MMC で、ルール エンジン更新サービスと BizTalk 受信ホスト サービスを再起動します。  
  
## <a name="a4swift-will-not-be-able-to-process-an-unparsed-message-without-proper-database-permissions"></a>A4SWIFT では、適切なデータベース権限のない未解析のメッセージを処理できません。  
  
### <a name="symptom"></a>現象  
 A4SWIFT を解析できないメッセージをドロップすると、A4SWIFT メッセージを処理することはありません、キャッチされない例外で失敗です。  
  
### <a name="possible-cause"></a>考えられる原因  
 データベースのアクセス許可の問題があります。 HostSvc は、BizTalk サービスのログオン アカウントは、A4SWIFT 管理者および A4SWIFT ユーザー グループに含まれていません。  
  
### <a name="solution"></a>解決方法  
 A4SWIFT の管理者と A4SWIFT ユーザー グループに BizTalk サービスのログオン アカウントを追加します。  
  
## <a name="a-timeout-of-the-infopath-repair-form-can-result-in-two-copies-of-a-message-in-different-stages-of-the-repair-workflow"></a>修復の InfoPath フォームのタイムアウト、メッセージの 2 つのコピーになります修復ワークフローのさまざまな段階  
  
### <a name="symptom"></a>現象  
 フォームの送信でエラーがある場合 (どのワークフロー ステージの)、InfoPath フォームからのメッセージを送信するときに、エラー メッセージのコピーを 2 つ可能性があります。 1 つのメッセージがの現在のステージは受信トレイに残っており、その他のメッセージは、ワークフローの次のロールの受信トレイにします。 これらのメッセージを処理しようとしていますでは、次に発生します。  
  
-   ワークフローの次のロールの受信トレイからメッセージを送信する場合は、メッセージがワークフローから続行されます。  
  
-   次のステージの受信トレイから送信されたメッセージの処理が完了した後、現在のステージの受信トレイからメッセージを送信する場合は、ルーティング エラーにより、現在の受信トレイから送信されたメッセージが中断されます。  
  
-   次のステージの受信トレイから送信されたメッセージが完了する前に、現在のステージの受信トレイにメッセージを送信する場合、処理の段階では、受信トレイに現在のステージの受信トレイから送信されたメッセージが返されます、表示されます。次のエラーが表示されます。  
    "ためにワークフローをリセットしますメッセージが改ざんされたか、ユーザーは、このステージでは有効ではありません。"。  
    その後、次のステージでは、受信トレイからメッセージを送信する場合にワークフローもリセットされます。 現在のステージの受信トレイに返され、上記のエラーが表示されます。  
  
### <a name="possible-cause"></a>考えられる原因  
 InfoPath フォームには、Microsoft Windows Sharepoint Services および検証を実行するカスタム Web サービスを使用して BizTalk Server にメッセージが送信されます。 メッセージを送信するために複数の手順では、この手順は、Windows Sharepoint Services がトランザクションではないため、トランザクションではないです。 この制限に合わせて、MRSR オーケストレーションが検出し、メッセージの送信から発生したエラーから回復する回復ロジック組み込まれています。 MRSR オーケストレーションは、常に SWIFT に送信される重複したメッセージを回避します。  
  
### <a name="solution"></a>解決方法  
 このような場合は、ワークフローのかなり後のあるメッセージを取得し、ワークフローの以前の段階にあるその他のメッセージを処理する前に、ワークフローを完了する必要があります。 ワークフローのかなり後のあるメッセージには、処理が完了したら後、適宜 (ルーティング エラーにより中断されて) を 2 番目のメッセージを破棄することができます。  
  
 られているメッセージさらにに沿ってワークフローの完了しなかった場合、2 番目のメッセージを処理する前に、処理、もう一度、ワークフローの InfoPath フォームの修復のかなり後のあるメッセージを修復して、送信してください。 処理の完了を許可し、2 番目のメッセージを送信します。 2 番目のメッセージが中断された後に処分してください。  
  
## <a name="a-new-submission-with-no-verify-stage-will-result-in-a-suspended-message"></a>中断されたメッセージでない検証ステージの提出が新しいになります  
  
### <a name="symptom"></a>現象  
 検証ステージを持たないワークフロー内で新しいメッセージを送信するときに、メッセージは中断されます。  
  
### <a name="possible-cause"></a>考えられる原因  
 検証ステージの欠如なりますが、メッセージが中断を作成するには、A4SWIFT_MRSRLastStage は設定されていない場合  
  
### <a name="solution"></a>解決方法  
 A4SWIFT_MRSRLastStage のサブスクリプションを使用して = = を確実にメッセージのルーティングが正常に作成します。  
  
## <a name="validation-of-message-results-a-parse-error-in-the-infopath-form-task-pane"></a>メッセージの検証の結果、"エラー"で解析フォームの InfoPath タスク ペイン  
  
### <a name="symptom"></a>現象  
 InfoPath のフォーム作業ウィンドウを示しています「解析エラーです。」任意の説明なしでメッセージのボタンを検証します。  
  
### <a name="solution"></a>解決方法  
 MRSR web サービスを再起動または iisreset を実行します。  
  
## <a name="publishing-an-infopath-form-results-an-authorization-error"></a>承認エラーの結果、InfoPath フォームを発行します。  
  
### <a name="symptom"></a>現象  
 承認エラーは、InfoPath フォームを公開します。  
  
### <a name="solution"></a>解決方法  
 MRSR サイトの URL で localhost では、コンピューター名を置き換えます。  
  
## <a name="infopath-form-task-pane-shows-html-source-code"></a>フォームの InfoPath タスク ペインは、HTML ソース コードを示しています。  
  
### <a name="symptom"></a>現象  
 フォームの InfoPath タスク ペインは、Web コントロールではなく HTML ソース コードを示しています。  
  
### <a name="solution"></a>解決方法  
 移動して**ツール**-> **セキュリティ タブ** -> **インターネット ゾーン**、有効にして**コンテンツに基づいてファイルを開く拡張機能ではなく**下にあるその他。  
  
## <a name="profile-web-client-website-results-an-authentication-error"></a>プロファイル Web クライアントの web サイト認証エラーを結果します。  
  
### <a name="symptom"></a>現象  
 Web クライアントの web サイトをプロファイルには、認証エラーが表示されます。  
  
### <a name="solution"></a>解決方法  
 実行、 **BTSharePointAdapterWSAppPool**と**DefaultAppPoolApplication** ]-> [し、管理者アカウントでインターネット情報サービス (iis) にプールします。  
  
## <a name="see-also"></a>参照  
 [トラブルシューティング: 問題と解決策](../../adapters-and-accelerators/accelerator-swift/troubleshooting-issues-and-resolutions1.md)