---
title: EDI バッチ処理に関する既知の問題 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 510ac82b-8a02-4135-87b7-0a5f288f5317
caps.latest.revision: 38
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9941e6f88bc7bd23a9825a1960a2dcf9f92466f9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330402"
---
# <a name="known-issues-with-edi-batching"></a>EDI バッチ処理に関する既知の問題
このトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のバッチ処理に関する既知の問題について説明します。  
  
## <a name="subdocument-splitting-was-not-performed-even-though-the-subdocument-annotation-was-set-to-yes"></a>サブドキュメントの注釈が [はい] に設定されていても、サブドキュメントの分割が実行されない  
 **現象**  
  
 HIPAA インターチェンジの HIPAA スキーマ内で、subdocument_creation_break 注釈が [はい] に設定されていても、HIPAA インターチェンジがサブドキュメントに分割されません。  
  
 **考えられる原因**  
  
- 受信バッチ処理、送信元パーティのオプションは、「インターチェンジの保存」に設定されました この場合、HIPAA スキーマ内の subdocument_creation_break 注釈が [はい] に設定されていても、HIPAA ドキュメントはサブドキュメントに分割されません。  
  
- subdocument_break 注釈は [はい] に設定されていますが、subdocument_creation_break 注釈は [はい] に設定されていません。  
  
  **解決方法**  
  
- **検証と確認の生成の設定**のページ、 **EDI のプロパティ** ダイアログ ボックス、送信元パーティの設定、**受信バッチ処理**プロパティをオプションいずれか**エラーのトランザクション セットを中断するトランザクション セットとして分割されたインターチェンジ**または**エラーでインターチェンジを中断するトランザクション セットとして分割されたインターチェンジ**します。  
  
- subdocument_creation_break 注釈を [はい] に設定しない場合、HIPAA ドキュメントはサブドキュメントに分割されません。  
  
## <a name="validation-of-a-batch-may-fail-if-batch-configuration-settings-are-changed-while-the-batch-orchestration-is-activated"></a>バッチ オーケストレーションがアクティブになっているときに、バッチの構成設定を変更すると、バッチの検証に失敗する場合がある  
 バッチ処理オーケストレーションがバッチを処理している間にバッチの構成設定を変更した場合、そのバッチに対して新しい構成設定は適用されません。 これにより、送信パイプラインで検証エラーが発生する場合があります。  
  
 これらの設定は、[EDI のプロパティ] ダイアログ ボックスの [バッチ] ページにあります。  
  
 この問題を解決するには、バッチ処理オーケストレーションに関連付けられたホスト インスタンスを再起動します。 これにより、バッチの構成設定の変更が直ちに適用されます。  
  
## <a name="the-batchcontrolmessagerecvloc-receive-location-can-only-run-on-a-32-bit-computer-or-in-wow-on-a-64-bit-computer"></a>BatchControlMessageRecvLoc 受信場所を実行できるのが、32 ビット コンピューター、または 64 ビット コンピューターの WOW のみである  
 SQL アダプターが機能するのは、32 ビット コンピューターで実行する場合、または 64 ビット コンピューター上の WOW64 エミュレーターで実行する場合のみです。 そのため、セットアップ プログラムによってインストールされ、SQL アダプターを使用する BatchControlMessageRecvLoc 受信場所が機能するのは、32 ビット コンピューターで実行する場合、または 64 ビット コンピューター上の WOW で実行する場合のみです。 この受信場所はバッチ処理に必要です。  
  
 64 ビット コンピューター上の WOW で BatchControlMessageRecvLoc 受信場所を実行する場合は、バッチ処理オーケストレーションを別のホストで実行する必要があります。 受信場所と同じホストで実行すると、バッチ処理オーケストレーションが WOW でも実行されるため、64 ビット コンピューターで実行する利点がなくなります。  
  
## <a name="a-batch-can-be-picked-up-by-an-unintended-send-port"></a>予期しない送信ポートによってバッチが取得される  
 バッチ処理オーケストレーションがインターチェンジを公開すると、2 つのプロパティを昇格します。ToBeBatched = False と DestinationPartyName = \< *PartyName*\>します。 これらのプロパティの一方または両方をサブスクライブする送信ポートは、これらのバッチ インターチェンジを取得できます。 送信ポートがこれらの取得対象のバッチ インターチェンジを取得するよう、送信ポートのフィルターを必ず構成してください。  
  
## <a name="a-batch-element-count-greater-than-the-required-number-of-transaction-sets-for-a-batch-may-not-prompt-batch-release"></a>バッチ要素数がバッチに必要なトランザクション セット数より多い場合に、バッチがリリースされないことがある  
 バッチのリリース条件が、グループまたはインターチェンジごとのトランザクション セット数に基づいている場合は、バッチ要素数が、リリースされるバッチに必要なトランザクション セット数より多くても、バッチがリリースされないことがあります。 これは、受信確認を有効にしており、その受信確認をバッチに追加するようにバッチのフィルター条件を設定している場合に発生します。 この場合、グループ (またはインターチェンジ) 内のバッチ要素数は、グループ (またはインターチェンジ) ごとのトランザクション セット数より多くなります。 その場合は、グループ (またはインターチェンジ) ごとのトランザクション セット数がバッチ リリースに必要な数より少なければ、バッチがリリースされませんが、同時に、バッチ要素数がバッチ リリースに必要なトランザクション セット数よりも多くなります。  
  
## <a name="no-batch-elements-were-saved-when-start-was-clicked"></a>[開始] をクリックしたときにバッチ要素が保存されない  
 **現象**  
  
 ときに**開始**がクリックされたパーティのバッチ ページで、メッセージが収集されません、バッチ用。  
  
 **考えられる原因**  
  
 日時が**開始**がクリックされたで入力した日時より前のバージョンでした、**アクティベーション**セクション。 その結果、オーケストレーション インスタンスがアクティブ化が、バッチのメッセージが収集されません。 詳細については、次を参照してください。[送信バッチの構成](../core/configuring-an-outgoing-batch.md)します。  
  
 **解決方法**  
  
 クリックして**停止**この問題が発生しているバッチ構成のバッチ ページでします。 設定、**アクティベーション**いずれかに**をすぐに開始**または現在の時刻より前の日時を入力し、クリックして**開始**します。 リセットするメッセージが表示されたら、**開始**をクリックして現在の時刻を datetime **[ok]** します。 BizTalk Server は、その時点でバッチ用のメッセージの収集を開始します。  
  
## <a name="the-number-of-bytes-in-an-edifact-batch-may-depend-upon-the-character-set-used"></a>EDIFACT バッチのバイト数が、使用される文字セットによって異なる  
 一部の EDIFACT 文字セットで 2 バイト文字である文字が、他の EDIFACT 文字セットでは 1 バイト文字である場合があります。 そのため、インターチェンジ内の文字数に基づいてバッチのリリース条件を設定するときは、使用する文字セットによってインターチェンジ内のバイト数が異なることがあります。  
  
## <a name="the-characters--and--must-be-represented-in-their-encoded-form-in-the-envelope-of-a-batch"></a>バッチのエンベロープで、文字 "<" と "&" をエンコード形式で表す必要がある  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、バッチ EDI インターチェンジのエンベロープ フィールドを作成する場合に、リテラル形式の "<" と "&" をサポートしません。  
  
 送信バッチ インターチェンジのエンベロープ フィールドで、これらの文字のいずれかをそのまま使用すると、インターチェンジのシリアル化に EdiSend パイプラインが使用されている場合にメッセージが中断されます。  
  
 バッチのエンベロープ フィールドでこれらの文字の 1 つを使用する必要がある場合は、BizTalk 管理でエンベロープ フィールドを構成するときに、次の表の適切なエンコード値を使用できます。  
  
|文字|[エンコード]|  
|---------------|--------------|  
|<|&lt;|  
|&|&amp;|  
  
 これらのエンコード形式の 1 つを使用すると、BizTalk Server 管理コンソールのパートナー アグリーメント マネージャー (PAM) 画面で、BizTalk Server が長さの制限についてフィールドを検証する場合に、エンコード形式の各文字が個別の文字と見なされます。 たとえば、場合でも、エンコード"&lt;「1 つの文字を表現は」\<"、バッチ EDI インターチェンジで BizTalk Server としてカウントされますこの 4 つの文字の特定のフィールドの長さの制限を検証するとき. これは PAM のみの問題であり、EDI アセンブラーには該当しません。  
  
## <a name="an-exeption-occurs-during-the-execution-of-the-upgrade-batch-orchestration"></a>アップグレード バッチ オーケストレーションの実行中に例外が発生する  
 **現象**  
  
 受信ドキュメントで EDI.DestinationPartyId プロパティを設定するカスタム パイプライン コンポーネントを使用する場合、アプリケーション イベント ログで、アップグレード バッチ オーケストレーションの実行中に例外が発生したことを示すエラーが受信されることがあります。  
  
 **考えられる原因**  
  
 ErrorMessage が "バッチが見つかりませんでした" である場合、このエラーは、アップグレード バッチ オーケストレーションで受信ドキュメント用のバッチを適切に識別できなかったことを示します。  
  
 **解決方法**  
  
 アップグレード バッチ オーケストレーションでは、EDI.DestinationPartyId を使用してパーティ名を参照します。 その後、パーティ名、EDI.EncodingType、および文字列 “Default” を使用して文字列を構築し、一致するバッチ名のバッチ構成を検索します。 この名前のバッチ構成が存在しない場合、このエラーがアプリケーション イベント ログに記録され、オーケストレーション インスタンスが中断されます。  
  
> [!NOTE]
>  たとえば、パーティ名が Contoso で、EDI.EncodingType が X12 である場合、オーケストレーションでは "ContosoX12Default" という名前のバッチを検索します。  
  
 この問題を解決するには、アップグレード バッチ オーケストレーションによって構築された文字列に一致する名前のバッチが存在することを確認します。  
  
## <a name="messages-marked-with-editobebatched--true-and-edidestinationparties-are-suspended"></a>EDI.ToBeBatched = True および EDI.DestinationParties でマークされたメッセージが中断される  
 **現象**  
  
 カスタム パイプライン コンポーネントを使用して、EDI.ToBeBatched に True を設定し、EDI.DestinationParties にパーティ ID のリストを設定することによりメッセージにバッチ用のマーキングを行う場合、メッセージはサブスクライバーが存在しないことを示すルーティング エラーにより中断されます。  
  
 **考えられる原因**  
  
 以前のバージョンの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、メッセージを複数のバッチ構成で処理する必要がある場合、パーティ ID のスペース区切りリストを EDI.DestinationParties プロパティに設定していました。 ルーティング オーケストレーションは、EDI.ToBeBatched が True に設定され、EDI.DestinationParties プロパティを持つメッセージをサブスクライブし、EDI.DestinationParties プロパティに含まれるパーティ ID のリストを使用して各 ID 用のメッセージを作成し、メッセージをバッチ オーケストレーションに渡していました。  パーティ ID を使用してバッチを判断していたのは、各パーティ構成が保持できるバッチ構成が 1 つだけだったからです。  
  
 BizTalk Server で、各パーティはパーティ ID のみを使用して、使用するバッチ構成を決定するための十分なができなくなったために複数のバッチ構成を持つことができます。  メッセージを複数のバッチ構成で処理する必要があることを示すには、メッセージの EDI.BatchIDs プロパティに、メッセージの送信先であるバッチ ID のスペース区切りリストを設定する必要があります。  
  
> [!NOTE]
>  EDI.DestinationPartyId プロパティを使用して単一のパーティ ID のみによりマークされたメッセージを処理すると、メッセージはアップグレード バッチ オーケストレーションによって処理されます。 詳細については、次を参照してください。[バッチ EDI インターチェンジをアセンブル](../core/assembling-a-batched-edi-interchange.md)します。  
  
 **解決方法**  
  
 EDI.DestinationParties プロパティではなく EDI.BatchIDs プロパティを設定するようにカスタム パイプライン コンポーネントをアップグレードします。  特定のバッチのバッチ ID は、各パーティの EDI プロパティの [バッチ] 設定ページで確認できます。  
  
> [!NOTE]
>  この問題は、BatchMarker パイプライン コンポーネントを使用してメッセージにバッチ用のマーキングを行う場合は発生しません。  
  
## <a name="batch-filter-refresh-timeout-is-hardcoded-to-fifteen-minutes"></a>バッチ フィルター更新タイムアウトが 15 分にハードコーディングされている  
 バッチ フィルター条件を変更した場合、変更が有効になるまで 15 分かかります。 この更新間隔は変更できません。 フィルターをすぐに有効にするには、BizTalk Server ホスト プロセスを再起動します。  
  
## <a name="the-routingorchestration-suspends-after-reporting-an-uncaught-exception"></a>不明な例外を報告した後に RoutingOrchestration が中断される  
 **現象**  
  
 複数のバッチ構成に送信されるドキュメントを処理する場合、XLANG/s からアプリケーション イベント ログに、不明な例外により Microsoft.BizTalk.Edi.RoutingOrchestration.BatchRoutingService で障害が発生したというエラーが送信されることがあります。  
  
 **考えられる原因**  
  
 このエラーは、RoutingOrchestration が BatchingOrchestration にメッセージを送信したときに、BatchingOrchestration インスタンスが起動していなかった場合に発生する可能性があります。  
  
 **解決方法**  
  
 バッチ処理するドキュメントを送信する前に、BatchingOrchestration インスタンスが実行されていることを確認します。  
  
## <a name="many-active-batches-may-cause-the-biztalkmsgboxdb-logfile-to-grow-large"></a>多数のアクティブ バッチにより、BizTalkMsgBoxDb ログファイルが大きくなることがある  
 **現象**  
  
 複数のバッチを開始した後で、BizTalk メッセージ ボックス データベース (BizTalkMsgBoxDb) のトランザクション ログのサイズが大きくなることがあります。  
  
 **考えられる原因**  
  
 この問題は、バッチ リリースの間隔を短くするリリース条件 (たとえば、バッチを 1 分ごとにリリースする) で大量のバッチを開始した場合に発生する可能性があります。  
  
 バッチを開始したときに作成されるバッチ オーケストレーション インスタンスは、実行時間の長いプロセスであり、バッチのリリース後にデータベースに保持されます。 オーケストレーションが保持されるたびに、保持に含まれるトランザクションにより、トランザクション ログのサイズが大きくなります。  
  
> [!NOTE]
>  バッチ オーケストレーションが保持されている間に、トランザクション ログは約 30 KB 大きくなります。  
  
 **解決方法**  
  
 この問題を解決するには、バッチ リリースの間隔が長くなるようにリリース条件を変更します。 詳細については、次を参照してください。 [(X12) をバッチ処理構成](../core/configuring-batching-x12.md)します。  
  
## <a name="see-also"></a>参照  
 [EDI 受信確認の構成](../core/configuring-edi-acknowledgments.md)   
 [受信バッチの処理](../core/processing-incoming-batches.md)   
 [送信 EDI メッセージをバッチ処理](../core/batching-outgoing-edi-messages.md)   
 [EDI バッチの構成](../core/configuring-edi-batches.md)