---
title: 既知の問題は、EDI および AS2 状態レポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d755dca-a4b6-44be-bc45-88c0b17685a0
caps.latest.revision: 32
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1349bf374f90739cac9253784b87f65ed897ff33
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2018
ms.locfileid: "50753042"
---
# <a name="known-issues-with-edi-and-as2-status-reporting"></a>EDI および AS2 状態レポートに関する既知の問題
このトピックでは、EDI 状態レポートでは、BizTalk Server に関する既知の問題について説明します。  
  
## <a name="batch-status-reporting-data-may-not-be-updated-if-the-batch-orchestration-is-stopped-outside-of-the-partner-agreement-manager"></a>バッチ オーケストレーションがパートナー アグリーメント マネージャーの外部で停止されるとバッチ状態レポート データが更新されない  
 バッチ オーケストレーション インスタンスは、パーティの [EDI のプロパティ] ダイアログ ボックスの [バッチ] ページで非アクティブ化できます。 この方法でバッチ オーケストレーション インスタンスを非アクティブ化した場合、そのバッチの状態レポート データが更新されます。 ただし、別の方法でバッチ オーケストレーションを停止した場合 (たとえば、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールの [グループの概要] ページのいずれかのクエリ ページからオーケストレーションを停止するなど)、状態レポート データが更新されず、バッチ状態レポートの内容が最新のものではなくなる可能性があります。 たとえば、バッチ オーケストレーション インスタンスが非アクティブ化されているにもかかわらず、状態レポートではバッチがアクティブであると表示される可能性があります。  
  
## <a name="the-biztalk-service-needs-to-be-restarted-after-edi-status-reporting-has-been-enabled"></a>EDI 状態レポートを有効化した後で BizTalk サービスを再起動する必要がある  
 **現象**  
  
 EDI 状態レポートが有効化されても EDI 状態レポートが生成されません。  
  
 **考えられる原因**  
  
 EDI 状態レポートをアクティブ化または非アクティブ化した後は、変更を有効にするために、BizTalk サービスを再起動する必要があります。 ソリューションで AS2EdiReceive パイプラインまたは AS2EdiSend パイプラインを使用している場合は、変更を有効にするために、BizTalk サービスと IIS サービスの両方を再起動する必要があります。  
  
 **解決方法**  
  
 [コンピューターの管理] ダイアログ ボックスで BizTalk サービスを再起動します。 AS2EdiReceive パイプラインまたは AS2EdiSend パイプラインは、ソリューションで使用されている場合、IIS 管理サービスを再起動 (を使用して、 *iisreset*コマンド) もします。  
  
> [!NOTE]
>  AS2 状態レポートを有効化するときに BizTalk サービスまたは IIS Admin サービスを再起動する必要はありません。  
  
## <a name="the-status-report-will-display-9999-for-the-year-when-the-as2-message-date-time-in-the-message-is-a-null-value"></a>AS2 メッセージの日時がメッセージ内で Null 値である場合に状態レポートに年が "9999" と表示される  
 受信 AS2 メッセージの "AS2 メッセージの日時" フィールドが Null に設定されている場合、AS2 状態レポートには、そのメッセージの "AS2 メッセージの日時" フィールドの年が "9999" と表示されます。  
  
 受信 AS2 メッセージの "AS2 メッセージの日時" フィールドを解析できない場合 (たとえば、Mon, 21 May 2007 10:08:28 NZST であった場合)、AS2 状態レポートでは、そのメッセージの "AS2 メッセージの日時" フィールドが現在の時刻に設定されます。  
  
## <a name="status-reporting-is-still-configured-after-bam-tools-have-been-uninstalled"></a>BAM ツールをアンインストールした後も状態レポートが構成されたままである  
 EDI 状態レポートをインストールするには、BAM ツールをインストールする必要があります。 しかし、BAM ツールをアンインストールしても、状態レポートは構成されたままになります。 これは仕様です。  
  
 BAM ツールを削除すると、ユーザー インターフェイスを使用して状態レポートのテーブルを検索することができなくなります。 ただし、状態レポートが有効であれば、BizTalk Server は状態レポートのテーブルにレコードを作成します。  
  
## <a name="only-one-edi-interchange-will-be-correlated-to-an-as2-message-in-the-status-report-ui"></a>状態レポートの UI で 1 つの EDI インターチェンジだけが AS2 メッセージに関連付けられる  
 AS2 メッセージに複数の EDI インターチェンジが含まれている場合、その AS2 メッセージ内の複数の EDI インターチェンジの状態を表示しようとすると、最後の EDI インターチェンジだけがインターチェンジ/確認の状態レポートに表示されます。 さらに、 **EDI のインターチェンジ制御番号**AS2/MDN の状態レポート内のフィールドは、最後のインターチェンジ制御番号のみを表示します。 インターチェンジ制御番号によって、AS2 メッセージとその EDI インターチェンジ ペイロードが関連付けられます。  
  
 AS2 メッセージ内のすべての EDI インターチェンジのデータは、状態レポート データベースに保存されます。 場合、インターチェンジ/確認の状態レポートで AS2 メッセージのすべてのインターチェンジを表示することができます、 **Control ID Equals All**句は、状態レポート クエリ。 これによって、AS2 メッセージに含まれていない他のインターチェンジも表示される可能性がありますが、"送信者パーティ"、"受信者パーティ"、"インターチェンジの日時" などのフィールドを調べることで、単一の AS2 メッセージに含まれる EDI インターチェンジを特定できます。  
  
## <a name="removing-the-bam-tools-from-a-group-will-prevent-you-from-viewing-edi-or-as2-status-reports"></a>BAM ツールをグループから削除すると EDI または AS2 状態レポートを表示できなくなる  
 BAM ツールをグループから削除した後に EDI または AS2 状態レポートを表示しようとするとエラーが発生します。 たとえば、ストアド プロシージャ bts_GetBatchStatusRecords が見つからないというエラーが発生します。 EDI または AS2 状態レポートを表示しようとしたときにエラーが表示された場合は、グループ、ランタイム、および BAM ツールが EDI と AS2 用に正しく構成されていることを確認してください。  
  
 BAM ツールを単に削除するのではなく、BAM ツールの構成を解除することにより、この問題を回避できます。 BAM ツールの構成を解除するとき、依存する EDI/AS2 機能の構成を解除するよう求めるメッセージが表示されます。 BAM ツールを削除するときは、このメッセージは表示されません。  
  
## <a name="status-reporting-will-not-work-after-an-upgrade-if-the-bam-tools-are-not-configured"></a>BAM ツールが構成されていない場合、アップグレード後に状態レポートが動作しない  
 EDI および AS2 状態レポートが動作するためには、BAM ツールが構成されている必要があります。 [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] のインストールを後続のバージョンにアップグレードするとき、アップグレード プロセスで BAM ツールを構成しないと、アップグレードしたインストールで EDI/AS2 状態レポート機能が正しく動作しません。  
  
 状態を BizTalk Server にアップグレードした後にレポートを使用する場合は、アップグレードを実行する前に、BAM ツールが構成されていることを確認します。  
  
 アップグレードを実行した後、状態レポートが動作しない場合は、アップグレード前に BAM ツールを構成したかどうかをアップグレード ログで確認します。 BAM ツールを構成しにある EdiStatusReportingActivityDefs.xml ファイルに含まれている BusinessMessageJournal BAM アクティビティを展開し、そうでない場合*\<ドライブ\>*: \Program Files\MicrosoftBizTalk Server です。  
  
## <a name="disabling-transaction-set-storage-affects-an-activated-batch-but-enabling-storage-does-not"></a>トランザクション セットの格納を無効にした場合はアクティブなバッチが影響を受けるが、格納を有効にした場合は影響を受けない  
 バッチ処理オーケストレーション インスタンスがアクティブになっているときにトランザクション セットの格納を無効にすると、変更は直ちに適用されます。 トランザクション セットの格納が有効なとき、BizTalk Server は、そのバッチのトランザクション セットを格納しますが、格納が無効になると、トランザクション セットを格納しません。 トランザクション セットの格納を無効にするには、[EDI のプロパティ] ダイアログ ボックスの [全般] ペインで、[レポート用にトランザクション セット/ペイロードを格納する] プロパティをオフにします。  
  
 ただし、トランザクション セットの格納が無効であるときにバッチ処理オーケストレーション インスタンスをアクティブにした場合、後で格納を有効にしても、作成中のバッチについてはトランザクション セットは格納されません。  
  
## <a name="unicode-as2-messages-will-not-be-displayed-completely-in-text-wire-format"></a>UNICODE AS2 メッセージがテキストのワイヤ形式で正しく表示されない  
 BizTalk Server が UNICODE 形式でエンコードされた AS2 メッセージまたは MDN を処理する場合に、メッセージをテキストのワイヤ形式で表示しようとすると、メッセージが正しく表示されません。 この問題は、UNICODE 形式の "00" バイトがストリームの末尾として解釈されるために発生します。 ただし、バイナリのワイヤ形式でメッセージを表示しようとした場合は、メッセージは正しく表示されます。  
  
 これは (全般 ペインで、AS2 のプロパティ ダイアログ ボックスの)、AS2 メッセージの状態レポートがアクティブになると、受信または送信 AS2 メッセージまたは MDN メッセージの記憶域が (の パーティ-AS2 メッセージの受信者 ペインまたは パーティ-AS2 メッセージの送信者 ペインで有効な場合に発生します。AS2 のプロパティ ダイアログ ボックスの)。  
  
## <a name="enabling-as2-status-reporting-and-send-port-body-tracking-simultaneously-may-cause-an-error"></a>AS2 状態レポート機能と送信ポートでの本文の追跡機能を同時に有効にするとエラーが発生する  
 AS2 状態レポートを有効にして、ポートでの本文を送信すると、次の追跡に同時に、エラーが表示される、イベント ビューアーで:「メッセージング エンジンに、1 つまたは複数のメッセージの削除中にあるエラーが発生」。 この問題は、送信ポートが AS2Send および AS2Receive パイプラインを使用した静的な送信請求 - 応答の AS2 送信ポートである場合に発生します。 次のプロパティが有効な場合に発生します。  
  
- "AS2 レポートをアクティブにする" プロパティ ([AS2 のプロパティ] ダイアログ ボックスの [全般] ペイン)  
  
- "エンコードされた送信 AS2 メッセージを否認不可データベースに保存する" プロパティ ([AS2 のプロパティ] ダイアログ ボックスの [パーティ - AS2 メッセージの受信者] ペイン)  
  
- "ポート処理後の要求メッセージ" プロパティ ([送信ポートのプロパティ] ダイアログ ボックスの [追跡] ペイン)  
  
  この問題を回避するには、[エンコードされた送信 AS2 メッセージを否認不可データベースに保存する] プロパティまたは [ポート処理後の要求メッセージ] プロパティをオフにします。 [ポート処理後の要求メッセージ] をオフにして、AS2 の追跡で本文情報をその他の AS2 状態レポート用の情報と共に取得できるようにする方法をお勧めします。  
  
## <a name="edi-and-as2-message-context-properties-are-not-available-after-upgrading-to-biztalk-2009"></a>BizTalk 2009 にアップグレードした後、EDI および AS2 メッセージ コンテキスト プロパティを使用できない  
 BizTalk Server にアップグレードすると、コンテキスト プロパティは表示されません状態レポートのアップグレードが発生する前に受信した EDI または AS2 のメッセージ。  アップグレード後に受信したメッセージでは、コンテキスト プロパティが正しく表示されます。  
  
 以前のバージョンの BizTalk Server では、EDI および AS2 コンテキスト プロパティ コレクションはメッセージの一部として保存されないので、アップグレード後は使用できなくなります。 AS2 メッセージの一部としてコンテキスト プロパティが格納されている BizTalk Server にアップグレードした後ただし EDI コンテキスト プロパティはありません。  
  
## <a name="interchange-date-for-received-documents-may-display-the-wrong-year-in-status-reports"></a>状態レポートに表示される受信ドキュメントのインターチェンジの日付で年が正しくない場合がある  
 受信ドキュメントでは、日付が YYMMDD 形式で指定されて、BizTalk Server は、次のロジックを使用して年の値を決定します。  
  
- YY が 75 以上である場合、年は 19YY 年として表示されます。  
  
- YY が 75 未満である場合、年は 20YY 年として表示されます。  
  
  たとえば、受信メッセージの ISA09 の値が 991113 である場合、状態レポートでは日付は 11/13/1999 として表示されます。  
  
## <a name="error-message-may-be-displayed-as-a-string-of-question-marks"></a>エラー メッセージは疑問符の文字列として表示される場合があります。  
 BizTalk Server のローカライズされたビルドでは、エラー メッセージが疑問符の文字列として表示される場合は、予想されるエラー メッセージを受け取るためのオペレーティング システム言語に従ってシステム ロケールを変更する必要があります。 オペレーティング システム (OS) に応じて、具体的な手順が異なりますが、次の手順は、OS のような可能性があります。 
 
 1. 移動して**コントロール パネル** > **時計および地域** > **リージョン**します。
 2. 選択、**管理 タブ** > **の Unicode 以外のプログラムの言語** > **システム ロケール変更**します。
 3. 言語を選択 > **OK** > **OK**変更を保存します。
  
## <a name="see-also"></a>参照  
 [EDI および AS2 ソリューションのトラブルシューティング](../core/troubleshooting-edi-and-as2-solutions.md)   
 [EDI および AS2 状態レポート](../core/edi-and-as2-status-reporting.md)
