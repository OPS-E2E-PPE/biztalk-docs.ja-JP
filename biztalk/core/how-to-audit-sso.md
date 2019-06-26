---
title: SSO を監査する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [SSO], auditing
- SSO, auditing
- auditing [SSO]
- SSO database, auditing
ms.assetid: dc6d0726-fc31-4af2-9a23-8df9e3fc5836
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 315ef88247d61e26056467232bf5a460c6c7fed1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387185"
---
# <a name="how-to-audit-sso"></a>SSO を監査する方法
MMC スナップインまたはコマンドラインを使用して、両方、正および負監査のレベルを設定することができます。 監査の結果は、イベント ログとデータベースの監査ログの両方に格納されます。  
  
 SSO 管理者は、企業の規定に応じて、成功と失敗の監査レベルを設定できます。 成功と失敗の監査は、次のレベルのいずれかに設定できます。  
  
 0 = なし  
  
 1 = 低。  
  
 2 = 中。  
  
 3 = 高。 このレベルは、できるだけ多くの監査メッセージを発行します。  
  
 成功の監査の既定値は 0 (なし) と、失敗の監査の既定値は 1(low) します。  
  
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
  
### <a name="to-audit-single-sign-on-using-the-mmc-snap-in"></a>シングル サインオン、MMC スナップインを使用して監査するには  
  
1.  **開始** メニューのをクリックして**すべてのプログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、 をクリックし、 **SSO 管理**。  
  
2.  ENTSSO MMC スナップインの [スコープ] ウィンドウで、**エンタープライズ シングル サインオン**ノード。  
  
3.  右クリックして**システム**、 をクリックし、**プロパティ**します。  
  
4.  **システム プロパティ**ダイアログ ボックスで、をクリックして、**監査**タブ。  
  
5.  適切な設定を入力し、クリックして**OK**します。  
  
### <a name="to-audit-single-sign-on-using-the-command-line"></a>シングル サインオン、コマンドラインを使用して監査するには  
  
1.  **開始** メニューのをクリックして**実行**、し、入力**cmd**します。  
  
2.  コマンド ライン プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは **\<ドライブ\>** : \Program Files\Common \enterprise シングル サインオンします。  
  
3.  型**ssoconfig – auditlevel\<正\>\<負\>** ここで、 **\<正\>** のレベルです監査アクションが成功すると **\<負\>** アクションが失敗する場合の監査のレベルです。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
### <a name="to-audit-the-sso-database"></a>SSO データベースを監査するには  
  
1. クリックして**開始**、 をクリックして**実行**、し、入力**cmd**します。  
  
2. コマンド ライン プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは **\<ドライブ\>** : \Program Files\Common \enterprise シングル サインオンします。  
  
3. 型**ssomanage – updatedb\<更新ファイル\>** ここで、 <strong>\<更新ファイル\></strong>はパスとファイルの名前。  
  
   > [!NOTE]
   >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [SSO データベースを更新する方法](../core/how-to-update-the-sso-database.md)   
 [SSO の使用](../core/using-sso.md)