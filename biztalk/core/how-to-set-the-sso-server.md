---
title: SSO サーバーを設定する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- servers, selecting [SSO]
- SSO, selecting servers
- managing [SSO], selecting servers
- SSOManage [SSO]
ms.assetid: a0b0176d-b426-4ab1-8a7e-1f96f4214683
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 804c1da3cec2fa13d82d6b0c9a7ae5f2e33989ed
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334119"
---
# <a name="how-to-set-the-sso-server"></a>SSO サーバーを設定する方法
Ssomanage を使用するたびに接続するシングル サインオン サーバーにユーザーをまずポイントする必要があります。  
  
 2 つの方法のいずれかでこれを行うことができます。  
  
-   個々 のユーザーは、正しいシングル サインオン サーバーをそれ自体をポイントできます。  
  
-   シングル サインオン サーバーのローカル コンピューターの管理者は、このサーバーをシングル サインオン ユーザー アカウントのすべてのメンバーを指定できます。  
  
### <a name="to-set-the-enterprise-single-sign-on-server-using-the-mmc-snap-in"></a>エンタープライズ シングル サインオン サーバー MMC スナップインを使用して設定するには  
  
1.  クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、順にクリックします**SSO 管理**します。  
  
2.  MMC スナップインで、**コンソール ルート**を右クリックして**エンタープライズ シングル サインオン**、 をクリック**選択**します。  
  
3.  目的のサーバーに移動します。  
  
4.  必要に応じて、、**すべてのユーザーの SSO サーバーを設定**チェック ボックスをオンします。  
  
5.  **[OK]** をクリックします。  
  
### <a name="to-set-the-enterprise-single-sign-on-server-for-a-single-user-using-the-command-line"></a>コマンドラインを使用して 1 人のユーザーのエンタープライズ シングル サインオン サーバーを設定するには  
  
1.  **開始** メニューのをクリックして**実行**、し、入力**cmd**します。  
  
2.  コマンド ライン プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは **\<ドライブ\>** : \Program Files\Common \enterprise シングル サインオンします。  
  
3.  型**ssomanage – server \<SSO サーバー名\>** ここで、  **\<SSO サーバー名\>** シングル サインオン サーバーのコンピューター名をユーザーには接続しようとしています。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
### <a name="to-set-the-enterprise-single-sign-on-server-for-all-users-using-the-command-line"></a>コマンドラインを使用してすべてのユーザーに対してエンタープライズ シングル サインオン サーバーを設定するには  
  
1.  **開始** メニューのをクリックして**実行**、し、入力**cmd**します。  
  
2.  コマンド ライン プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは **\<ドライブ\>** : \Program Files\Common \enterprise シングル サインオンします。  
  
3.  型**ssomanage – serverall \<SSO サーバー名\>** ここで、  **\<SSO サーバー名\>** はシングル サインオン サーバーのすべてのコンピューター名ですシングル サインオン ユーザー アカウントのメンバーが指すされます。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
### <a name="to-determine-the-enterprise-single-sign-on-server-to-which-a-user-is-connected-using-the-command-line"></a>エンタープライズ シングル サインオン サーバーのコマンドラインを使用して、ユーザーの接続先を決定するには  
  
1.  **開始** メニューのをクリックして**実行**、し、入力**cmd**します。  
  
2.  コマンド ライン プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは **\<ドライブ\>** : \Program Files\Common \enterprise シングル サインオンします。  
  
3.  型**ssomanage – showserver**します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
> [!NOTE]
>  このコマンドは、存在する場合、現在のユーザーも他のユーザーの設定を表示します。  
  
## <a name="see-also"></a>参照  
 [SSO を有効にする方法](../core/how-to-enable-sso.md)   
 [SSO を無効にする方法](../core/how-to-disable-sso.md)   
 [SSO データベース情報を表示する方法](../core/how-to-display-the-sso-database-information.md)   
 [SSO の使用](../core/using-sso.md)