---
title: BizTalk Server のホスティング環境を作成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- hosting environments, creating
- managing [hosts], hosting environments
- hosts, environments
- managing [hosts], creating
- creating, hosting environment
ms.assetid: 6f335139-1121-45ff-88da-5c626b8fff97
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de4183a91d2e10eaaefd2f6298a66b05b74eb9c3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340117"
---
# <a name="how-to-create-a-biztalk-server-hosting-environment"></a>BizTalk Server のホスティング環境を作成する方法
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のホスティング環境を作成する前に、次の推奨事項を考慮してください。  

- **信頼できる、信頼されていないオーケストレーションの別のホストを使用してハンドラーと受信ハンドラー**  

   ホストで実行されているすべての項目 (オーケストレーション、パイプライン、受信ハンドラーと送信ハンドラーなど) は同じ ID で実行され、そのホストの作業キューおよび保留キューにアクセスできます。  

   アクセス許可のエラーによって、メッセージをオーケストレーションに配信できない場合、このメッセージは、送信プロセス (受信パイプラインまたは別のオーケストレーション) が実行されているホストの保留キューに格納されます。 ただし、オーケストレーションおよび送信プロセス (受信パイプラインなど) は同じホストで実行され、オーケストレーションでは引き続き保留キューのメッセージにアクセスできます。 これにより、信頼されていないオーケストレーションが信頼済みホストで実行されている場合、システムが危険にさらされる可能性があります。  

   信頼されていないオーケストレーションの実行は、BizTalk グループの信頼済みホストとは異なるサービス アカウントを使用して、独立したホストで行うことをお勧めします。 信頼できる場合は、「」を参照としてホストを指定する方法について[ホスト プロパティを変更する方法](../core/how-to-modify-host-properties.md)します。  

- **BizTalk Server データベースでデータベースとログのサイズを制限します。**  

   BizTalk メッセージ ボックス データベースおよび BizTalk 追跡データベースのサイズは、他の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースよりもはるかに高速に増大します。 バックアップ プログラムおよびメンテナンス プログラムの一環として、これらのデータベースを頻繁に更新する必要があります。  

   既定では、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースのテーブルにはログ サイズの制限がありません。 バックアップ プログラムおよびメンテナンス プログラムの一環として、ログ サイズを制限することで、ログが大きくなりすぎないようにし、ディスク領域が占有されないようにすることをお勧めします。 追跡データベースのサイズを管理する方法の詳細については、次を参照してください。[アーカイブおよび BizTalk 追跡データベースの削除](../core/archiving-and-purging-the-biztalk-tracking-database.md)します。  

- **SQL Server クラスタ リングを使用して、**  

   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースの高可用性を実現するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースが格納されている SQL Server をクラスター化することをお勧めします。 クラスター化すると、データベースの 1 つまたは SQL Server が失敗した場合のダウンタイムを、最小限に抑えることができます。 SQL Server クラスタリングの詳細については、SQL Server Books Online の「フェールオーバー クラスタリングのアーキテクチャ」を参照してください。  

## <a name="prerequisites"></a>前提条件  
 次に、このトピックの手順を実行するための前提条件を示します。  

- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。  

- 以下の手順の指示では、完全インストール オプションを使用して [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をインストールしたことを前提としています。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を完全インストール オプションでインストールしていない場合は、手順 1. で一覧表示される管理オブジェクトの一部がシステムに存在しない可能性があります。  

### <a name="to-create-a-biztalk-server-hosting-environment"></a>BizTalk Server のホスティング環境を作成するには  

1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 構成を使用して新しい BizTalk グループを作成します。 新しいを作成する方法については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループを参照してください[、BizTalk Server 構成を使用して構成するグループ](http://msdn.microsoft.com/library/16beb7bb-091c-4056-8622-cc79c95186e9)します。  

    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 構成により、次の管理オブジェクトが作成されます。  


   |                   管理オブジェクト                    |                                                                                                                                                                                                                                       説明                                                                                                                                                                                                                                       |
   |------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |      **BizTalk 管理**データベース (BizTalkMgmtDb)       |                                                                                                                                                                    このデータベースには、すべての [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のメタ情報が集中的に保存されます。                                                                                                                                                                     |
   |     **BizTalk メッセージ ボックス**データベース (BizTalkMsgBoxDb)      |           このデータベースには、サブスクリプションの述語が格納されます。 このデータベースはホスト プラットフォームであり、各 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ホストのキューおよび状態テーブルが保持されます。 また、メッセージ ボックス データベースには、メッセージおよびメッセージ プロパティが格納されます。 メッセージ ボックス データベースについては、追加のメッセージ ボックス データベースを追加するを参照してください[メッセージ ボックス データベースを管理する](../core/managing-messagebox-databases.md)します。           |
   |                         **[サーバー]**                         | このコンピューターには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] がインストールおよび構成され、ホスト インスタンスが実行されます。 サーバーで作成されたホストから、ホスト インスタンスを作成します。 ホストの作成の詳細については、次を参照してください。[新しいホストを作成する方法](../core/how-to-create-a-new-host.md)します。 ホスト インスタンスを作成する方法の詳細については、次を参照してください。[ホスト インスタンスを追加する方法](../core/how-to-add-a-host-instance.md)します。 |
   |     **BAM プライマリ インポート**データベース (BAMPrimaryImport)     |                                                                                                                                                                                                このデータベースには、ビジネス アクティビティ監視ツールによって追跡データが収集されます。                                                                                                                                                                                                 |
   |       **ルール エンジン**データベース (BizTalkRuleEngineDb)       |                                                                                                                                                                                       このデータベースは、ポリシー、ルール、およびボキャブラリのリポジトリです。ビジネス ルールのデータ参照に使用されます。                                                                                                                                                                                        |
   |        **BizTalk 追跡**データベース (BizTalkDTADb)        |                                                                                                                                                       このデータベースには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 追跡エンジンで追跡したビジネス データおよび稼働状況の監視データが格納されます。                                                                                                                                                       |
   |                  **SSO**データベース (SSODB)                  |                                                                                                                                                                                                                      このデータベースには、資格情報が格納されます。                                                                                                                                                                                                                       |
   |   **インプロセス ホスト**に対応するホスト インスタンス    |                                                                                                                                                                        インプロセス ホストは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のプロセス領域内で機能します。                                                                                                                                                                        |
   |    **分離ホスト**に対応するホスト インスタンス     |                                                                                                                                                                       分離ホストは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] インストールの外部で機能します。                                                                                                                                                                        |
   | HTTP/S、BizTalk メッセージ キュー、ファイル、SMTP、SOAP、および SQL |                                                                                                                                                                   構成ウィザードで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の一部であるアダプターを作成します。                                                                                                                                                                    |


2. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールまたは WMI を使用して、必要に応じて [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境にコンポーネントを追加します。 ソリューションをスケール アウトするには、メッセージ ボックス データベース、ホスト、およびサーバーを追加します。  

3. BizTalk 管理コンソールまたは WMI を使用して、マップされたサーバーにホスト インスタンスを作成します。 この手順では、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を実行するサーバーを決定します。 企業内のニーズの変化に応じて、サーバーの追加、サーバーの削除、サーバーからホストへのマッピングの変更を行えます。  

## <a name="see-also"></a>参照  
 [BizTalk ホストとホスト インスタンスの管理](../core/managing-biztalk-hosts-and-host-instances.md)   
 [ホスト](../core/hosts.md)   
 [ホスト インスタンス](../core/host-instances.md)