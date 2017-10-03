---
title: "追跡を拡張 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: tracking
ms.assetid: 8adf78f0-ab0f-44d4-aa5b-9546e2bdf01f
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6660cf8f783a407c3ddead342effecfb4cdd0201
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="enhanced-tracking"></a>拡張追跡
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]プロセスとメッセージを追跡するために、拡張機能を提供します。 ネイティブな機能のビジネス アクティビティ監視 (BAM) で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]はメタデータのみを追跡します。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]追跡メッセージの内容、service content とヘッダーの両方です。  
  
 次の表に、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] が行うデータ追跡のすべての範囲を示します。 ここでは、プロセスおよびメッセージの追跡について説明します。 否認不可データの詳細については、次を参照してください。 [RNIF メッセージの処理](../../adapters-and-accelerators/accelerator-rosettanet/rnif-message-processing.md)です。  
  
|追跡される情報|機能|ユーザー アクセス|  
|-------------------------|-------------|-----------------|  
|RosettaNet のプロセスとメッセージの追跡|メタデータ (データベース テーブルとデータのビュー) は BAM 経由、メッセージ本文は専用インターフェイス経由|BAM ユーザー インターフェイスまたはカスタム ユーザー インターフェイス|  
|エラーとイベント|[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] のイベント ログ経由|イベント ログ|  
|否認不可データ|ワイヤ形式のメッセージが保存されている専用インターフェイス経由|[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]Archive データベースの MessageStorageIn と MessageStorageOut テーブル、および SDK 経由|  
  
## <a name="process-and-message-tracking"></a>プロセスとメッセージの追跡  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] は、プロセス アクティビティとメッセージ アクティビティの 2 つの基本的なアクティビティを追跡します。 プロセス アクティビティは、public-process オーケストレーションのメッセージ処理を追跡します。 メッセージ アクティビティは、送信パイプラインと受信パイプラインにおけるメッセージ処理を追跡します。  
  
 プロセス アクティビティは、メッセージ メタデータ全体を追跡します。 メッセージ アクティビティは、プロセス アクティビティ メタデータとメッセージの内容を追跡します。  
  
### <a name="process-activity"></a>プロセス アクティビティ  
 パブリック プロセス オーケストレーション (開始側または応答側) がインスタンス化されるたびに、パブリック プロセスは、BAM 追跡データベースにプロセス アクティビティ レコードを作成します。 オーケストレーションは、パブリック プロセスの各地点で追跡メタデータを保存します。 オーケストレーションが停止すると、プロセス アクティビティも停止します。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] は、次の 2 つのインスタンスにおけるプロセスのメタデータ全体を追跡します。  
  
-   [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] が応答側で、要求アクション メッセージを受信する場合  
  
-   [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] が開始側で、基幹業務 (LOB) アプリケーションから要求メッセージを受信する場合  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] がメッセージを送受信するたびに、パブリック プロセスはプロセス アクティビティの状態を更新します。  
  
### <a name="message-activity"></a>メッセージ アクティビティ  
 メッセージ アクティビティは、送信パイプラインと受信パイプライン経由でメッセージを追跡します。 送信パイプラインまたは受信パイプラインがメッセージを処理するたびに、パイプラインはメッセージ アクティビティを作成します。 パイプラインは、BAM 追跡データベースとのメッセージのレコードにメッセージ アクティビティ レコードを作成、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]アーカイブ データベースです。  
  
 メッセージ アクティビティは、Service Content とヘッダーを含めたメッセージの内容を保存します。 受信パイプラインで MIME デコーダーの処理が成功すると、アクティビティはメッセージの内容の 4 つの部分を、MessageContent テーブルの [ContentXml] 列にテキスト形式の XML として保存します。 MIME デコーダーの処理が失敗すると、アクティビティはメッセージの内容を MessageContent テーブルの [ContentBinary] 列にバイナリ形式で保存します。  
  
### <a name="use-of-tracking-data-in-correlation"></a>関連付けにおける追跡データの使用  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] は、特定の PIP について、交換されたすべてのメッセージに各プロセスを関連付けるための情報を追跡します (正または負のシグナル、要求と応答のシグナル)。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] が PIP に対してエラー通知を送信すると、0A1 メッセージを関連付けるために使用されている情報も追跡します。 PIP インスタンス ID、開始側パーティ名、相手側パーティ名の組み合わせにより、アクティビティに関連付けられたメッセージが決まります。  
  
### <a name="tracking-databases"></a>追跡データベース  
 プロセス アクティビティとメッセージ アクティビティは、追跡したメタデータを BAMPrimaryImport [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] データベースに保存します。 このデータベースでは、"bam_Process" というプレフィックスで始まる名前のテーブルにはプロセス アクティビティ追跡データが格納され、"bam_Message" というプレフィックスで始まる名前のテーブルにはメッセージ アクティビティ追跡データが格納されます。 各プロセス アクティビティまたはメッセージ アクティビティのテーブルには、対応するレコードが 1 つあります。 この 2 つのアクティビティとメタデータの追跡に関する情報は、"bam_Metadata" というプレフィックスで始まる名前のメタデータ テーブルに含まれています。  
  
 BAMPrimaryImport 追跡データベースのデータは、次のビューを使って使用できます。 これらおよび他のビューで使用可能な[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]のノード、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]管理コンソールです。  
  
|追跡ビュー|data|  
|-------------------|----------|  
|bam_Process_AllInstances|PIP によって定義された RosettaNet プロセスの状態|  
|bam_Message_AllInstances|すべてのメッセージの状態|  
|bam_Process_CompletedInstances|完了したプロセスの状態|  
  
 メッセージ アクティビティは、メッセージの内容を [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]Archive データベースの MessageContent テーブルに保存します。 メッセージの内容は、メッセージの一意の識別子を使用して MessageContent テーブルにクエリを実行すると確認できます。 このアクティビティは、"bam_Message" というプレフィックスを使用して、メッセージ アクティビティ追跡テーブルの ContentKey 列に一意の識別子を保存します。  
  
> [!IMPORTANT]
>  メッセージ アクティビティは、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]Archive データベースの MessageContent テーブルでメッセージの内容をクリア テキストで共有します。 これは、メッセージが暗号化されたり、署名されるシナリオを含むすべての追跡シナリオで発生します。 メッセージの内容へのアクセスを懸念する場合は、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]Archive データベースへのアクセスを制限できます。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] は、BAM 追跡 API を使用して追跡データを保存します。  
  
### <a name="status-codes"></a>状態コード  
 BAMPrimaryImport データベースの bam_Process_Active と bam_Process_Completed テーブルには、プロセスの状態を示す Status 列があります。 次の表は、各状態コードの値を示しています。  
  
|状態コード|プロセスの状態|  
|-----------------|-------------------|  
|-1000|ActivityNotPresentFatalError|  
|-500|UnexpectedFatalError|  
|-100|Initiated0A1|  
|-99|TerminatedOnError<br /> (終了 0A1 による終了)|  
|-85|TerminatedBy0A1|  
|-75|TimedOutOnResponseSignal|  
|-50|TimedOutOnResponse|  
|-25|TimedOutOnActionSignal|  
|0|RegisteredActivity|  
|1|ActivityToBeInitiated|  
|10|ReceivedAction または SentAction|  
|25|ReceivedActionSignal または SentActionSignal|  
|35|ReceivedActionSignal2 または SentActionSignal2<br /> (信号 2 は、RNIF v11 向けのものです)|  
|50|ReceivedResponse または SentResponse|  
|75|ReceivedResponseSignal または SentResponseSignal|  
|85|ReceivedResponseSignal2 または SentResponseSignal2<br /> (信号 2 は、RNIF v11 向けのものです)|  
|100|ActivityCompleted|  
  
### <a name="activity-definition-file"></a>アクティビティ定義ファイル  
 アクティビティ定義ファイルでは、BAM で追跡するフィールドおよびその表示方法を定義します。 このファイルの詳細については、次を参照してください。[追跡アクティビティ定義ファイルの操作](../../adapters-and-accelerators/accelerator-rosettanet/working-with-the-tracking-activity-definition-file.md)です。  
  
 BAM の詳細については、[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] ヘルプの「ビジネス アクティビティ監視 (BAM)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [追跡アクティビティ定義ファイルの操作](../../adapters-and-accelerators/accelerator-rosettanet/working-with-the-tracking-activity-definition-file.md)   
 [BizTalk Server に BizTalk Accelerator for RosettaNet の追加](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md)