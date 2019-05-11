---
title: メッセージのライフ サイクル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 305dc48db684a1e0f0ba37232b672e6ffb63406a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329674"
---
# <a name="lifecycle-of-a-message"></a>メッセージのライフ サイクル
次の図では、メッセージングの観点から、BizTalk Server アーキテクチャの概要を示します。  
  
 ![BizTalk Server メッセージング アーキテクチャ](../core/media/arch-messaging-01.gif "arch_messaging_01")  
  
 この簡略化されたビューでメッセージが特定の受信ポートで定義されている受信場所を介して受信されます。 このメッセージは受信場所で処理され、メッセージ ボックス データベースでは、メインの永続化および BizTalk Server のルーティング メカニズムにパブリッシュします。 メッセージ ボックスは、アクティブなサブスクリプションの評価しそのオーケストレーションにメッセージをルーティングし、サブスクリプションに一致するポートを送信します。 オーケストレーションはメッセージを処理し、プッシュは最終的な送信先に送信ポートにメッセージ ボックスを経由してメッセージを発行する可能性があります。  
  
 BizTalk Server メッセージの処理に関連する主要なコンポーネントを次に示します。  
  
## <a name="receive-ports-and-receive-locations"></a>受信ポートと受信場所  
 A*受信ポート*いずれかのコレクションまたは以上の受信場所を BizTalk Server への特定のエントリ ポイントを定義します。 A*受信場所*メッセージを受信する 1 つのエンドポイント (URL) の構成を示します。 場所には、受信アダプターと受信パイプラインの両方の構成情報が含まれています。 *アダプター*のメッセージの受信トランスポートおよび通信の一部を担当します。 例には、ファイル アダプターと SOAP アダプタは、さまざまな種類のソースからメッセージを受信する各が含まれます。 受信パイプラインは、メッセージをメッセージ ボックス データベースへの発行の準備を行います。 A*パイプライン*一連の暗号化/暗号化解除などのメッセージを特定の処理、解析、または検証を提供するそれぞれのシーケンスで実行されるコンポーネントです。 パイプラインの詳細については、受信ポート、および受信場所を参照してください[成果物](../core/artifacts.md)します。  
  
## <a name="send-ports-and-send-port-groups"></a>送信ポートと送信ポート グループ  
 A*送信ポート*送信パイプラインと送信アダプタの組み合わせです。 送信ポート グループを送信ポートのコレクションは、電子メール配布リストと同様に機能します。 送信ポート グループに送信されるメッセージは、そのグループ内のすべての送信ポートに送信されます。 別のサービスに転送の BizTalk Server から受信メッセージを準備するには、送信パイプラインを使用します。 送信アダプターは、実際には、SOAP や FTP などの特定のプロトコルを使用してメッセージを送信します。 送信ポートおよび送信ポート グループの詳細については、次を参照してください。[成果物](../core/artifacts.md)します。  
  
## <a name="orchestrations"></a>オーケストレーション  
 オーケストレーションのサブスクライブ (受信) することができ、メッセージ ボックス データベースを介して (送信) メッセージを発行します。 さらに、オーケストレーションは、新しいメッセージを構築することができます。 メッセージを受信する、サブスクリプションを使用して、ルーティング機構について説明します。 オーケストレーションのサブスクリプションがいっぱいになるの新しいインスタンスがアクティブ化し、メッセージを配信すると、必要に応じてインスタンスのサブスクリプションの場合、インスタンスがリハイド レートや、メッセージが配信されます。 オーケストレーションから送信されたメッセージに発行されます、メッセージ ボックスに同様に、適切なプロパティを持つ受信場所に到着するメッセージがルーティングで使用するためのデータベースに挿入されるとします。 オーケストレーションの詳細については、次を参照してください。[成果物](../core/artifacts.md)します。  
  
## <a name="messagebox-database"></a>メッセージ ボックス データベース  
 BizTalk Server での発行/サブスクライブ エンジンの中核は、メッセージ ボックス データベースです。 2 つのコンポーネントのメッセージ ボックス データベースから成る: 1 つまたは複数の Microsoft SQL Server データベースとメッセージ エージェント。 SQL Server データベースでは、多くのメッセージ、メッセージのプロパティ、サブスクリプション、オーケストレーションの状態、追跡データ、ルーティングのためのホスト キューなどの永続化ストアを提供します。 メッセージ ボックス データベースの詳細については、次を参照してください。 [、メッセージ ボックス データベース](../core/the-messagebox-database.md)します。  
  
## <a name="hosts-and-host-instances"></a>ホストとホスト インスタンス  
 A*ホスト*などの BizTalk Server アイテムを実行する Microsoft Windows プロセスの論理表現として送信ポートやオーケストレーションです。 A*ホスト インスタンス*特定のサーバー上のホストの物理表現です。 ホストが所有し、BizTalk Server によって管理されていることを意味のインプロセス ホスト、または分離ホストで、BizTalk Server によって制御されていないプロセスで BizTalk Server コードが実行されていることを意味のいずれかを使用できます。 分離ホストの良い例では、HTTP および SOAP アダプターの受信機能をホストするインターネット インフォメーション サービス (IIS) です。 。 BizTalk Server グループ全体のホストが定義されています。構成、メッセージ ボックス、ポート、およびなどを共有する BizTalk サーバーのコレクション。 ホストとホスト インスタンスの詳細については、次を参照してください。[エンティティ](../core/entities.md)します。  
  
## <a name="saving-a-message-body"></a>メッセージ本文を保存しています  
 メッセージ本文を保存する 3 つの方法はあります。  
  
### <a name="from-the-admin-mmc-group-hub-page-queries"></a>管理 MMC のグループ ハブ ページのクエリから  
 この方法は、メッセージ ボックス データベースにのみメッセージです。  
  
-   サービス インスタンスを表示します。  
  
-   開く、**サービス インスタンスの詳細** ダイアログ ボックス。  
  
-   をクリックして、**メッセージ タブ**このインスタンスに関連付けられたメッセージの一覧を表示します。  
  
-   メッセージを右クリックし、をクリックし、**保存**します。  
  
     - または -  
  
-   メッセージをダブルクリックして開くことで、**メッセージ ビューアー**、 をクリック**保存**します。  
  
### <a name="from-the-operations-om"></a>Operations オブジェクト モデルから  
  
-   使用**GetInstance**サービス インスタンス オブジェクトを取得します。  
  
-   使用**Instance.Messages**サービス インスタンスで現在参照されているすべてのメッセージを列挙します。  
  
-   など、メッセージ オブジェクトでメソッドを使用して**Message.BodyPart**と**Message.Context**をアクセスし、保存します。  
  
### <a name="from-the-dta"></a>DTA から  
  
-   使用して、DTA からメッセージを取得、 **GetTrackedInstance**と**GetTrackedmessage** API 呼び出し。  
  
## <a name="see-also"></a>参照  
 [ランタイム アーキテクチャ](../core/runtime-architecture.md)