---
title: 最低限のセキュリティ ユーザー権限 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, user accounts
- permissions, user accounts
- permissions, roles
- administrator accounts, permissions
- roles, permissions
- permissions, administrator accounts
- user accounts, permissions
- user accounts, access control
- security, permissions
ms.assetid: 44b6e7da-8e6c-40c0-a250-52ab422c0adf
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d42f6a3ad04af27786c3b3379d00bfde12101971
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394428"
---
# <a name="minimum-security-user-rights"></a>最低限のセキュリティ ユーザー権限
グループと BizTalk Server で使用されるアカウントは、ほとんどのタスクの実行に必要な最小限のユーザー権限を持っています。 そのため、タスクがありますの BizTalk Server は自動的に所属するグループを与え、以上のユーザー権利を必要があります。 このトピックの内容  
  
 [グループとロールのメンバーシップ](../core/minimum-security-user-rights.md#BKMK_GroupRole)  
  
 [管理タスクを実行するためのユーザー権限](../core/minimum-security-user-rights.md#BKMK_UserRights)  
  
 [コミュニティによる補足 – タスク一覧](../core/minimum-security-user-rights.md#BKMK_Community)  
  
##  <a name="BKMK_GroupRole"></a> グループとロールのメンバーシップ  
 次の表では、BizTalk Server でタスクを実行する必要がある最低限のセキュリティ ユーザー権限について説明します。  
  
|タスク|グループまたはロール|  
|----------|---------------------|  
|**セットアップ**||  
|インストール|-ローカルの管理者|  
|構成|-BizTalk Server 管理者<br />-ローカルの管理者<br />sysadmin SQL Server ロール<br />SSO 管理者<br />OLAP 管理者|  
|BizTalk Server グループに参加します。|-ローカルの管理者<br />-BizTalk Server 管理者|  
|**BizTalk 管理コンソール**||  
|メッセージ ボックス データベースを作成します。|-BizTalk Server 管理者<br />sysadmin SQL Server ロール|  
|作成または BizTalk ホストを削除します。|-BizTalk Server 管理者<br />-BizTalk メッセージ ボックス データベース上の db_ddladmin SQL Server データベース ロール|  
|ホストのホストの追跡プロパティを変更します。|-BizTalk Server 管理者<br />BAM プライマリ インポート データベース、BizTalk メッセージ ボックス データベース、および BizTalk 追跡データベースの db_securityadmin SQL Server データベース ロール|  
|作成 (インストール)、削除、またはホスト インスタンスの資格情報の変更|<ul><li>BizTalk Server 管理者</li><li>ローカル管理者</li><li>以下のデータベース サーバー上の securityadmin SQL Server ロール:<br /><br /> <ul><li>BizTalk メッセージ ボックス データベース、BizTalk 管理データベース、ルール エンジン データベース、BizTalk 追跡データベース、BAM プライマリ インポート データベース</li></ul></li><li>次のデータベースの db_securityadmin SQL Server データベース ロール:<br /><br /> <ul><li>BizTalk メッセージ ボックス データベース、BizTalk 管理データベース、ルール エンジン データベース、BizTalk 追跡データベース、BAM プライマリ インポート データベース</li></ul></li></ul>|  
|ホスト インスタンス開始または停止|-BizTalk Server 管理者|  
|サーバー追加または削除|-BizTalk Server 管理者<br />のコンピューター上ローカルの管理者を追加または削除します。|  
|追加または受信ハンドラーを削除します。|-BizTalk Server 管理者<br />SSO 関連管理者|  
|開始、アプリケーション、オーケストレーションを停止または送信ポート、および送信ポート グループ|BizTalk Server Operators|  
|受信場所の有効化または無効にします。|BizTalk Server Operators|  
|アイテムの検索|BizTalk Server Operators|  
|アダプターを追加します。|-BizTalk Server 管理者<br />SSO 関連管理者|  
|データベースのバックアップ|のデータベース BTS_BACKUP_USERS ロール<br />-BizTalk 管理データベースをホストする SQL Server の sysadmin SQL Server ロール。 **注:** SQL Server の各インスタンスにマップされたユーザー ドメイン アカウントまたはローカル アカウントで実行する SQL Server エージェント サービスを構成する必要があります。|  
|証明書での BizTalk グループを構成します。|-BizTalk Server 管理者|  
|その他のすべてのタスク (WMI など)|-BizTalk Server 管理者|  
|**操作およびメッセージとサービス インスタンスの追跡**||  
|ビューのグループ ハブ ページの保存クエリの実行し、クエリの読み込み|BizTalk Server Operators|  
|クエリ結果を表示します。|BizTalk Server Operators|  
|一般的な構成および追跡の構成|BizTalk Server 管理者 (読み取りし、書き込み)<br />BizTalk Server オペレーター (読み取り)|  
|稼働状況の監視キューブを参照します。|-BizTalk Server 管理者|  
|メッセージ プロパティの表示|-BizTalk Server 管理者|  
|メッセージ本文を保存します。|-BizTalk Server 管理者|  
|使用**メッセージの検索**クエリ|-BizTalk Server 管理者|  
|使用**ビルドのクエリ**|-BizTalk Server 管理者|  
|オーケストレーション デバッガーを使用します。|-BizTalk Server 管理者|  
|メッセージ フローおよび BizTalk Server 管理コンソールを使用してグループ ハブ ページでメッセージ イベントを表示します。|BizTalk Server Operators|  
|インスタンスの中断または終了すると、|BizTalk Server Operators|  
|アーカイブまたは追跡データベースからメッセージを削除します。|-BizTalk 追跡データベースの db_owner ロール|  
|その他のすべてのタスク|-BizTalk Server 管理者|  
|**追跡プロファイル エディター**||  
|BizTalk 管理データベースに対する読み取りまたは書き込み|-BizTalk Server 管理者|  
|**イベント バスの監視 MMC**||  
|すべてのタスク|-BizTalk Server 管理者|  
|**BizTalk WCF サービス公開ウィザード**||  
|すべてのタスク|-ローカルの管理者|  
|**BizTalk Web サービス公開ウィザード**||  
|すべてのタスク|-ローカルの管理者|  
|**ビジネス アクティビティの監視**||  
|BM.exe を実行します。|BAM プライマリ インポート、BAM スター スキーマ、および BAM アーカイブ データベースの db_owner SQL Server データベース ロール|  
|Analysis Services データベースがある場合、BM.exe を実行します。|BAM プライマリ インポート、BAM スター スキーマ、および BAM アーカイブ データベースの db_owner SQL Server データベース ロール<br />BAM Analysis Services データベースでの OLAP 管理者|  
|BAM ビュー用アカウントを作成します。|BAM プライマリ インポート データベースの db_owner SQL Server データベース ロール<br />BAM Analysis Services データベースでの OLAP 管理者|  
|**ルール エンジン (ルールの公開)**||  
|ポリシーの展開/展開解除、セキュリティに関連する成果物の操作|のルール エンジン データベース RE_ADMIN_USERS SQL Server データベース ロール|  
  
##  <a name="BKMK_UserRights"></a> 管理タスクを実行するためのユーザー権限  
 BizTalk Server 管理コンソールまたは Windows Management Instrumentation (WMI) を使用して、管理タスクを実行するために管理タスクを実行するアカウントは異なるレベルのタスクによってユーザーの権限が必要です。実行します。  
  
 次の表では、ほとんどのユーザー権限 (レベル 4) に最小限のユーザー権限 (レベル 1) から、タスクを実行するアカウントが必要なユーザー権限について説明します。  
  
|ユーザー権限のレベル|許可されるユーザー権限|処理手順|  
|--------------------------|-------------------------|-----------|  
|0|BizTalk Server Operators|-基本的な管理と監視タスク。 構成設定を変更することはできません。 メッセージのプロパティやコンテンツにアクセスできません。|  
|1|-BizTalk Server 管理者|-すべての管理タスクを必要とするものを除く 2 ~ 4 のユーザー権限をレベルします。|  
|2|のレベル 1 に付与されたユーザー権限<br />-すべての SQL Server の securityadmin SQL Server ロール<br />-db_securityadmin ロールおよび db_accessadmin SQL Server データベース ロールで BizTalk の追跡、ルール エンジン、BizTalk 管理、BAM プライマリ インポートおよび BizTalk メッセージ ボックス データベース<br />-すべての BizTalk メッセージ ボックス データベース上の db_ddladmin SQL Server データベース ロール<br />SSO 関連管理者|-作成して、BizTalk ホストの削除<br />ホスト追跡プロパティの変更<br />-追加し、サーバーを削除<br />-追加ハンドラーと受信ハンドラーの削除<br />-アダプターを追加します。|  
|3|のレベル 2 に付与されたユーザー権限<br />のすべての BizTalk Server ランタイム コンピューター上ローカル管理者|-作成およびホスト インスタンスの削除|  
|4|のレベル 3 に付与されたユーザー権限<br />-すべての BizTalk メッセージ ボックス データベースが SQL サーバー上の sysadmin SQL Server ロール|-メッセージ ボックス データベースを作成します。|  
  
##  <a name="BKMK_Community"></a> コミュニティによる補足 – タスク一覧  
 [BizTalk Server 2013 R2 の最低限のセキュリティ権限](http://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2013-r2.aspx)(http://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2013-r2.aspx)  
  
## <a name="see-also"></a>参照  
 [アクセス制御とデータ セキュリティ](../core/access-control-and-data-security.md)   
 [BizTalk Server のシステム アーキテクチャの設計](../core/designing-the-system-architectures-for-biztalk-server.md)   
 [BizTalk Server でのデータベース](../core/databases-in-biztalk-server.md)   
 [BizTalk Server の Windows グループ アカウントとユーザー アカウント](../core/windows-groups-and-user-accounts-in-biztalk-server.md)