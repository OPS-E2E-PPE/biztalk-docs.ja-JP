---
title: BizTalk Server のセキュリティを管理する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Server, security
- security, user accounts
- security, passwords
- certificates, security
- security, certificates
- security, BizTalk Server
- passwords, security
- user accounts, security
ms.assetid: adc89b0a-9846-4c99-b0fc-a32fc56ed769
caps.latest.revision: 31
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f31ef3483661b20ff62cadb0ec601282a05af9e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262858"
---
# <a name="managing-biztalk-server-security"></a>BizTalk Server のセキュリティを管理します。
セキュリティで保護された Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境を維持するには、アカウント、証明書、およびパスワードを管理する必要があります。 BizTalk Server が処理するビジネス ドキュメントのセキュリティを確保できるよう、BizTalk Server 管理者は次のアカウントと証明書を管理します。  
  
-   **BizTalk Server 管理者グループ**です。 BizTalk 管理コンソールまたは Microsoft Windows Management Instrumentation (WMI) プロバイダを使用して管理タスクを実行するユーザーは、Microsoft SQL Server および Microsoft Windows の適切な権限を持っている必要があります。 管理タスクの特権の詳細については、次を参照してください。[最低限のセキュリティ ユーザー権限](../core/minimum-security-user-rights.md)です。  
  
     BizTalk Server 管理者グループにユーザーを追加するまたは BizTalk Server 管理者グループからユーザーを削除する方法については、次を参照してください。[を BizTalk Server 管理者グループを管理する方法](../core/how-to-manage-the-biztalk-server-administrators-group.md)です。  
  
     エンタープライズ シングル サインオンに関する詳細については、次を参照してください。[を使用して SSO](../core/using-sso.md)です。  
  
-   **BizTalk Server Operators グループ**です。 BizTalk Server Operator は権限レベルの低いロールで、監視操作とトラブルシューティング操作にのみアクセスできます。  
  
     BizTalk Server Operator グループのメンバは、次の操作を実行できます。  
  
    -   サービスの状態とメッセージ フローの表示。  
  
    -   アプリケーションの開始または停止。  
  
    -   オーケストレーションの開始または停止。  
  
    -   送信ポートまたは送信ポート グループの開始または停止。  
  
    -   受信場所の有効化または無効化。 変更は、次回のキャッシュ更新の後で有効になります。キャッシュの更新間隔は既定では 60 秒で、 BizTalk Server のグループ レベルで設定できます。  
  
    -   サービス インスタンスの終了と再開。  
  
     BizTalk Server Operators グループのメンバは、次の操作を実行できません。  
  
    -   BizTalk Server の構成の変更。  
  
    -   個人情報 (PII) に分類されるメッセージ コンテキストのプロパティまたはメッセージ本文の表示。  
  
    -   実行中のシステムに対するサブスクリプションを削除や追加など、メッセージ ルーティングのコースを変更する操作。これには BizTalk Server ランタイムへのメッセージの公開も含まれます。  
  
    > [!NOTE]
    >  BizTalk Server Operators グループのメンバであるユーザーが、BizTalk Server を実行しているコンピュータのローカル管理者でもある場合、このユーザーは、Operators グループ ロールの制限を受けずにこれらのコンピュータのデータにアクセスできます。 詳細については、次を参照してください。[最低限のセキュリティ ユーザー権限](../core/minimum-security-user-rights.md)です。  
  
    > [!NOTE]
    >  BizTalk Server Operators グループのメンバであるユーザーに対して、リモートの BizTalk Server の監視を許可する場合、このユーザーはリモート コンピュータのローカル管理者グループのメンバになっている必要があります。  
  
-   **ホストおよびサービス アカウント**です。 ホストとそれに関連するホスト インスタンスを作成するときには、ホストの Windows グループと、各ホスト インスタンスのサービス アカウント資格情報を指定する必要があります。 ホスト インスタンスのサービス アカウントは、ホストの Windows グループのメンバである必要があります。  
  
-   **署名証明書**です。 署名証明書 (秘密キー証明書) は、BizTalk グループに対して指定するものです。 これらは省略可能で、BizTalk Server 管理者がいつでも変更できます。  
  
 BizTalk Server で使用する Windows アカウントの詳細については、次を参照してください。 [Windows グループと BizTalk Server でのユーザー アカウント](../core/windows-groups-and-user-accounts-in-biztalk-server.md)です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [Windows グループとユーザー アカウントを管理するためのベスト プラクティス](../core/best-practices-for-managing-windows-groups-and-user-accounts.md)  
  
-   [証明書を管理するためのベスト プラクティス](../core/best-practices-for-managing-certificates1.md)  
  
-   [Windows グループおよびユーザー アカウントの管理](../core/managing-windows-groups-and-user-accounts.md)