---
title: "SSO サーバーを設定する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- servers, selecting [SSO]
- SSO, selecting servers
- managing [SSO], selecting servers
- SSOManage [SSO]
ms.assetid: a0b0176d-b426-4ab1-8a7e-1f96f4214683
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c7dab9df7b5444b437f12737c37036b592a70aad
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-set-the-sso-server"></a>SSO サーバーを設定する方法
ssomanage を使用するたびに、まず、ユーザーが接続先のシングル サインオン サーバーを参照するように設定する必要があります。  
  
 これは、次の 2 つの方法のいずれかで行うことができます。  
  
-   各ユーザーが、自分自身が正しいシングル サインオン サーバーを参照するように設定します。  
  
-   シングル サインオン サーバーのローカルのコンピューター管理者が、シングル サインオン ユーザーのすべてのメンバーがこのサーバーを参照するように設定します。  
  
### <a name="to-set-the-enterprise-single-sign-on-server-using-the-mmc-snap-in"></a>MMC スナップインでエンタープライズ シングル サインオン サーバーを設定するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、順にクリック**SSO 管理**です。  
  
2.  MMC スナップインで、**コンソール ルート**を右クリックして**エンタープライズ シングル サインオン**、 をクリック**選択**です。  
  
3.  対象のサーバーを参照します。  
  
4.  必要に応じて、、**すべてのユーザーの SSO サーバーの設定**チェック ボックスをオンします。  
  
5.  **[OK]**をクリックします。  
  
### <a name="to-set-the-enterprise-single-sign-on-server-for-a-single-user-using-the-command-line"></a>コマンド ラインで 1 人のユーザーに対してエンタープライズ シングル サインオン サーバーを設定するには  
  
1.  **開始** メニューのをクリックして**実行**、し、入力**cmd**です。  
  
2.  コマンド ライン プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは**\<ドライブ\>**: \program files \common files \enterprise シングル サインオンします。  
  
3.  型**ssomanage – server \<SSO サーバー名\>**ここで、  **\<SSO サーバー名\>**シングル サインオン サーバーのコンピューター名をユーザーには接続しようとしています。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
### <a name="to-set-the-enterprise-single-sign-on-server-for-all-users-using-the-command-line"></a>コマンド ラインですべてのユーザーに対してエンタープライズ シングル サインオン サーバーを設定するには  
  
1.  **開始** メニューのをクリックして**実行**、し、入力**cmd**です。  
  
2.  コマンド ライン プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは**\<ドライブ\>**: \program files \common files \enterprise シングル サインオンします。  
  
3.  型**ssomanage – serverall \<SSO サーバー名\>**ここで、  **\<SSO サーバー名\>**シングル サインオン サーバーのすべてのコンピューター名にはシングル サインオン ユーザー アカウントのメンバーが指すされます。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
### <a name="to-determine-the-enterprise-single-sign-on-server-to-which-a-user-is-connected-using-the-command-line"></a>コマンド ラインでユーザーが接続されているエンタープライズ シングル サインオン サーバーを特定するには  
  
1.  **開始** メニューのをクリックして**実行**、し、入力**cmd**です。  
  
2.  コマンド ライン プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは**\<ドライブ\>**: \program files \common files \enterprise シングル サインオンします。  
  
3.  型**ssomanage – showserver**です。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
> [!NOTE]
>  このコマンドでは、現在のユーザーの設定だけでなく、存在する場合は他のユーザーの設定も表示されます。  
  
## <a name="see-also"></a>参照  
 [SSO を有効にする方法](../core/how-to-enable-sso.md)   
 [SSO を無効にする方法](../core/how-to-disable-sso.md)   
 [SSO データベース情報を表示する方法](../core/how-to-display-the-sso-database-information.md)   
 [SSO の使用](../core/using-sso.md)