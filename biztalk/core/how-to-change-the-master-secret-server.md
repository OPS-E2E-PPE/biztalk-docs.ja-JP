---
title: "マスター シークレット サーバーを変更する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Master Secret server, promoting
- managing [Master Secret server], promoting servers
- managing [SSO], promoting servers
- SSO, Master Secret server
- modifying, Master Secret server
- Master Secret server, changing
ms.assetid: 44a786ca-4645-44a8-b33e-d0019f0aeca9
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a1e30f1703f554792ce5243414a95965da93670
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-change-the-master-secret-server"></a>マスター シークレット サーバーを変更する方法
マスター シークレット サーバーをセットアップして SSO データベースを構成した後、元のマスター シークレット サーバーで障害が発生して復旧できない場合は、マスター シークレット サーバーを変更できます。 マスター シークレット サーバーを変更するには、SSO サーバーを、マスター シークレット サーバーに昇格させる必要があります。  
  
### <a name="to-change-the-master-secret-server-using-the-mmc-snap-in"></a>MMC スナップインを使用してマスター シークレット サーバーを変更するには  
  
1.  **開始** メニューのをクリックして**すべてのプログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、クリックして**SSO 管理**です。  
  
2.  スコープ ペインで右クリックして**システム**、クリックして**プロパティ**です。 マスター シークレット サーバーが表示されます、**全般**のタブ、**システム プロパティ** ダイアログ ボックス。  
  
3.  をクリックして**変更**を選択、新しいマスター シークレット サーバーです。  
  
    > [!IMPORTANT]
    >  MMC スナップインを使ってマスター シークレット サーバーを変更している場合、操作はマスター シークレット サーバー上で実行する必要があります。 マスター シークレット サーバー以外のコンピューターから MMC スナップインを使用して、マスター シークレット サーバーを変更することはできません。  
  
4.  新しいマスター シークレット サーバーにログオンし、マスター シークレットを、新しいマスター シークレット サーバーのレジストリに復元します。  
  
5.  **開始** メニューのをクリックして**実行**、し、入力**cmd**です。  
  
6.  コマンド ライン プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは*\<ドライブ\>*: \program files \common files \enterprise シングル サインオンします。  
  
7.  新しいマスター シークレット サーバーを再起動します。  
  
8.  型**ssoconfig – restoresecret と入力\<ファイルを復元\>**ここで、 **\<ファイルを復元\>**マスター シークレットがファイルの名前とパスには格納されています。  
  
     マスター シークレットがレジストリの次の場所に保存されます。  
  
     HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ENTSSO\SSOSS  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
### <a name="to-promote-a-single-sign-on-server-to-master-secret-server-using-the-command-line"></a>コマンド ラインを使用してシングル サインオン サーバーをマスター シークレット サーバーに昇格させるには  
  
1.  マスター シークレット サーバーに昇格させる SSO サーバーの名前を含む、XML ファイルを作成します。 例を次に示します。  
  
    ```  
    <sso>  
      <globalInfo>  
         <secretServer>SSO Server name</secretServer>  
      </globalInfo>  
    </sso>  
    ```  
  
    > [!IMPORTANT]
    >  マスター シークレット サーバーではないコンピューターからマスター シークレット サーバーを変更する場合、指定された XML ファイルにはマスター シークレット サーバー名のみが格納されていることを確認してください。 具体的に含めることはできません、SSO 管理者の XML タグまたは**ssomanage-updatedb**操作は失敗します。  
  
2.  **開始** メニューのをクリックして**実行**、し、入力**cmd**です。  
  
3.  コマンド ライン プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは*\<ドライブ\>*: \program files \common files \enterprise シングル サインオンします。  
  
4.  型**ssomanage – updatedb** \<**更新ファイル**\>ここで、 \<**更新ファイル**\> XML ファイルの名前を指定します手順 1. で作成します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
5.  マスター シークレット サーバーを再起動します。  
  
6.  型**ssoconfig – restoresecret と入力\<ファイルを復元\>**ここで、 **\<ファイルを復元\>**マスター シークレットがファイルの名前とパスには格納されています。  
  
     マスター シークレットがレジストリの次の場所に保存されます。  
  
     HKEY_LOCAL_MACHINESOFTWAREMicrosoftENTSSOSSOSS  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [マスター シークレット サーバー](../core/master-secret-server.md)   
 [マスター シークレット サーバーをクラスター化する方法](../core/how-to-cluster-the-master-secret-server1.md)   
 [SSO データベースを更新する方法](../core/how-to-update-the-sso-database.md)   
 [SSO の使用](../core/using-sso.md)