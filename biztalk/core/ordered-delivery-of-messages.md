---
title: メッセージの配信を順序付けられた |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- backing up, message order
- file transport, message order
- Messaging Engine, transports
- messages, performance
- dynamic send ports, message order
- BTS.SuspendAsNonResumable message context property
- performance, message order
- Messaging Engine, performance
- Messaging Engine, message order
- MessageBox database, message order
- messages, sorting
- backing up, backup transports
- adapters, custom receive adapters
- adapters, messages
- customizing, receive adapters
ms.assetid: 39e0bba6-81f5-4ae0-af92-837b225bc801
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6068d3d4e84389022a07d315b808b7005b95a88c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262597"
---
# <a name="ordered-delivery-of-messages"></a>メッセージの順次配送
メッセージの順次配送とは、特定の順序でメッセージ ボックス データベースに公開されたメッセージを、それぞれ対応するサブスクライバーに (メッセージ ボックスに公開されたときと同じ順序で) 配送することです。  
  
## <a name="configuring-ordered-message-delivery"></a>メッセージの順次配送の構成  
 メッセージの順次配送は、次の場所で構成できます。  
  
-   **受信**のオーケストレーションの図形  
  
-   送信ポート  
  
## <a name="ordered-delivery-with-existing-transports"></a>既存のトランスポートでの順次配送  
 トランスポートに使用されるプロトコルによっては、特に順次配送が必要ないものもあります (FILE や HTTP など)。 ただし、このようなトランスポートの場合でもポートにバインドする場合、トランスポートが順次配送は、対象としてマークし、BizTalk Server では、順次配送を強制により、エントリの現在の 1 つが正常に送信されるまで、トランスポートは、[次へ] の送信メッセージが取得できません. この機能を実現するために、BizTalk Server は、各メッセージを 1 つのバッチとしてトランスポートのアダプターに渡し、アダプターがそのメッセージをメッセージ ボックスから削除するまで待機してから、次のメッセージを別のバッチとしてアダプターに配送します。  
  
### <a name="ordered-delivery-for-custom-adapters"></a>カスタム アダプターでの順次配送  
 カスタムの受信アダプターでは、特別に考慮しなければならない事柄があります。 順次配送をサポートするカスタム アダプターは、次のことを実行する必要があります。  
  
- カスタムの受信メッセージのバッチを送信した後にアダプターが待機する必要があります、 **BatchComplete**次のバッチを送信する前に、BizTalk Server からのコールバック。 詳細については、次を参照してください。 [Batch-Supported の受信アダプター用のインターフェイス](../core/interfaces-for-a-batch-supported-receive-adapter.md)します。  
  
- メッセージの処理がパイプラインで失敗した場合、そのメッセージを保留 (できれば再開不可に) する必要があります。 使用して、 **BTS します。SuspendAsNonResumable**メッセージ コンテキスト プロパティ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]にメッセージを適切にフラグを設定します。  
  
> [!NOTE]
>  保留したメッセージが後で再開されると、メッセージの順序が破綻してしまいます。 このような事態を避けるためには、失敗したメッセージを再開不可として保留します。  
  
 カスタム アダプター作成の詳細については、次を参照してください。[カスタム アダプターの開発](../core/developing-custom-adapters.md)します。  
  
## <a name="conditions-for-end-to-end-ordered-message-processing"></a>エンド ツー エンドの順次メッセージ処理を実現するための条件  
 エンド ツー エンドの順次配送を実現するには、次の条件を満たす必要があります。  
  
- メッセージは、BizTalk Server に送信するメッセージの順序を保持できるアダプターで受信されなければなりません。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] には、この条件を満たすアダプターとして、MSMQ および MQSeries があります。 HTTP アダプターまたは SOAP アダプターを使用して、メッセージを順次配送することもできますが、その場合は、HTTP クライアントまたは SOAP クライアント側で、正しい順序が維持されるよう配慮する必要があります (メッセージを 1 つずつ送信する)。  
  
- これらのメッセージを持つ送信ポートをサブスクライブする必要があります、**順次配送**オプションに設定されて`True`します。  
  
- プロセスがメッセージをオーケストレーションのインスタンスが 1 つだけを使用する必要がありますにオーケストレーションを使用する場合、オーケストレーションを構成して、シーケンシャルなコンボイを使用する必要がある、**順次配送**のプロパティ、オーケストレーションの受信ポートに設定する必要があります`True`します。  
  
## <a name="restrictions"></a>制限  
 メッセージの順次配送は、次のサポートされていません。  
  
- 動的送信ポート[!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)]と以前のバージョン

- 動的送信ポート[!INCLUDE[bts2016_md](../includes/bts2016-md.md)](および以降のバージョン) のアダプターの種類を**しない**順次配送の静的送信ポートのサポート
  
- バックアップ トランスポート  

  
## <a name="interactions"></a>他の設定との関係  
 送信ポートに対して順次配送を構成する場合、他の設定との関係に注意する必要があります。  
  
-   同じ送信ポートの "現在のメッセージが失敗したときに、後続のメッセージの送信を停止する" 設定  
  
    -   **False です。** 失敗したメッセージだけが (再開不可として) 保留にされ、以降のすべてのメッセージは引き続き処理されます。 これにより、失敗しなかったメッセージの順序は維持されますが、元の順序に抜けが生じることになります。 たとえば、101、102、103 という順序で受信され、102 が保留状態になった場合、101 と 103 については正しい順番で処理されます。  
  
    -   **True です。** いずれかのメッセージで処理が失敗した場合、送信ポートのインスタンスが保留状態になります。 これにより、順次配送の設定された、後続のすべてのメッセージが保留されます。 後続のメッセージが、失敗したメッセージよりも前に配送されることはないため、メッセージの順序は完全に維持されます。  
  
-   送信請求 - 応答の送信ポートで、"現在のメッセージが失敗したときに、後続のメッセージの送信を停止する" プロパティが `true` に設定され、応答の受信パイプラインの逆アセンブル ステージで復旧可能な交換処理が構成されていた場合、応答を逆アセンブルしているときに復旧可能なエラーが発生したとしても、送信ポートはメッセージの送信を中断しません (つまり、インスタンスは保留状態になりません)。  
  
-   順次配送の設定された送信ポートを削除する場合は、関連付けられたインスタンスが存在しないことを確認しておく必要があります。 関連付けられたインスタンスが存在する場合は、それを終了させてから、送信ポートを削除します。  
  
## <a name="ordered-delivery-to-file-transport"></a>ファイル トランスポートへの順次配送  
 ファイル アダプターには、メッセージが順に到着します。 ファイル アダプターでは、メッセージを単一のファイルに追加していくか、個別のファイルとして書き出します。  
  
-   メッセージ データが単一のファイルに追加される場合、各メッセージは順番に追加されていきます。 ファイル アダプターを使用する送信ポートの順次配送オプションは、送信トランスポートが追加モードで動作している場合にのみ機能します。  
  
-   メッセージが個別のファイルに出力される場合、その順番がファイル名に反映されます。つまり、到着した順番に基づいてファイル名が付けられます。 このとき、アダプターによって書き込まれたファイルでは、時系列 (ファイルの作成日時や更新時刻など) に関するファイル システムのプロパティには、メッセージが到着した順序は反映されません。  
  
## <a name="performance-impact-of-ordered-delivery"></a>順次配送がパフォーマンスに与える影響  
 BizTalk Server は、順次配送を実現するために、メッセージ経路のさまざまな地点において、メッセージを順番どおりに処理する必要があります。 そのため、複数のホスト インスタンスを使用して、メッセージを並列処理するなどのスケール アウト手段が通用しなくなります。 順次配送を行う場合、複数のホスト インスタンスで動作するように構成されたポートであっても、複数のホスト インスタンスで実行させることはできません。順次配送を行うには、単一のホスト インスタンスで動作させる必要があるためです。 ただし、複数のホスト インスタンスの場合でも、高い可用性のメリットは享受できます。メッセージの順次配送を処理するホスト インスタンスで障害が発生した場合、処理に失敗したメッセージは利用可能な別のホスト インスタンスで再処理されます。  
  
 順次配送が有効な場合、既定値**再試行間隔**は 5 分です。 パフォーマンスを向上させるには、[再試行の間隔] を最小値 (1 分) に設定します。 **再試行間隔**プロパティがゼロ (0) の値を受け入れることがありますが、ゼロ (0) が無効です。 **再試行の回数**も必要な回数を調整できます。 たとえば、リクエストを 1 分以内に処理する必要があり、送信ポート送信先がいつでもアクセスできる場合は、両方の値を 1 に設定します。  
  
 再試行の値を変更するには[送信ポートのトランスポート詳細設定オプションの構成方法](http://go.microsoft.com/fwlink/p/?LinkID=267697)します。  
  
 順次配送の詳細については、次の情報を参照してください。  
  
 [BizTalk:エンド ツー エンドの順次メッセージ処理オプション](http://social.technet.microsoft.com/wiki/contents/articles/12887.biztalk-end-to-end-ordered-message-processing-options.aspx)  
  
 [BizTalk:順次配送](http://social.technet.microsoft.com/wiki/contents/articles/6681.biztalk-ordered-delivery.aspx)  
  
## <a name="see-also"></a>参照  
 [MSMQ アダプターでメッセージの配信を順序付け](../core/ordered-delivery-of-messages-with-the-msmq-adapter.md)   
 [MQSeries アダプターを使用したメッセージの順次配送](../core/ordered-delivery-of-messages-with-the-mqseries-adapter.md)