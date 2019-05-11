---
title: サーバーの名前付け規則 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, naming conventions
- naming conventions, servers
- installation, naming conventions
ms.assetid: 98989c15-51d7-4a67-b054-abe6993a98a6
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a727ca9c817c182055ba6a6580d02f394bdceba7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393317"
---
# <a name="server-naming-conventions"></a>サーバーの名前付け規則
BizTalk Server の展開のシステム アーキテクチャの詳細については、次を参照してください。 [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md)します。  
  
 次の表に、このトピックの図内のサーバー[大規模な分散アーキテクチャ](../core/large-distributed-architecture.md)とその機能。  
  
|ダイアグラム内のサーバー名|関数|説明|  
|----------------------------|--------------|-----------------|  
|FW4|ファイアウォール|インターネットと境界ネットワークの間の forefront Threat Management Gateway (TMG) 2010 サーバーです。|  
|HTTP (受信)|Web サーバー|HTTP アダプターのメッセージを受信する web サーバー。 このサーバーには、インストールされている BizTalk Server コンポーネントはありません。サービス インターフェイス ドメインにメッセージを中継する ASP.NET ページがあります。 リバース プロキシを FW 4 から FW 3 までは、ASP.NET ページではなく使用できます。 リバース プロキシを使用する場合、このサーバーは必要ありません。|  
|Exchange (送信/受信)|メール サーバー|メール サーバーの SMTP メッセージを送受信する BizTalk Server を使用します。 POP3 アダプターは、受信したメッセージを読み取る|  
|FTP (送信/受信)|Web サーバー|BizTalk の送信とメッセージの受信元のファイル転送プロトコル (FTP) サーバーを表します。 これは、リモート サーバーを使用できます。|  
|SQL|SQL Server|サーバーは、SQL アダプターによって使用される SQL Server データベース。|  
|ファイル|ファイル サーバー|ファイル アダプターは、サービス インターフェイス ドメインを元のファイル ディレクトリが含まれるサーバーは、削除し、ファイルを取得します。|  
|FW3|ファイアウォール|サービスを保護する forefront Threat Management Gateway (TMG) 2010 サーバーのドメインおよび企業ドメイン境界ネットワークからインターフェイスします。|  
|処理|処理サーバー|このサーバーは、メッセージを処理します。 BizTalk Server ランタイム、ビジネス ルール エンジン、およびエンタープライズ シングル サインオン (SSO) サービスがあります。 BizTalk アセンブリ、ホスト インスタンス、オーケストレーション、スキーマ、およびマップは、このサーバーには。 特定の処理サーバーでは、さまざまなホストのホスト インスタンスを配置できます。|  
|[受信ハンドラー]<br /><br /> (分離ホスト)|受信/送信サーバー|BizTalk Server は、HTTP および SOAP アダプターからメッセージを受信する専用。 指定された受信/送信サーバー別のホストのホスト インスタンスことができます。|  
|[受信ハンドラー]<br /><br /> (インプロセス ホスト)|受信/送信サーバー|BizTalk Server は、SQL、FTP、EDI、ファイル、POP3 および BizTalk メッセージ キュー アダプターからメッセージを受信する専用。 指定された受信/送信サーバー別のホストのホスト インスタンスことができます。|  
|送信ハンドラー|受信/送信サーバー|BizTalk Server では、すべてのアダプターのメッセージの送信を専用。 特定のサーバーには、メッセージの送信に使用する別のホストのホスト インスタンスを配置できます。|  
|FW2|ファイアウォール|サービス インターフェイス ドメインおよび企業ドメイン (運用サービスです。) からサービス ドメインを保護する forefront Threat Management Gateway (TMG) 2010 サーバー|  
|ホストの追跡|追跡サーバー|追跡のために使用する BizTalk ホストのホスト インスタンスがあるサーバー。|  
|管理ツール|管理サーバー|サーバーは、BizTalk Server ランタイム、BizTalk Server 管理コンソール、および展開ツールです。|  
|[マスター シークレット サーバー]|[マスター シークレット サーバー]|環境全体のマスター シークレット キーを管理する SSO サーバーです。 このコンピューターには、他の BizTalk Server コンポーネントはありません。|  
|FW1|ファイアウォール|データ ドメインと、サービス インターフェイス ドメインおよびサービス ドメインを保護する forefront Threat Management Gateway (TMG) 2010 サーバーです。|  
|メッセージ ボックス 1<br /><br /> メッセージ ボックス 2<br /><br /> メッセージ ボックス 'n' 日前|データ サーバー|SQL Server メッセージ ボックス データベースを含むです。 各メッセージ ボックス データベースを別の SQL Server があることができます。|  
|SSO|データ サーバー|エンタープライズ シングル サインオンを使用して暗号化された形式のユーザー Id と資格情報と BizTalk Server で使用するアダプターの構成情報フォームに暗号化された形式で格納するため、他のシステムにログオンするために格納する SSO データベースを含む SQL Server.|  
|ログ配布のバックアップ/復元|データ サーバー|SQL Server が BizTalk Server データベースによって生成されたデータベース バックアップを復元するために使用します。|  
|BizTalk 分析|データ サーバー|BizTalk 分析データベースを含む分析サーバー。|  
  
 次の表に、このトピックの図に追加のサーバー[インフォメーション ワーカー サービスでの大規模な分散アーキテクチャ](../core/large-distributed-architecture-with-information-worker-services.md)とその機能をこのトピックの図と比較して[大分散アーキテクチャ](../core/large-distributed-architecture.md)します。  
  
|サーバー名|関数|説明|  
|-----------------|--------------|-----------------|  
|BAM ポータル|BAM ポータル|BAM ポータルを含むサーバーです。 ビジネス エンドユーザーは、BAM ポータルを使用して、主要業績評価指標 (Kpi) と、ビジネス プロセスに関するその他の情報を監視する BAM データベースにアクセスします。|  
|通知サービス<br /><br /> Windows SharePoint Services の構成<br /><br /> Windows SharePoint Services のコンテンツ<br /><br /> BAM スター スキーマ<br /><br /> BAM プライマリ インポート<br /><br /> BAM アーカイブ<br /><br /> BAM 分析 (OLAP)|IW データ サーバー|SQL Server ビジネス アクティビティ監視で使用されるデータベースを含むです。 これらのデータベースの複数の SQL Server を使用することができます。|  
|IW クライアント|IW クライアント|インフォメーション ワーカーがビジネス アクティビティを監視するために使用するクライアント コンピューター。|  
  
## <a name="see-also"></a>参照  
 [大規模な分散アーキテクチャ](../core/large-distributed-architecture.md)   
 [インフォメーション ワーカー サービスで大規模な分散アーキテクチャ](../core/large-distributed-architecture-with-information-worker-services.md)   
 [BizTalk Server のサンプル アーキテクチャ](../core/sample-biztalk-server-architectures.md)