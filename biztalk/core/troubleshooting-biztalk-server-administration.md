---
title: BizTalk Server 管理のトラブルシューティング |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9dfb56b0-352f-4012-b030-087bbcfe09d4
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 573e7a2509741748b0f95837f310e2e651b255c9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25975080"
---
# <a name="troubleshooting-biztalk-server-administration"></a>BizTalk Server 管理のトラブルシューティング
このセクションでは、BizTalk Server 管理コンソールの使用時に発生する一般的な問題に関する情報をまとめて提供します。  
  
 次の既知の問題、に加えて[一般的な問題と解決策を BizTalk Server 管理コンソール](http://social.technet.microsoft.com/wiki/contents/articles/common-issues-and-resolutions-with-the-biztalk-server-administration-console.aspx)追加情報を提供します。  
  
## <a name="known-issues"></a>既知の問題  
  
#### <a name="delay-in-entsso-service-prevents-biztalk-server-service-from-starting"></a>ENTSSO サービスの遅れのため、BizTalk Server サービスが開始されない  
  
##### <a name="problem"></a>問題  
 DTC を使用したコンピューターの再起動が自動起動に設定されていない場合、BizTalk Server サービスが開始されないことがあります。  
  
##### <a name="cause"></a>原因  
 これは、ENTSSO サービスの開始にかかる時間が、BizTalk Server サーバーに許可されたタイムアウト時間を超えることがあるためです。  
  
##### <a name="solution"></a>解決方法  
 この問題を解決するには、DTC を自動に設定します。  
  
#### <a name="sql-resources-may-become-locked"></a>SQL リソースがロックされることがある  
  
##### <a name="problem"></a>問題  
 次のエラーが発生することがあります。  
  
 **トランザクション (プロセス ID 95) が、ロックのリソースで他のプロセスとデッドロックして、このトランザクションがそのデッドロックの対象となりました。トランザクションを再実行します。**  
  
##### <a name="cause"></a>原因  
 これはまれに発生する状況であり、ユーザーが行った管理操作のために別のユーザーがデータベース管理からロックアウトされています。  
  
##### <a name="solution"></a>解決方法  
 問題は短時間で自動的に解消されます。 数分後にもう一度実行してみてください。  
  
#### <a name="sql-database-may-become-locked"></a>SQL データベースがロックされることがある  
  
##### <a name="problem"></a>問題  
 ユーザーが SQL データベースからロックアウトされることがあります。 さまざまなエラー メッセージが返される可能性があります。  
  
##### <a name="cause"></a>原因  
 1 人のユーザーがデータベースに書き込んでいるため、実質的に別のユーザーがデータベースからロックアウトされることがあります。  
  
##### <a name="solution"></a>解決方法  
 問題は短時間で自動的に解消されます。 数分後にもう一度実行してみてください。  
  
#### <a name="termination-of-multiple-service-instances-in-a-multiple-messagebox-environment-fails-with-an-error"></a>複数のメッセージ ボックス環境で複数のサービス インスタンスを終了するとエラーが発生する  
  
##### <a name="problem"></a>問題  
 BizTalk Server 管理コンソールから複数のサービス インスタンスを終了しようとすると失敗し、次のようなエラーが表示されます。  
  
 SQL Server によって、コンポーネント 'Agent XPs' のプロシージャ 'sys.xp_sqlagent_enum_jobs' に対するアクセスがブロックされました。サーバーのセキュリティ構成で、このモジュールが OFF に設定されているためです。  
  
> [!NOTE]
>  この問題は複数のメッセージ ボックス環境で発生します。  
  
##### <a name="cause"></a>原因  
 場合、複数のメッセージ ボックス環境でこの問題は発生 SQL エージェント ジョブ 'operations_operateoninstances_onmaster _\<*dbName*\>' が、セカンダリ メッセージ ボックス データベースで実行されていません。 セカンダリ メッセージ ボックス データベースからプライマリ メッセージ ボックス データベースに情報を伝達するためには、このジョブを実行している必要があります。 このジョブが有効になっていないか、ログオン エラーが発生した場合、このジョブは実行できません。  
  
##### <a name="solution"></a>解決方法  
 操作を実行する複数のサービス インスタンスで同時に、BizTalk 管理コンソールを使用しているし、複数のメッセージ ボックス データベース、BizTalk Server 環境を構成する場合は、SQL Server エージェント ジョブがという名前のことを確認 ' Operations_OperateOnInstances_OnMaster_\<*dbName*\>' すべてのセカンダリ (マスター以外の) メッセージ ボックス データベースで有効にします。 さらに、セカンダリ メッセージ ボックス データベースをホストする SQL Server コンピューターの SQL Server エージェント サービスは、セカンダリ メッセージ ボックス データベースの BTS_SQLAGENT_USER データベース ロールに含まれるアカウントとして実行する必要があります。  
  
> [!NOTE]
>  \<*dbname* \> BizTalk メッセージ ボックス データベースの実際の名前のプレース ホルダーです。  
  
 SQL Server エージェント サービス アカウントをセカンダリ メッセージ ボックス データベースの BTS_SQLAGENT_USER データベース ロールに追加するには、次の手順を実行します。  
  
 **SQL Server 2008 で**  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft SQL Server 2008**、順にクリック**SQL Server Management Studio**です。  
  
2.  入力を求められたらを選択して、**サーバーの種類**の**データベース エンジン**を入力するかを選択、**サーバー名**セカンダリ メッセージ ボックス データベースをホストします。  
  
3.  クリックして展開**データベース**セカンダリ メッセージ ボックス データベースを展開し、クリックして展開**セキュリティ**をクリックして展開**ロール**をクリックして展開**データベース ロール**、し、BTS_SQLAGENT_USER データベース ロールをダブルクリックします。  
  
4.  **[追加]** をクリックします。  
  
5.  をクリックして**参照**、SQL Server エージェント サービス アカウントのメンバーであるグループを選択し、をクリックして**OK**です。  
  
> [!NOTE]
>  SQL Server エージェント サービス アカウントが指定されたグループのメンバーではない場合、このアカウントをグループに追加する必要があります。  
  
#### <a name="changes-applied-in-one-instance-of-the-biztalk-administration-console-are-not-automatically-updated-in-other-instances-of-the-biztalk-administration-console"></a>BizTalk 管理コンソールのあるインスタンスに適用した変更が、BizTalk 管理コンソールの他のインスタンスに自動的に反映されない  
  
##### <a name="problem"></a>問題  
 BizTalk 管理コンソールの複数のインスタンスが同時に同じ BizTalk Server グループに接続している場合に、あるインスタンスで行われた変更が他のインスタンスに自動的に反映されません。 このため、BizTalk 管理コンソールのインスタンスに表示されているアイテムの状態が BizTalk 管理データベースに格納されているアイテムの実際の状態と一致しない場合に、そのインスタンスでアイテムを変更しようとすると、同時実行違反エラーが発生する可能性があります。  
  
##### <a name="cause"></a>原因  
 BizTalk 管理コンソールの各インスタンスは、BizTalk グループ構成のキャッシュを独自に保持しており、そのキャッシュにのみ変更を反映します。 キャッシュが更新されるのは、BizTalk 管理コンソール ビューが更新されるときだけです。  
  
##### <a name="resolution"></a>解決策  
 BizTalk 管理コンソールで、同時実行違反エラーが発生した場合をクリックして、BizTalk 管理コンソールのインスタンスのキャッシュを更新、**更新**BizTalk 管理コンソール ボタンツールバーまたはキーを押して、 **f5 キーを押して**キー。  
  
#### <a name="failed-to-execute-action-stop-error-occurs-when-you-attempt-to-stop-an-orchestration-with-the-biztalk-administration-console"></a>BizTalk 管理コンソールでオーケストレーションを停止しようとすると、"アクション '停止' の実行に失敗しました" というエラーが発生する  
  
##### <a name="problem"></a>問題  
 BizTalk 管理コンソールでオーケストレーションを停止しようとすると、次のようなエラー メッセージが表示されます。  
  
```  
Failed to execute action 'Stop'.  
------------------------------  
ADDITIONAL INFORMATION:  
A transport-level error has occurred when sending the request to the server. (provider: TCP Provider, error: 0 - An existing connection was forcibly closed by the remote host.) (Microsoft SQL Server, Error: 10054)  
```  
  
 この問題は、次の条件が当てはまるときに発生します。  
  
-   BizTalk 管理コンソールが開いている。  
  
-   BizTalk 管理データベースが SQL Server のクラスター化インスタンスにインストールされている。  
  
-   SQL Server のクラスター化インスタンスがフェールオーバーされている。  
  
-   フェールオーバー完了後に、BizTalk 管理コンソールを使用してオーケストレーションの実行中のインスタンスを停止しようとした。  
  
##### <a name="cause"></a>原因  
 BizTalk 管理コンソールは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の管理データベースへの接続を維持しています。 フェールオーバー中に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の管理データベースとの接続が切断されると、BizTalk 管理コンソールをいったん閉じて再度開くまで、一部の管理タスクから "接続できませんでした" または "実行できませんでした" というエラーが返される場合があります。  
  
##### <a name="resolution"></a>解決策  
 BizTalk 管理コンソールを閉じて再度開きます。 BizTalk 管理コンソールが再び開くと、指定した [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理データベースとの接続が新たに作成されます。  
  
#### <a name="windows-group-names-that-were-previously-deleted-do-not-have-access-to-the-biztalk-server-databases"></a>以前に削除した Windows グループ名で BizTalk Server データベースにアクセスできない  
  
##### <a name="problem"></a>問題  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を再インストールする際に、以前に削除した Windows グループ名を使用すると、その Windows グループは BizTalk Server データベースにアクセスできません。  
  
##### <a name="cause"></a>原因  
 Windows グループを削除し、同じ名前で Windows グループを作成すると、その Windows グループ用に新しいセキュリティ識別子 (SID) が生成されますが、 以前の SID が SQL Server にキャッシュされたままであるため、新しい Windows グループは SQL Server にログオンできません。  
  
##### <a name="resolution"></a>解決策  
 Windows グループを削除するときは、その Windows グループの SQL Server ログインも削除する必要があります。  
  
#### <a name="biztalk-administrator-cannot-start-the-biztalk-server-administration-console"></a>BizTalk 管理者が BizTalk Server 管理コンソールを起動できない  
  
##### <a name="problem"></a>問題  
 BizTalk 管理者 (BizTalk Administrators Windows グループのメンバー) がローカル コンピューターの Windows Administrators グループのメンバーでない場合、BizTalk Server 管理コンソールを開けないことがあります。  
  
##### <a name="cause"></a>原因  
 この問題は、BizTalk Server を再インストールまたは再構成した場合に発生します。 SQL Server がキャッシュされたセキュリティ ID を使用したことが原因です。  
  
##### <a name="resolution"></a>解決策  
 BizTalk 管理者を、ローカル コンピューター上のローカル Windows Administrators グループに一時的に追加します。 BizTalk Server 管理コンソールが正常に開いたら、ローカル コンピューター上のローカル Windows Administrators グループから BizTalk 管理者を削除します。  
  
#### <a name="cannot-start-a-host-instance-on-a-remote-computer"></a>リモート コンピューターでホスト インスタンスを起動できない  
  
##### <a name="problem"></a>問題  
 BizTalk ホスト インスタンスを起動するときに、次のエラーを表示する可能性があります、リモート コンピューター上の BizTalk ホスト インスタンスを作成するときに:「ログオンに失敗したため開始できませんでした」。  
  
##### <a name="cause"></a>原因  
 このエラーは、BizTalk ホスト インスタンスを実行しているサービス アカウントに無効な資格情報を入力した場合、またはそのサービス アカウントにサービスとしてログオンする権限がない場合に発生します。  
  
##### <a name="resolution"></a>解決策  
 BizTalk ホスト インスタンスを起動する前に、リモート コンピューター内のサービス アカウントにサービスとしてログオンする権限を割り当てます。 ローカル コンピューターではこの処理が自動的に行われますが、リモート コンピューターでは手動で実行する必要があります。  
  
#### <a name="creating-or-configuring-a-host-instance-on-an-x64-computer-with-the-32-bit-only-option-selected-fails"></a>X64 コンピューターで [32 ビットのみ] オプションが選択または構成されていると、ホスト インスタンスの作成または構成が失敗する  
  
##### <a name="problem"></a>問題  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで [32 ビットのみ] オプション (既定) が選択されていると、X64 コンピューター上の BizTalk ホスト インスタンスの作成が失敗します。  
  
 BizTalk Server 構成マネージャーで、[32 ビットのみ] オプションを選択して、X64 コンピューターの BizTalk Server ランタイムの構成や、インプロセス ホスト インスタンスまたは分離ホスト インスタンスの作成を行うと、サービスの開始が失敗する可能性があります。  
  
##### <a name="cause"></a>原因  
 Unknown  
  
##### <a name="resolution"></a>解決策  
 この問題は断続的に発生します。 ホストの作成または構成を再度試みるか、[32 ビットのみ] オプションをオフにします。  
  
#### <a name="host-instance-deletion-does-not-clear-registry-information"></a>ホスト インスタンスを削除してもレジストリ情報が消去されない  
  
##### <a name="problem"></a>問題  
 ローカル コンピューターの管理者でないユーザーがインプロセス ホストまたは分離ホストを削除すると、アクセスが拒否されたことを通知するエラー メッセージが表示されます。 ホストは強制的に削除できますが、 この方法でホストを削除すると、関連するすべてのレジストリ情報が消去されません。  
  
##### <a name="cause"></a>原因  
 ホスト インスタンスに関連するレジストリ情報を削除するには、管理者特権が必要です。  
  
##### <a name="resolution"></a>解決策  
 ローカル管理者アカウントでログオンしてホストを削除すると、関連するレジストリ情報も削除されます。  
  
#### <a name="cannot-delete-a-messagebox-database"></a>メッセージ ボックス データベースを削除できない  
  
##### <a name="problem"></a>問題  
 メッセージ ボックス データベースを削除できない場合があります。 削除に失敗した場合は、次のいずれかの問題が原因と考えられます。  
  
-   キャッシュ更新間隔に指定した時間が経過していない。  
  
-   メッセージ ボックス データベースに不完全なインスタンスが含まれている。  
  
 削除に失敗したときにキャッシュ更新間隔まだ切れていない場合、次のエラー メッセージが表示されます:"メッセージ ボックスにがある可能性がある残存作業、メッセージ ボックスのため削除できません。 確認して、MessageBox になくなる不完全なインスタンスがあること、もう一度やり直してください。"  
  
##### <a name="cause"></a>原因  
 メッセージ ボックス データベースで新しいメッセージの公開を無効にしてからデータベースを削除するまでの間に、キャッシュ更新間隔に指定した時間が経過する必要があります。 既定では、キャッシュ更新間隔は、60 秒です。  
  
##### <a name="resolution"></a>解決策  
 メッセージ ボックス データベースを削除するには、事前にそのメッセージ ボックス データベースについて新しいメッセージの公開を無効にし、キャッシュ更新間隔に指定した時間が経過するまで待つ必要があります。  
  
 メッセージ ボックス データベースに不完全なサービス インスタンスが含まれている場合、次のエラー メッセージが表示されます:"、メッセージ ボックスには不完全なインスタンスがまだ含まれているために削除できません。 メッセージ ボックスに不完全なインスタンスが存在しないことを確認して、再試行してください。" というエラー メッセージが表示されます。  
  
 BizTalk Server 管理コンソールの [グループ ハブ] ページを使用して、メッセージ ボックス データベースの不完全なサービス インスタンスを表示できます。 グループ ハブ ページでサービス インスタンスの状態を表示する方法については、次を参照してください。[追跡サービス インスタンスの検索方法](../core/how-to-search-for-tracked-service-instances.md)です。  
  
## <a name="see-also"></a>参照  
 [トラブルシューティング](../core/troubleshooting.md)