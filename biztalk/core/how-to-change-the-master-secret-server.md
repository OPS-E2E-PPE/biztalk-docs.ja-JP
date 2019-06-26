---
title: マスター シークレット サーバーを変更する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Master Secret server, promoting
- managing [Master Secret server], promoting servers
- managing [SSO], promoting servers
- SSO, Master Secret server
- modifying, Master Secret server
- Master Secret server, changing
ms.assetid: 44a786ca-4645-44a8-b33e-d0019f0aeca9
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23e588e4ea7ac91b5f4ff8124b33b3611e91e8d4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387010"
---
# <a name="how-to-change-the-master-secret-server"></a>マスター シークレット サーバーを変更する方法
マスター シークレット サーバーを設定して、SSO データベースを構成した後は、元のマスター シークレット サーバーが失敗し、復旧できない場合、マスター シークレット サーバーを変更できます。 マスター シークレット サーバーを変更するには、SSO サーバーをマスター シークレット サーバーを昇格させる必要があります。  
  
### <a name="to-change-the-master-secret-server-using-the-mmc-snap-in"></a>MMC スナップインを使用してマスター シークレット サーバーを変更するには  
  
1.  **開始** メニューのをクリックして**すべてのプログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、 をクリックし、 **SSO 管理**。  
  
2.  スコープ ペインで右クリック**システム**、 をクリックし、**プロパティ**します。 マスター シークレット サーバーが表示されます、**全般**のタブ、**システム プロパティ** ダイアログ ボックス。  
  
3.  クリックして**変更**新しいマスターを選択するシークレット サーバーです。  
  
    > [!IMPORTANT]
    >  マスター シークレット サーバーを変更するのには、MMC スナップインを使用して、ときに、マスター シークレット サーバーで操作を実行する必要があります。 マスター シークレット サーバーではないコンピューターから MMC スナップインを使用してマスター シークレット サーバーを変更することはできません。  
  
4.  新しいマスター シークレット サーバー、マスターを復元するログオン、新しいマスターのレジストリにシークレット サーバーです。  
  
5.  **開始** メニューのをクリックして**実行**、し、入力**cmd**します。  
  
6.  コマンド ライン プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは *\<ドライブ\>* : \Program Files\Common \enterprise シングル サインオンします。  
  
7.  新しいマスター シークレット サーバーを再起動します。  
  
8.  型**ssoconfig – restoresecret と入力\<ファイル復元\>** ここで、 **\<ファイルを復元\>** マスター シークレットがファイルの名前とパスには格納されています。  
  
     マスター シークレットは、次の場所にレジストリに格納されます。  
  
     HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ENTSSO\SSOSS  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
### <a name="to-promote-a-single-sign-on-server-to-master-secret-server-using-the-command-line"></a>コマンドラインを使用して、マスター シークレット サーバーに 1 つのシングル サインオン サーバーに昇格するには  
  
1.  マスター シークレット サーバーに昇格させる SSO サーバーの名前を含む XML ファイルを作成します。 例を次に示します。  
  
    ```  
    <sso>  
      <globalInfo>  
         <secretServer>SSO Server name</secretServer>  
      </globalInfo>  
    </sso>  
    ```  
  
    > [!IMPORTANT]
    >  変更するには、マスター シークレット サーバーではないコンピューターからマスター シークレット サーバーことを指定した XML ファイルにマスター シークレット サーバー名のみが含まれていることを確認します。 SSO 管理者の XML タグを含むことはない具体的には、または**ssomanage-updatedb**操作は失敗します。  
  
2.  **開始** メニューのをクリックして**実行**、し、入力**cmd**します。  
  
3.  コマンド ライン プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは *\<ドライブ\>* : \Program Files\Common \enterprise シングル サインオンします。  
  
4.  型**ssomanage – updatedb** \<**更新ファイル**\>ここで、 \<**更新ファイル**\> XML ファイルの名前を指定します手順 1. で作成します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
5.  マスター シークレット サーバーを再起動します。  
  
6.  型**ssoconfig – restoresecret と入力\<ファイル復元\>** ここで、 **\<ファイルを復元\>** マスター シークレットがファイルの名前とパスには格納されています。  
  
     マスター シークレットは、次の場所にレジストリに格納されます。  
  
     HKEY_LOCAL_MACHINESOFTWAREMicrosoftENTSSOSSOSS  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [マスター シークレット サーバー](../core/master-secret-server.md)   
 [マスター シークレット サーバーをクラスター化する方法](../core/how-to-cluster-the-master-secret-server1.md)   
 [SSO データベースを更新する方法](../core/how-to-update-the-sso-database.md)   
 [SSO の使用](../core/using-sso.md)