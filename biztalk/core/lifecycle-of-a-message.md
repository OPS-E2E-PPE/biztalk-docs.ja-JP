---
title: "メッセージのライフ サイクル |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, MessageBox database
- messages, orchestrations
- messages, host instances
- messages, receive locations
- send ports, about send ports
- processing, messages
- messages, processing
- host instances, about host instances
- receive locations, about receive locations
- hosts, about hosts
- messages, lifecycle
- MessageBox database, about MessageBox database
- receive ports, about receive ports
- send port groups, about send port groups
- messages, hosts
- messages, send port groups
- messages, receive ports
- orchestrations, about orchestrations
- messages, send ports
ms.assetid: d2374f86-9b5f-404f-ba7b-9cab69873fa8
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e05aca3ec819fb8615552c5ed57114032d7ea60b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="lifecycle-of-a-message"></a>メッセージのライフサイクル
次の図は、メッセージングという観点から捉えた BizTalk Server アーキテクチャの概要を示しています。  
  
 ![BizTalk Server メッセージング アーキテクチャ](../core/media/arch-messaging-01.gif "arch_messaging_01")  
  
 この簡単な図でいえば、メッセージは特定の受信ポートの定義された受信場所を介して受信されます。 このメッセージは、受信場所によって処理され、BizTalk Server で永続化およびルーティングを行うメインのメカニズムであるメッセージ ボックス データベースに公開されます。 メッセージ ボックスはアクティブなサブスクリプションを評価し、一致するサブスクリプションのあるオーケストレーションおよび送信ポートにメッセージをルーティングします。 メッセージがオーケストレーションによって処理され、メッセージ ボックスを経由して送信ポートにメッセージが公開されて、そこから最終的な送信先に転送される場合もあります。  
  
 BizTalk Server メッセージ処理に関連する主要なコンポーネントは次のとおりです。  
  
## <a name="receive-ports-and-receive-locations"></a>受信ポートと受信場所  
 A*受信ポート*は、1 つのコレクションまたは以上の受信場所を BizTalk Server に特定のエントリ ポイントを定義します。 A*受信場所*単一のエンドポイント (URL) の構成は、メッセージを受信します。 受信場所には、受信アダプターと受信パイプラインの両方に関する設定情報が含まれています。 *アダプター*は、メッセージの受信のトランスポートおよび通信の一部を担当します。 たとえば、ファイル アダプターや SOAP アダプターなどがあり、それぞれさまざまな種類のソースからメッセージを受信します。 受信パイプラインは、メッセージ ボックスにメッセージを公開する準備を行います。 A*パイプライン*する一連の暗号化/暗号化解除などのメッセージを特定の処理、解析、または検証を提供する各シーケンスで実行されるコンポーネントです。 パイプラインの詳細については、受信ポート、および受信場所を参照してください[成果物](../core/artifacts.md)です。  
  
## <a name="send-ports-and-send-port-groups"></a>送信ポートと送信ポート グループ  
 A*送信ポート*は、送信パイプラインと送信アダプターの組み合わせです。 送信ポート グループは送信ポートの集まりであり、電子メール配信リストのように機能します。 送信ポート グループに送信されたメッセージは、そのグループ内のすべての送信ポートに送信されます。 送信パイプラインを使用して、BizTalk Server から受信したメッセージを、他のサービスに送信する準備を行います。 送信アダプターは、SOAP や FTP のような特定のプロトコルを使用して、実際にメッセージを送信します。 送信ポートおよび送信ポート グループの詳細については、次を参照してください。[成果物](../core/artifacts.md)です。  
  
## <a name="orchestrations"></a>オーケストレーション  
 オーケストレーションは、メッセージ ボックスを使用してメッセージをサブスクライブ (受信) および公開 (送信) できます。 また、オーケストレーションは新しいメッセージを構築することもできます。 メッセージは、前述のサブスクリプションおよびルーティング機構を使用して受信されます。 オーケストレーションに対応するサブスクリプションが到着すると、新しいインスタンスがアクティブ化され、メッセージが配信されます。インスタンス サブスクリプションの場合は、必要に応じてインスタンスが復元されてメッセージが配信されます。 オーケストレーションから送信されたメッセージに公開されたメッセージ ボックスに同様の適切なプロパティの受信場所で到着したメッセージがルーティングで使用するデータベースに挿入されるとします。 オーケストレーションの詳細については、次を参照してください。[成果物](../core/artifacts.md)です。  
  
## <a name="messagebox-database"></a>メッセージ ボックス データベース  
 BizTalk Server の公開/サブスクライブ エンジンの中心となるのは、メッセージ ボックス データベースです。 2 つのコンポーネントのメッセージ ボックス データベースから成る: 1 つまたは複数の Microsoft SQL Server データベースとメッセージ エージェントです。 SQL Server データベースは、メッセージ、メッセージ プロパティ、サブスクリプション、オーケストレーションの状態、追跡データ、ルーティングのためのホスト キューなどの多くの要素に永続的なストアを提供します。 メッセージ ボックス データベースの詳細については、次を参照してください。 [、メッセージ ボックス データベース](../core/the-messagebox-database.md)です。  
  
## <a name="hosts-and-host-instances"></a>ホストとホスト インスタンス  
 A*ホスト*はポートやオーケストレーションなどの BizTalk Server アイテムを実行する Microsoft Windows プロセスの論理表現が送信されます。 A*ホスト インスタンス*特定のサーバー上のホストの物理的な表現です。 ホストには、インプロセス ホストと分離ホストがあります。インプロセス ホストとは、BizTalk Server が所有、管理していることを意味します。分離ホストとは、BizTalk Server が制御していないプロセスで BizTalk Server コードが実行されることを意味します。 分離ホストの代表的な例として、インターネット インフォメーション サービス (IIS) があります。このサービスでは、HTTP アダプターと SOAP アダプターの受信機能をホストします。 ホストは BizTalk Server グループ全体、すなわち設定、メッセージ ボックス、ポートなどを共有する BizTalk Server の集まりに対して定義されます。 ホストとホスト インスタンスの詳細については、次を参照してください。[エンティティ](../core/entities.md)です。  
  
## <a name="saving-a-message-body"></a>メッセージ本文の保存  
 メッセージ本文を保存する方法は 3 つあります。  
  
### <a name="from-the-admin-mmc-group-hub-page-queries"></a>管理 MMC の [グループ ハブ] ページのクエリから  
 この方法は、メッセージ ボックス データベース内のメッセージ専用です。  
  
-   サービス インスタンスを表示します。  
  
-   開く、**サービス インスタンスの詳細** ダイアログ ボックス。  
  
-   クリックして、**メッセージ タブ**をこのインスタンスに関連付けられているメッセージの一覧を表示します。  
  
-   いずれかのメッセージを右クリックし、をクリックして**保存**です。  
  
     -または-  
  
-   メッセージをダブルクリックして開くことで、**メッセージ ビューアー**、 をクリック**保存**です。  
  
### <a name="from-the-operations-om"></a>操作オブジェクト モデルから  
  
-   使用して**GetInstance**サービス インスタンス オブジェクトを取得します。  
  
-   使用して**Instance.Messages [**サービス インスタンスで現在参照されているすべてのメッセージを列挙します。  
  
-   メソッドを使用し、メッセージ オブジェクトなど**Message.BodyPart**と**Message.Context**にアクセスし、保存します。  
  
### <a name="from-the-dta"></a>DTA から  
  
-   使用して、DTA からメッセージを取得、 **GetTrackedInstance**と**GetTrackedmessage** API 呼び出し。  
  
## <a name="see-also"></a>参照  
 [ランタイム アーキテクチャ](../core/runtime-architecture.md)