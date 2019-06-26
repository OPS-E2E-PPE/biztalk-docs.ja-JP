---
title: Message Repair and New Submission のトラブルシューティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting, Message Repair and New Submission
- Message Repair and New Submission, troubleshooting
ms.assetid: bb07a286-6f02-4639-b5fa-a3647e356ac8
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e3017b16f0558f40d7dce82724c65792483e4da
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530246"
---
# <a name="message-repair-and-new-submission-troubleshooting"></a>Message Repair and New Submission のトラブルシューティング
## <a name="a-repaired-message-cannot-be-submitted-if-the-envelope-schema-is-not-deployed"></a>エンベロープ スキーマが展開されていない場合、修復されたメッセージを送信することはできません。  
  
### <a name="symptom"></a>現象  
 修復するメッセージを送信しようとしたときに[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]次のメッセージを投稿します。  
  
 「アダプターは、送信ポートにメッセージの移動を送信できませんでした」<http://mrsrtest:80/StsWebReceive/default.aspx?PartnerId=Unparsed&FolderType=MessagesInbox>"。 この送信ポートの指定された再試行間隔後に再送信されます。 詳細:「80131600」。 詳細については、ヘルプとサポート センターを参照してください[ http://go.microsoft.com/fwlink/?LinkId=142493](http://go.microsoft.com/fwlink/?LinkId=142493)します。  
  
### <a name="possible-cause"></a>考えられる原因  
 エンベロープ スキーマは展開されません。 これは、MT の true*xxx*メッセージまたはメッセージを解析に失敗しました。  
  
### <a name="solution"></a>解決方法  
 使用している各メッセージ スキーマに対してエンベロープ スキーマを展開 (\<ドライブ\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT\<バージョン\>メッセージ パック \SWIFT Messages\ A4SWIFT SRG\<バージョン\>\Category n\MTxxx.xsd)、未解析のエンベロープ スキーマ (\<ドライブ\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT\<バージョン\>メッセージ パック \SWIFT Messages\ A4SWIFT-SRG\<バージョン\>\ 未解析 Message\EnvelopeUnparsedMessage.xsd)。 詳細については、次を参照してください。 [A4SWIFT スキーマの展開](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md)します。  
  
## <a name="you-cannot-submit-a-fixed-unparsed-message-from-a-mrsr-site-library-named-other-than-unparsed"></a>"Unparsed"以外をという名前の MRSR サイト ライブラリから固定未解析メッセージを送信することはできません。  
  
### <a name="symptom"></a>現象  
 "Unparsed"名前が付いていません MRSR サイトのドキュメント ライブラリからの修正を未解析メッセージを送信しようとすると、操作が失敗します。  
  
### <a name="possible-cause"></a>考えられる原因  
 A4SWIFT では、"Unparsed"名前が付いていないライブラリからのメッセージが正常に送信できません。 MRSR (メッセージの修復) 機能をインストールする前に、MRSR サイトで既存の"Unparsed"ドキュメント ライブラリをした場合、A4SWIFT セットアップは未解析メッセージの"Unparsed"のサフィックスを持つ対象のライブラリを作成します。 A4SWIFT を解析できませんでしたメッセージを受信した場合は、メッセージを作成したライブラリにルーティングします。 ただし、そのライブラリからのメッセージを送信しようとするときに、操作は失敗します。  
  
### <a name="solution"></a>解決方法  
 MRSR 機能を削除、未解析のライブラリを削除してから再インストール MRSR 機能します。  
  
## <a name="cannot-loop-back-a-message-in-a-two-stage-workflow"></a>2 段階のワークフロー内のメッセージをループバックことはできません。  
  
### <a name="symptom"></a>現象  
 のみの作成段階と修復段階を持つワークフローの修復段階でメッセージを拒否した場合、送信は失敗します。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] メッセージを MessageBox にルーティングし、次のエラー メッセージ。  
  
 「をリセットできませんでした、ワークフローの最初のステージを。」  
  
### <a name="possible-cause"></a>考えられる原因  
 メッセージのループバックは作成段階のみと修復段階を持つワークフローではサポートされていません。  
  
### <a name="solution"></a>解決方法  
 2 段階のワークフローに別のステージを追加または送信をキャンセルします。  
  
## <a name="cannot-open-a-message-in-the-repair-inbox-in-mrsr"></a>MRSR で修復の受信トレイにメッセージを開くことができません。  
  
### <a name="symptom"></a>現象  
 MRSR で修復の受信トレイにメッセージを開くときに、ポップアップで、次のエラー メッセージが表示されます。  
  
 "ログイン 'A4SWIFT' で要求されたデータベースを開くことができません。 ログインに失敗しました。 ユーザー ' NT authority \network SERVICE' はログインできませんでした。  
  
### <a name="possible-cause"></a>考えられる原因  
 ログイン アカウント A4SWIFT_MRSR の web サービスを実行する web アプリケーションがネットワーク サービス、ローカルではない、またはドメイン アカウントは、A4SWIFT ユーザーのグループでは。  
  
### <a name="solution"></a>解決方法  
 A4SWIFT_MRSR の web サービスを実行する web アプリケーションのログイン アカウントを変更します。  
  
##### <a name="to-change-the-login-account-for-the-web-application-that-the-a4swiftmrsr-web-service-runs-under"></a>A4SWIFT_MRSR の web サービスを実行する web アプリケーションのログイン アカウントを変更するには  
  
1.  クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリックします**インターネット インフォメーション サービス (IIS) マネージャー**.  
  
2.  IIS マネージャーで、展開、 ***\<サーバー名\>* (ローカル コンピューター)** ノード、**アプリケーション プール**ノードと**Webサイト**ノード。 [Web サイト] ノードで、展開、**既定の Web サイト**ノード。  
  
3.  [既定の Web サイト] ノードを右クリックして**A4SWIFT_MRSR**、 をクリックし、**プロパティ**します。  
  
4.  A4SWIFT_MRSR プロパティ ダイアログ ボックスで、アプリケーション プールに注意してください。  
  
5.  IIS マネージャー ダイアログ ボックスの アプリケーション プール ノードで、A4SWIFT_MRSR のアプリケーション プールを右クリックし、**プロパティ**します。  
  
6.  \<アプリケーション プール名\>プロパティ ダイアログ ボックスで、をクリックして、 **Identity**に注意してください。 場合**定義済み**がクリックされたと**ネットワーク サービス**が選択されていること、**構成可能**、ローカルまたはドメイン アカウントを入力し、パスワードを入力します。 [**OK**] をクリックします。  
  
## <a name="a-message-created-in-mrsr-site-on-a-localized-computer-is-not-processed"></a>ローカライズされたコンピューター上の MRSR サイトで作成されたメッセージは処理されません。  
  
### <a name="symptom"></a>現象  
 ローカライズされたプラットフォームで実行されている A4SWIFT の英語版で作業しているユーザーが内のメッセージを作成するときに、 [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] MRSR、フォーム、および Message Repair and New Submission で使用するメッセージが表示されるメッセージを正常に送信する.オーケストレーションが正常に処理されていません。 メッセージは、送信トレイに送信されますが、BizTalk アダプタでは取得されません。 エラーまたは警告が発行されていなければ、イベント ビューアー、および HAT での実行中のオーケストレーション インスタンスのレコードがありません。  
  
### <a name="possible-cause"></a>考えられる原因  
 STS の URI として入力するパス。送信トレイの受信場所には、ローカライズされた名前ではなく、英語名が含まれています。  
  
### <a name="solution"></a>解決方法  
 STS の URI アドレスを変更します。送信トレイの受信場所を次のようにします。  
  
1.  BizTalk Server 2009 の管理コンソールで、展開、 **BizTalk グループ**、**アプリケーション**、および**BizTalk アプリケーション 1 ノード**します。  
  
2.  クリックして**受信場所**します。  
  
3.  ダブルクリック**Sts.Outbox.Location**します。  
  
4.  [受信場所のプロパティ] ダイアログ ボックスで、**構成**します。  
  
5.  トランスポートのプロパティ ダイアログ ボックスでの値を置き換える**SharePointSite URL**ローカライズと等価です。  
  
6.  をクリックして**OK**、順にクリックします**OK**。  
  
## <a name="removing-a-role-while-it-is-processing-a-message-results-in-incomplete-removal-of-documents-and-artifacts"></a>ドキュメントおよび成果物の削除が不完全なメッセージの結果を処理している間にロールを削除します。  
  
### <a name="symptom"></a>現象  
 プロファイル Web クライアント ロールを削除するときに、すべてのドキュメントと、ロールに関連付けられた成果物が削除されることを示すダイアログ ボックスがポストされます。 ただし、ロールは、部門、A4SWIFT 管理コンソール内からは削除されず、MRSR からロールのドキュメント フォルダー (受信トレイおよび送信済みアイテム) は削除されません。 パーティ、送信ポート、およびロールに関連付けられているアグリーメントを削除すると、およびロールのプロファイルが展開解除します。  
  
### <a name="possible-cause"></a>考えられる原因  
 メッセージは、MRSR でロールの受信トレイのままであり、メッセージがで開いてその[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォーム。  
  
### <a name="solution"></a>解決方法  
 MRSR サイトの受信トレイからメッセージを手動で削除し、削除された役割に関連付けられているドキュメント ライブラリを削除します。 フォームを閉じて、もう一度役割を削除します。  
  
## <a name="message-processing-fails-as-a-result-of-an-error-in-the-bic-master-policy"></a>BIC マスター ポリシーのエラーの結果としてメッセージの処理が失敗しました。  
  
### <a name="symptom"></a>現象  
 処理対象のメッセージを送信するときに、次のエラーが表示されます。  
  
 "、BicMasterPolicy の実行中にエラーが発生しました。 有効な値について、ポリシーを確認します。"  
  
### <a name="possible-cause"></a>考えられる原因  
 SQL Server 名、BIC データベース名、および BIC_Master_Policy.xml ファイル内の統合セキュリティ値*\<ドライブ\>*: Microsoft BizTalk Accelerator for SWIFT \Program Files\\<バージョン\>メッセージ Pack\SWIFT Messages\A4SWIFT-SRG\<バージョン\>二重引用符で囲まれた \Base ポリシーが含まれています。 BIC 検証を有効にするこれらの文字列に入力既定 BIC_Master_Policy.xml ファイル」の説明に従って[を有効にする検証の銀行識別コード](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md)します。  
  
### <a name="solution"></a>解決方法  
 BIC マスター ポリシーを修復するには、ように進めます。  
  
> [!NOTE]
>  BIC マスター ポリシーの展開に関する詳細については、次を参照してください。 [BRE ルールの展開](../../adapters-and-accelerators/accelerator-swift/deploying-bre-rules.md)します。  
  
1.  ビジネス ルール作成ツール、BIC_Master_Policy のバージョン 1.0 の展開を解除し、BIC_Master_Policy を削除します。  
  
2.  メモ帳などのテキスト エディターで開くで BIC_Master_Policy.xml *\<ドライブ\>*: Microsoft BizTalk Accelerator for SWIFT \Program Files\\<バージョン\>メッセージ Pack\SWIFTMessages\A4SWIFT SRG\<バージョン\>\Base ポリシー。 SQL Server 名を囲む二重引用符を削除、BIC データベース名、およびセキュリティの値を統合します。  
  
3.  ビジネス ルール エンジン展開ウィザードで、BIC_Master_Policy.xml をインポートし、BIC_Master_Policy.xml を展開します。  
  
4.  サービス mmc で、ルール エンジン更新サービスと BizTalk 受信ホスト サービスを再起動します。  
  
## <a name="a4swift-will-not-be-able-to-process-an-unparsed-message-without-proper-database-permissions"></a>A4SWIFT では、適切なデータベース権限のない未解析のメッセージを処理できません。  
  
### <a name="symptom"></a>現象  
 A4SWIFT を解析できないメッセージをドロップすると、A4SWIFT は、メッセージを処理することができませんが、キャッチされない例外で失敗します。  
  
### <a name="possible-cause"></a>考えられる原因  
 データベース アクセス許可の問題があります。 HostSvc は、既定では、BizTalk サービスのログオン アカウントは、A4SWIFT 管理者と A4SWIFT ユーザーのグループに含まれていません。  
  
### <a name="solution"></a>解決方法  
 A4SWIFT 管理者と A4SWIFT ユーザーのグループに BizTalk サービスのログオン アカウントを追加します。  
  
## <a name="a-timeout-of-the-infopath-repair-form-can-result-in-two-copies-of-a-message-in-different-stages-of-the-repair-workflow"></a>修復の InfoPath フォームのタイムアウトは、修復ワークフローのさまざまな段階でメッセージの 2 つのコピーで結果ことができます。  
  
### <a name="symptom"></a>現象  
 フォームの送信でエラーがある場合、ワークフロー ステージ)、(InfoPath フォームからのメッセージを送信するときに、エラー メッセージのコピーを 2 つ可能性があります。 現在のステージでは、1 つのメッセージは、受信トレイのままであり、ワークフローで [次へ]、ロールの受信トレイの他のメッセージでは。 これらのメッセージを処理しようとは、次のようになります。  
  
-   ワークフローの次のロールの受信トレイからメッセージを送信する場合は、メッセージがワークフローから続行されます。  
  
-   現在のステージの次のステージの受信トレイから送信されたメッセージの処理が完了したが、受信トレイからメッセージを送信する場合は、ルーティング エラーにより、現在の受信トレイから送信されたメッセージが中断されます。  
  
-   次のステージの受信トレイから送信されたメッセージが完了する前に、現在のステージの受信トレイにメッセージを送信する場合は、処理、そのステージでは、受信トレイに現在のステージの受信トレイから送信されたメッセージが返されますは、次のエラーが表示されます。  
    "ためにワークフローをリセットしていますメッセージが改ざんされたか、ユーザーは、このステージでは有効ではありません。"。  
    その後、次のステージでは、受信トレイからメッセージを送信する場合のワークフローもリセットされます。 現在のステージの受信トレイに返され、上記のエラーが表示されます。  
  
### <a name="possible-cause"></a>考えられる原因  
 InfoPath フォームには、Microsoft Windows Sharepoint Services および検証を実行するカスタム Web サービスを使用して BizTalk Server にメッセージが送信されます。 メッセージを送信するために複数の手順では、これらの手順は、Windows Sharepoint Services のトランザクションがないため、トランザクションではありません。 この制限を対応するためには MRSR オーケストレーションが検出し、メッセージの送信から発生したエラーから回復する回復ロジックで構築されています。 MRSR オーケストレーションは、常に SWIFT に送信される重複したメッセージを回避します。  
  
### <a name="solution"></a>解決方法  
 このような場合は、ワークフロー内にさらにメッセージを選択、ワークフローの初期段階では、その他のメッセージを処理する前に、ワークフローを完了してください。 ワークフロー内にさらにメッセージが処理を完了してから、必要に応じて (ルーティング エラーにより中断されました) を 2 番目のメッセージを破棄することができます。  
  
 メッセージさらにに沿ってワークフローの完了しなかった場合、2 番目のメッセージを処理する前に処理、なかで修復 InfoPath フォーム、ワークフローでは、メッセージをもう一度修復し、それを送信ください。 処理の完了を許可して、2 番目のメッセージを送信します。 2 番目のメッセージが中断された後は、それを破棄します。  
  
## <a name="a-new-submission-with-no-verify-stage-will-result-in-a-suspended-message"></a>中断されたメッセージが発生しない検証ステージで新しい送信  
  
### <a name="symptom"></a>現象  
 検証ステージを持たないワークフローで新しいメッセージを送信するときに、メッセージが中断されます。  
  
### <a name="possible-cause"></a>考えられる原因  
 作成するには、A4SWIFT_MRSRLastStage は設定されていない場合、検証ステージの欠如の結果は保留メッセージ。  
  
### <a name="solution"></a>解決方法  
 A4SWIFT_MRSRLastStage のサブスクリプションを使用して、メッセージが適切にルーティングされるようにするには作成を = =。  
  
## <a name="validation-of-message-results-a-parse-error-in-the-infopath-form-task-pane"></a>メッセージの検証結果を"エラー"で解析フォームの InfoPath タスク ペイン  
  
### <a name="symptom"></a>現象  
 InfoPath のフォームの作業ウィンドウで「解析エラー」を表示、説明のないメッセージ ボタンを検証します。  
  
### <a name="solution"></a>解決方法  
 MRSR の web サービスを再起動または iisreset を実行します。  
  
## <a name="publishing-an-infopath-form-results-an-authorization-error"></a>承認エラーの結果、InfoPath フォームの発行  
  
### <a name="symptom"></a>現象  
 承認エラーは、InfoPath フォームを公開します。  
  
### <a name="solution"></a>解決方法  
 MRSR サイトの URL で localhost では、コンピューター名を置き換えます。  
  
## <a name="infopath-form-task-pane-shows-html-source-code"></a>フォームの InfoPath タスク ペインは、HTML ソース コードを示しています。  
  
### <a name="symptom"></a>現象  
 InfoPath フォームのタスク ペインには、Web コントロールではなく HTML ソース コードが表示されます。  
  
### <a name="solution"></a>解決方法  
 移動して**ツール**-> **セキュリティ タブ** -> **インターネット ゾーン**、有効にして**コンテンツに基づいてファイルを開く拡張機能ではなく** その他。  
  
## <a name="profile-web-client-website-results-an-authentication-error"></a>プロファイル Web クライアントの web サイト認証エラーを結果します。  
  
### <a name="symptom"></a>現象  
 Web クライアントの web サイトをプロファイルには、認証エラーが表示されます。  
  
### <a name="solution"></a>解決方法  
 実行、 **BTSharePointAdapterWSAppPool**と**DefaultAppPoolApplication** -> し、管理者アカウントでインターネット情報サービス (iis) のプールします。  
  
## <a name="see-also"></a>参照  
 [トラブルシューティング: 問題と解決方法](../../adapters-and-accelerators/accelerator-swift/troubleshooting-issues-and-resolutions1.md)