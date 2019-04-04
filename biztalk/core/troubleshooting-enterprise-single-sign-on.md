---
title: エンタープライズ シングル サインオンのトラブルシューティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cb54af9f-a6ef-46c1-b987-2019cff3f837
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ebde8c0ccbb5d266b4f244f4597aa3d71286c8a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981667"
---
# <a name="troubleshooting-enterprise-single-sign-on"></a>エンタープライズ シングル サインオンのトラブルシューティング
このトピックでは、エンタープライズ シングル サインオン (SSO) の使用中に発生する可能性のある一般的な問題について説明します。  

 SSO 環境のトラブルシューティングを開始する際には、次の表の項目について順に実行し、すべてのコンポーネントが正常に動作していることを確認すると役立つ場合があります。  


|                                                                      質問                                                                      |                                                                                                                                                                                                                      コメント                                                                                                                                                                                                                       |
|----------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                        アプリケーション イベント ログに SSO システムからのメッセージが記録されていないか。                                         | イベント ログ内の SSO のメッセージは、SSO システムの問題を絞り込むのに役立ちます。 SSO システムからのメッセージのソースは ENTSSO です。 **重要:** エラーとしてではなく、イベント ログで警告として表示のさまざまな SSO エラーおよびイベント。 SSO システムでは、SSO サービスの単一クライアントにのみ影響する問題を警告として、SSO システム全体 (すべてのクライアント) に影響する問題をエラーとして生成します。 |
| SSO サービスが正常にインストールされているか。<br /><br /> 正常に起動されるか。<br /><br /> どのサービス アカウントが SSO サービスを実行しているか。 |                                                                                                                                                               SSO サービスが正常にインストールされていることと、SSO サービスのサービス アカウントが SSO 管理者グループのメンバーであることを確認します。                                                                                                                                                                |
|                                                             SSO データベースはどこにあるか。                                                             |                                                                                                                           コマンド ライン **ssoconfig -showdb**を使用してください。 このコマンドの詳細については、[SSO データベース情報を表示する方法](../core/how-to-display-the-sso-database-information.md)を参照してください。                                                                                                                           |
|                                                          どの SSO サーバーが使用されているか。                                                           |                                                                                                                                           コマンド ライン **ssomanage -showserver**を使用してください。 このコマンドの詳細については、[SSO サーバーを設定する方法](../core/how-to-set-the-sso-server.md)を参照してください。                                                                                                                                           |
|                                                       SSO 管理者アカウントは何か。                                                       |                                                                                                                         コマンド ライン **ssomanage –displaydb**を使用してください。 このコマンドの詳細については、[SSO データベース情報を表示する方法](../core/how-to-display-the-sso-database-information.md)を参照してください。                                                                                                                          |
|                                                          すべてが正しく有効化されているか。                                                          |                                                                                                                         コマンド ライン **ssomanage –displaydb**を使用してください。 このコマンドの詳細については、[SSO データベース情報を表示する方法](../core/how-to-display-the-sso-database-information.md)を参照してください。                                                                                                                          |
|                                                        関連アプリケーションはあるか。                                                        |                                                                                                                                 コマンド ライン **ssomanage –listapps all**を使用してください。 このコマンドの詳細については、[関連アプリケーションの一覧表示する方法](../core/how-to-list-affiliate-applications.md)を参照してください。                                                                                                                                 |
|               特定の関連アプリケーションが正常に実行されているか。<br /><br /> どのアカウントがこの関連アプリケーションを使用しているか。                |                                                                                               コマンドラインを使用して**ssomanage – displayapp**<em>\<アプリケーション名\></em>します。 このコマンドの詳細については、[関連アプリケーションのプロパティを一覧表示する方法](../core/how-to-list-the-properties-of-an-affiliate-application.md)を参照してください。                                                                                                |
|                                               この関連アプリケーションにマッピングがあるか。                                               |                                                                                                                           コマンドラインを使用して**ssomanage – listmappings**<em>\<アプリケーション名\></em>します。 このコマンドの詳細については、[ユーザー マッピングを一覧表示する方法](../core/how-to-list-user-mappings.md)を参照してください。                                                                                                                            |
|                                                    どのアカウントが SSO グループのメンバーか。                                                    |                                                                                                                                                                                            すべての SSO グループとアカウントについてグループのメンバーシップを確認します。                                                                                                                                                                                             |
|                                          SSO サーバーの COM+ アプリケーションは正常に動作しているか。                                           |                                                                                                                                                  SSO サーバーの COM+ アプリケーションを確認します。 **注:** イベントや警告メッセージなど詳細については、イベント ログを確認することもできます。                                                                                                                                                  |

## <a name="known-issues"></a>既知の問題  

#### <a name="entsso-service-fails-to-start"></a>ENTSSO サービスを開始できない  

##### <a name="problem"></a>問題  
 ENTSSO サービスを開始できません。  

##### <a name="cause"></a>原因  
 ENTSSO サービスが有効な SSO 管理者アカウントで実行されていない場合、サービスを開始できません。  

##### <a name="resolution"></a>解決策  
 有効な SSO 管理者アカウントを ENTSSO サービスに指定して、サービス コントロール マネージャー (SCM) スナップインからサービスを再起動します。  

#### <a name="biztalk-services-dependent-on-the-enterprise-single-sign-on-service-entsso-fail-to-start-after-a-reboot"></a>エンタープライズ シングル サインオン (ENTSSO) サービスに依存する BizTalk サービスが、再起動後に起動しない  

##### <a name="problem"></a>問題  
 BTSSvc$BizTalkServerApplication はエンタープライズ シングル サインオン サービス (ENTSSO) と依存関係があり、リブート後の起動中にタイムアウトすることがあります。  

##### <a name="cause"></a>原因  
 エンタープライズ シングル サインオン サービスは、起動に約 3 分かかる場合があります。  

##### <a name="resolution"></a>解決策  
 "BizTalk Service BizTalk グループ: BizTalkServerApplication" サービスを、スタートアップ オプションの種類を [自動 (遅延スタート)] として構成します。 これにより、すべての自動サービスのスタートアップ ルーチン完了後に、このサービスが開始されます。  

#### <a name="cannot-access-an-affiliate-application"></a>関連アプリケーションにアクセスできない  

##### <a name="problem"></a>問題  
 関連するアプリケーションの管理者アカウントが有効でない場合、エンタープライズ シングル サインオン サービスはこの関連アプリケーションを無効にします。  

##### <a name="cause"></a>原因  
 SSO アプリケーションの管理者アカウントが無効です。  

##### <a name="resolution"></a>解決策  
 関連アプリケーションを作成する前に、SSO アプリケーションの管理者アカウントが有効なことを確認します。 関連アプリケーションを使用するには、そのアプリケーションを有効にする必要があります。  

#### <a name="rpc-error-occurs-when-connecting-to-a-client-computer"></a>クライアント コンピューターへの接続時に RPC エラーが発生する  

##### <a name="problem"></a>問題  
 ときにコマンドを実行するユーザーなど**ssomanage-displayapp**<em>\<applicationname\></em>コンピューターは、情報を取得するリモート SSO サーバーに接続しようとしていますが、次のエラーを受け取った: エラー: 0x800706BA: RPC サーバーは使用できません。  

##### <a name="cause"></a>原因  
 このエラーは、ユーザーが間違ったサーバー情報を指定した場合、またはリモート サーバーで SSO サービスを利用できない場合に発生します。  

##### <a name="resolution"></a>解決策  

-   次の手順では、 [SSO サーバーを設定する方法](../core/how-to-set-the-sso-server.md)正しい SSO サーバーに接続しているかどうかを確認します。  

-   接続先の SSO サーバーで SSO サービスが有効になっており、実行されていることを確認します。  

#### <a name="master-secret-is-missing-or-corrupt"></a>マスター シークレットがない、または破損している  

##### <a name="problem"></a>問題  
 マスター シークレットがない、または破損しています。 この問題は、主に構成中に発生します。 シークレットがない場合、エンタープライズ シングル サインオン サービスが開始されるときに、以下のいずれかのメッセージがイベント ログに表示されます。  

 MessageId=10520  

 Severity=Warning  

 SSO_WARN_NO_SECRETS  

 MessageId=10565  

 Severity=Error  

 SSO_ERROR_SECRET_VALIDATE_FAILED  

 MessageId=10521  

 Severity=Error  

 SSO_ERROR_SECRETS_NOT_LOADED  

##### <a name="cause"></a>原因  
 この問題は、あるサービス アカウントでエンタープライズ シングル サインオン サービス (SSO) を実行中にシークレットを生成した後で、サービス アカウントが変更された場合に発生する可能性があります。 シークレットは、暗号化された形式でレジストリに保存されます。暗号化には、(ENTSSO を実行する) サービス アカウントの ID を基にしたキーが使用されます。  

##### <a name="resolution"></a>解決策  
 ENTSSO を実行しているサービス アカウントを、マスター シークレット作成時の元のサービス アカウントに変更します。  

 ENTSSO サービス アカウントを変更するには、次の操作を行います。  

1.  マスター シークレットをバックアップします。 詳細については、[バックアップ マスター シークレットを方法](../core/how-to-back-up-the-master-secret.md)を参照してください。  

2.  エンタープライズ シングル サインオン サービスを停止します。  

3.  サービス アカウントを変更します。  

4.  SSO を再起動します。破損したシークレットに関するイベント ログのエラーは一切無視します。  

5.  マスター シークレットを復元します。 詳細については、[マスター シークレットを復元する方法](../core/how-to-restore-the-master-secret.md)を参照してください。  

## <a name="see-also"></a>参照  
 [Enterprise Single Sign-On の実装](../core/implementing-enterprise-single-sign-on.md)