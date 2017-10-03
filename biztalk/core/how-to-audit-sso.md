---
title: "SSO を監査する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [SSO], auditing
- SSO, auditing
- auditing [SSO]
- SSO database, auditing
ms.assetid: dc6d0726-fc31-4af2-9a23-8df9e3fc5836
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: abea3028c2ec9fd2131b8fd17247476b6fdfa6f0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-audit-sso"></a>SSO を監査する方法
MMC スナップインまたはコマンド ラインを使用して、成功と失敗の監査のレベルを設定できます。 監査の結果は、イベント ログと、データベースの監査ログの両方に保存されます。  
  
 SSO 管理者は、企業の規定に応じて、成功と失敗の監査レベルを設定できます。 成功と失敗の監査は、次のレベルのいずれかに設定できます。  
  
 0 = なし  
  
 1 = 低。  
  
 2 = 中。  
  
 3 = 高。 このレベルは、ように、できるだけ多くの監査メッセージを発行します。  
  
 成功の監査の既定値は 0 (なし)、および失敗の監査の既定値は 1(low) します。  
  
 データベース レベルの監査を変更するには、XML ファイルを使用して SSO データベースを更新する必要があります。 SSO データベースを更新するためのサンプル XML ファイルは次のとおりです。  
  
```  
<sso>  
<globalnfo>  
<auditDeletedApps>1000</auditDeletedApps>  
<auditDeletedMappings>1000</auditDeletedMappings>  
<auditCredentialLookups>1000</auditCredentialLookups>  
</globalInfo>  
</sso>  
  
```  
  
### <a name="to-audit-single-sign-on-using-the-mmc-snap-in"></a>MMC スナップインでシングル サインオンを監査するには  
  
1.  **開始** メニューのをクリックして**すべてのプログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、クリックして**SSO 管理**です。  
  
2.  ENTSSO MMC スナップインの [スコープ] ウィンドウで、展開、**エンタープライズ シングル サインオン**ノード。  
  
3.  右クリック**システム**、クリックして**プロパティ**です。  
  
4.  **システム プロパティ**ダイアログ ボックスで、をクリックして、**監査**タブです。  
  
5.  適切な設定を入力し、クリックして**OK**です。  
  
### <a name="to-audit-single-sign-on-using-the-command-line"></a>コマンド ラインでシングル サインオンを監査するには  
  
1.  **開始** メニューのをクリックして**実行**、し、入力**cmd**です。  
  
2.  コマンド ライン プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは**\<ドライブ >**: \program files \common files \enterprise シングル サインオンします。  
  
3.  型**ssoconfig – auditlevel\<正 >\<負の値 >**ここで、 **\<正 >**は、レベルのアクションが成功したときに監査と**\<負の値 >**操作が失敗したときの監査のレベルです。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
### <a name="to-audit-the-sso-database"></a>SSO データベースを監査するには  
  
1.  をクリックして**開始**、 をクリックして**実行**、し、入力**cmd**です。  
  
2.  コマンド ライン プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは**\<ドライブ >**: \program files \common files \enterprise シングル サインオンします。  
  
3.  型**ssomanage – updatedb\<更新プログラム ファイル >**ここで、 **\<更新プログラム ファイル >**はパスとファイルの名前。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [SSO データベースを更新する方法](../core/how-to-update-the-sso-database.md)   
 [SSO の使用](../core/using-sso.md)