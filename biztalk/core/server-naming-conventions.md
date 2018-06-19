---
title: サーバーの名前付け規則 |Microsoft ドキュメント
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
ms.openlocfilehash: 4a54e61a9ec37754158697a57a3f310d9edb90ff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22273202"
---
# <a name="server-naming-conventions"></a>サーバーの名前付け規則
BizTalk Server の展開のシステム アーキテクチャに関する詳細については、次を参照してください。[サンプル BizTalk Server アーキテクチャ](../core/sample-biztalk-server-architectures.md)です。  
  
 次の表は、トピックの「ダイアグラム内のサーバー[大規模な分散アーキテクチャ](../core/large-distributed-architecture.md)、とその機能します。  
  
|図中のサーバー名|関数|Description|  
|----------------------------|--------------|-----------------|  
|FW4|ファイアウォール|インターネットと境界ネットワークの間での forefront Threat Management Gateway (TMG) 2010 サーバーです。|  
|HTTP (受信)|Web サーバー|HTTP アダプター用のメッセージを受信する Web サーバーです。 このサーバーには、BizTalk Server コンポーネントがインストールされておらず、メッセージをサービス インターフェイス ドメインに中継する ASP.NET ページがあります。 FW 4 から FW 3 までは、ASP.NET ページではなくリバース プロキシを使用できます。 リバース プロキシを使用する場合、このサーバーは必要ありません。|  
|Exchange (送信/受信)|[メール サーバー]|BizTalk Server で SMTP メッセージの送信および受信に使用するメール サーバーです。 POP3 アダプターが受信メッセージを読み取ります。|  
|FTP (送信/受信)|Web サーバー|BizTalk のメッセージの送信元および受信元となるファイル転送プロトコル (FTP) サーバーを表します。 このサーバーはリモート サーバーにすることができます。|  
|SQL|SQL Server|SQL アダプターで使用される SQL Server データベースを含むサーバーです。|  
|ファイル|ファイル サーバー|サービス インターフェイス ドメイン内のファイル アダプターがファイルを削除および取得するファイル ディレクトリがあるサーバーです。|  
|FW3|ファイアウォール|サービスを保護する forefront Threat Management Gateway (TMG) 2010 サーバー インターフェイス ドメインを境界ネットワークおよび企業ドメイン。|  
|処理|処理サーバー|このサーバーでは、メッセージを処理します。 このサーバーには、BizTalk Server ランタイム、ビジネス ルール エンジン、およびエンタープライズ シングル サインオン (SSO) サービスが含まれています。 BizTalk アセンブリ、ホスト インスタンス、オーケストレーション、スキーマ、およびマップはこのサーバー上にあります。 指定した処理サーバーには、さまざまなホストのホスト インスタンスを配置できます。|  
|[受信ハンドラー]<br /><br /> (分離ホスト)|受信/送信サーバー|HTTP アダプターおよび SOAP アダプターから着信するメッセージの受信のみを行う BizTalk Server です。 指定した受信/送信サーバーには、さまざまなホストのホスト インスタンスを配置できます。|  
|[受信ハンドラー]<br /><br /> (インプロセス ホスト)|受信/送信サーバー|SQL アダプター、FTP アダプター、EDI アダプター、ファイル アダプター、POP3 アダプター、および BizTalk メッセージ キュー アダプターからのメッセージの受信のみを行う BizTalk Server です。 指定した受信/送信サーバーには、さまざまなホストのホスト インスタンスを配置できます。|  
|送信ハンドラー|受信/送信サーバー|すべてのアダプターへのメッセージ送信のみを行う BizTalk Server です。 指定したサーバーには、メッセージの送信に使用するさまざまなホストのホスト インスタンスを配置できます。|  
|FW2|ファイアウォール|サービス インターフェイス ドメインおよび企業ドメイン (運用サービス) からサービス ドメインを保護する forefront Threat Management Gateway (TMG) 2010 サーバー|  
|追跡ホスト|追跡サーバー|追跡に使用する、BizTalk ホストのホスト インスタンスがあるサーバーです。|  
|管理ツール|管理サーバー|BizTalk Server ランタイム、BizTalk Server 管理コンソール、および展開ツールがあるサーバーです。|  
|[マスター シークレット サーバー]|[マスター シークレット サーバー]|環境全体のマスター シークレット キーを管理する SSO サーバーです。 このコンピューターには、他の BizTalk Server コンポーネントがありません。|  
|FW1|ファイアウォール|データ ドメインをサービス インターフェイス ドメインおよびサービス ドメインを保護する forefront Threat Management Gateway (TMG) 2010 サーバーです。|  
|メッセージ ボックス 1<br /><br /> メッセージ ボックス 2<br /><br /> メッセージ ボックス 'n'|データ サーバー|メッセージ ボックス データベースが配置された SQL Server です。 メッセージ ボックス データベースごとに異なる SQL Server を使用できます。|  
|SSO|データ サーバー|SSO データベースが配置された SQL Server です。このデータベースは、他のシステムにログオンする際のユーザー ID と資格情報を暗号化形式で格納する場合や BizTalk Server で使用するアダプターの構成情報を暗号化形式で格納する場合に、エンタープライズ シングル サインオンによって使用されます。|  
|ログ配布のためのバックアップ/復元|データ サーバー|BizTalk Server データベースによって生成されたデータベース バックアップを復元するために使用される SQL Server です。|  
|BizTalk 分析|データ サーバー|BizTalk 分析データベースが配置された分析サーバーです。|  
  
 次の表は、トピックの図は、他のサーバー[インフォメーション ワーカー サービスで大規模な分散アーキテクチャ](../core/large-distributed-architecture-with-information-worker-services.md)とトピックの図と比較してその機能[大分散アーキテクチャ](../core/large-distributed-architecture.md)です。  
  
|サーバー名|関数|Description|  
|-----------------|--------------|-----------------|  
|BAM ポータル|BAM ポータル|BAM ポータルが配置されたサーバーです。 ビジネス エンド ユーザーは、BAM ポータルを使用して BAM データベースにアクセスし、主要業績評価指標 (KPI) およびビジネス プロセスに関するその他の情報を監視します。|  
|通知サービス<br /><br /> Windows SharePoint Services の構成<br /><br /> Windows SharePoint Services コンテンツ<br /><br /> BAM スター スキーマ<br /><br /> BAM プライマリ インポート<br /><br /> BAM アーカイブ<br /><br /> BAM 分析 (OLAP)|IW データ サーバー|ビジネス アクティビティ監視で使用されるデータベースが入った SQL Server です。 これらのデータベースには複数の SQL Server を使用できます。|  
|IW クライアント|IW クライアント|インフォメーション ワーカーがビジネス アクティビティ監視に使用するクライアント コンピューターです。|  
  
## <a name="see-also"></a>参照  
 [大規模な分散アーキテクチャ](../core/large-distributed-architecture.md)   
 [インフォメーション ワーカー サービスで大規模な分散アーキテクチャ](../core/large-distributed-architecture-with-information-worker-services.md)   
 [BizTalk Server のサンプル アーキテクチャ](../core/sample-biztalk-server-architectures.md)