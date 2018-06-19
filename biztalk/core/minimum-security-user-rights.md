---
title: セキュリティの最小ユーザー権限 |Microsoft ドキュメント
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
ms.openlocfilehash: 4ad405afd1f69b4499b8c4650586411957a2ca3c
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2018
ms.locfileid: "22265586"
---
# <a name="minimum-security-user-rights"></a>セキュリティの最小ユーザー権限
グループと BizTalk Server で使用するアカウントは、ほとんどのタスクを実行する必要がある最小ユーザー権限を持っています。 タスクによっては、所属しているグループに対し BizTalk Server で自動的に許可されている以外のユーザー権限が必要になる場合もあります。 このトピックの内容:  
  
 [グループとロールのメンバーシップ](../core/minimum-security-user-rights.md#BKMK_GroupRole)  
  
 [管理タスクを実行するためのユーザー権利](../core/minimum-security-user-rights.md#BKMK_UserRights)  
  
 [コミュニティによる補足 – タスク一覧](../core/minimum-security-user-rights.md#BKMK_Community)  
  
##  <a name="BKMK_GroupRole"></a> グループとロールのメンバーシップ  
 次の表では、BizTalk Server でのタスクを実行する必要があります。 最小セキュリティ ユーザー権限について説明します。  
  
|タスク|グループまたはロール|  
|----------|---------------------|  
|**セットアップ**||  
|インストール|-ローカル管理者|  
|構成|BizTalk Server 管理者<br />-ローカル管理者<br />sysadmin SQL Server ロール<br />-SSO 管理者<br />OLAP 管理者|  
|BizTalk Server グループへの参加|-ローカル管理者<br />BizTalk Server 管理者|  
|**BizTalk 管理コンソール**||  
|メッセージ ボックス データベースの作成|BizTalk Server 管理者<br />sysadmin SQL Server ロール|  
|BizTalk ホストの作成または削除|BizTalk Server 管理者<br />-BizTalk メッセージ ボックス データベース上の db_ddladmin SQL Server データベース ロール|  
|ホストの "ホストの追跡" プロパティの変更|BizTalk Server 管理者<br />BAM プライマリ インポート データベース、BizTalk メッセージ ボックス データベースおよび BizTalk 追跡データベースの db_securityadmin SQL Server データベース ロール|  
|ホスト インスタンス用の資格情報の作成 (インストール)、削除、変更|<ul><li>BizTalk Server 管理者</li><li>ローカル管理者</li><li>次のデータベースがあるサーバー上の securityadmin SQL Server ロール<br /><br /> <ul><li>BizTalk メッセージ ボックス データベース、BizTalk 管理データベース、ルール エンジン データベース、BizTalk 追跡データベース、BAM プライマリ インポート データベース</li></ul></li><li>次のデータベースの db_securityadmin SQL Server データベース ロール<br /><br /> <ul><li>BizTalk メッセージ ボックス データベース、BizTalk 管理データベース、ルール エンジン データベース、BizTalk 追跡データベース、BAM プライマリ インポート データベース</li></ul></li></ul>|  
|ホスト インスタンスの開始または停止|BizTalk Server 管理者|  
|サーバーの追加または削除|BizTalk Server 管理者<br />のコンピューター上ローカルの管理者を追加または削除します。|  
|受信ハンドラーの追加または削除|BizTalk Server 管理者<br />-SSO 関連管理者|  
|アプリケーション、オーケストレーション、送信ポート、および送信ポート グループの開始と停止|BizTalk Server Operators|  
|受信場所の有効化または無効化|BizTalk Server Operators|  
|アイテムの検索|BizTalk Server Operators|  
|アダプターの追加|BizTalk Server 管理者<br />-SSO 関連管理者|  
|データベースのバックアップ|のデータベース BTS_BACKUP_USERS ロール<br />BizTalk 管理データベースをホストする SQL Server の sysadmin SQL Server ロール。 **注:**  SQL Server の各インスタンスにマップされたユーザー ドメイン アカウントまたはローカル アカウントで実行する SQL Server エージェント サービスを構成する必要があります。|  
|BizTalk グループへの証明書の構成|BizTalk Server 管理者|  
|他のすべてのタスク (WMI など)|BizTalk Server 管理者|  
|**操作およびメッセージとサービス インスタンスの追跡**||  
|[グループ ハブ] ページの表示と、クエリの実行、保存、ロード|BizTalk Server Operators|  
|クエリ結果の表示|BizTalk Server Operators|  
|全般の構成および追跡の構成|BizTalk Server 管理者 (読み取りし、書き込み)<br />BizTalk Server オペレーター (読み取り)|  
|稼働状況の監視キューブの参照|BizTalk Server 管理者|  
|メッセージ プロパティの表示|BizTalk Server 管理者|  
|メッセージ本文を保存します。|BizTalk Server 管理者|  
|使用 **メッセージの検索** クエリ|BizTalk Server 管理者|  
|使用 **ビルドの照会**|BizTalk Server 管理者|  
|オーケストレーション デバッガーの使用|BizTalk Server 管理者|  
|BizTalk Server 管理コンソールを使用した [グループ ハブ] ページでのメッセージ フローおよびメッセージ イベントの表示|BizTalk Server Operators|  
|インスタンスの中断、終了、再開|BizTalk Server Operators|  
|追跡データベースのメッセージのアーカイブおよび削除|BizTalk 追跡データベースの db_owner ロール|  
|他のすべてのタスク|BizTalk Server 管理者|  
|**追跡プロファイル エディター**||  
|BizTalk 管理データベースの読み取りまたは書き込み|BizTalk Server 管理者|  
|**イベント バスの監視 MMC**||  
|すべてのタスク|BizTalk Server 管理者|  
|**BizTalk WCF サービス公開ウィザード**||  
|すべてのタスク|-ローカル管理者|  
|**BizTalk Web サービス公開ウィザード**||  
|すべてのタスク|-ローカル管理者|  
|**ビジネス アクティビティの監視**||  
|BM.exe の実行|BAM プライマリ インポート、BAM スター スキーマ、および BAM アーカイブ データベースの db_owner SQL Server データベース ロール|  
|BM.exe の実行 (Analysis Services データベースがある場合)|BAM プライマリ インポート、BAM スター スキーマ、および BAM アーカイブ データベースの db_owner SQL Server データベース ロール<br />BAM Analysis Services データベースの OLAP 管理者|  
|BAM ビュー用アカウントの作成|BAM プライマリ インポート データベースの db_owner SQL Server データベース ロール<br />BAM Analysis Services データベースの OLAP 管理者|  
|**ルール エンジン (ルールの公開)**||  
|ポリシーの展開および展開解除、セキュリティ関連アイテムの操作|のルール エンジン データベース RE_ADMIN_USERS SQL Server データベース ロール|  
  
##  <a name="BKMK_UserRights"></a> 管理タスクを実行するためのユーザー権利  
 BizTalk Server 管理コンソールまたは Windows Management Instrumentation (WMI) を使用して管理タスクを実行するには、管理タスクを実行するアカウントで、実行タスクごとに異なるレベルのユーザー権限が必要になります。  
  
 次の表で、最小のユーザー権限 (レベル 1) から最大のユーザー権限 (レベル 4) までのタスクを実行する際にアカウントで必要になるユーザー権限について説明します。  
  
|ユーザー権限のレベル|許可されるユーザー権限|処理手順|  
|--------------------------|-------------------------|-----------|  
|0|BizTalk Server Operators|-基本的な管理および監視作業します。 構成設定は変更できません。 メッセージ プロパティおよびメッセージの内容にはアクセスできません。|  
|1|BizTalk Server 管理者|-すべての管理タスクを必要とするものを除く 2 ~ 4 ユーザー権限をレベルします。|  
|2|のレベル 1 に付与されたユーザー権限<br />-すべての SQL Server の securityadmin SQL Server ロール<br />-db_securityadmin ロールおよび db_accessadmin SQL Server データベース ロールで、BizTalk 追跡、ルール エンジン、BizTalk 管理、BAM プライマリ インポート データベースおよび BizTalk メッセージ ボックス データベース<br />-すべての BizTalk メッセージ ボックス データベース上の db_ddladmin SQL Server データベース ロール<br />-SSO 関連管理者|-作成し、BizTalk ホストの削除<br />ホスト追跡プロパティの変更<br />追加し、サーバーの削除<br />追加し、受信ハンドラーの削除<br />-アダプターを追加します。|  
|3|のレベル 2 に付与されたユーザー権限<br />のすべての BizTalk Server ランタイム コンピューター上ローカルの管理者|-作成し、ホスト インスタンスを削除|  
|4|のレベル 3 に付与されたユーザー権限<br />-すべての BizTalk メッセージ ボックス データベースがある SQL サーバー上の sysadmin SQL Server ロール|-メッセージ ボックス データベースを作成します。|  
  
##  <a name="BKMK_Community"></a> コミュニティによる補足 – タスク一覧  
 [BizTalk Server 2013 R2 の最低限のセキュリティ権限](http://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2013-r2.aspx)(http://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2013-r2.aspx)  
  
## <a name="see-also"></a>参照  
 [アクセス制御とデータ セキュリティ](../core/access-control-and-data-security.md)   
 [BizTalk Server のシステム アーキテクチャの設計](../core/designing-the-system-architectures-for-biztalk-server.md)   
 [BizTalk Server でのデータベース](../core/databases-in-biztalk-server.md)   
 [BizTalk Server の Windows グループ アカウントとユーザー アカウント](../core/windows-groups-and-user-accounts-in-biztalk-server.md)