---
title: 側開始 SSO 関連アプリケーション ホストを作成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications [SSO], host initiated SSO
- creating, applications [SSO]
- host initiated SSO, creating affiliate applications
ms.assetid: 06202d21-055a-46bc-acff-da461f5673f1
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d207766ce830da973a4767213810f07432c743fc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65339832"
---
# <a name="how-to-create-affiliate-applications-for-host-initiated-sso"></a>ホスト側開始 SSO 関連アプリケーションを作成する方法
2 種類のアプリケーションを定義できます。  
  
-   **個別**は Windows および Windows 以外のユーザーに一対一のリレーションシップがあります。  
  
-   **ホスト グループ**同じ Windows アカウントに複数の Windows 以外のユーザーをマップすることができます。  
  
### <a name="to-create-an-affiliate-application-using-the-mmc-snap-in"></a>MMC スナップインを使用して関連アプリケーションを作成するには  
  
1.  **開始** メニューのをクリックして**すべてのプログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、 をクリックし、 **SSO 管理**。  
  
2.  ENTSSO MMC スナップインの [スコープ] ウィンドウで、**エンタープライズ シングル サインオン**ノード。  
  
3.  右クリック**関連アプリケーション**、 をクリックし、**アプリケーションの作成**を開く、**エンタープライズ シングル サインオン アプリケーション ウィザード**します。  
  
4.  ウィザードを使用して、関連アプリケーションのプロパティ を選択します。  
  
### <a name="to-create-an-individual-type-affiliate-application-using-the-command-line"></a>コマンドラインを使用してアプリケーションを関連する個々 の型を作成するには  
  
1.  **[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。  
  
2.  **実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。  
  
3.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。  
  
4.  型**ssomanage – createapps \<AffApp.xml\>** AffApp.xml は xml ファイルの名前です。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
     サンプル ファイルは、以下に示します。  
  
    ```  
    <?xml version="1.0"?>  
    <SSO>  
      <application name="SSOApp_Host1">  
        <description>An Individual Type Affiliate Application for Host Initiated SSO</description>  
        <contact>someone@companyname.com</contact>  
        <appUserAccount>DomainName\AppUserGroup_HISSO</appUserAccount>  
        <appAdminAccount>DomainName\AppAdminGroup_HISSO</appAdminAccount>  
        <field ordinal="0" label="User ID" masked="no" />  
        <field ordinal="1" label="Password" masked="yes" />  
        <flags windowsInitiatedSSO="no" enableApp="yes" />  
      </application>  
    </SSO>  
  
    ```  
  
### <a name="to-create-a-host-group-type-affiliate-application-using-the-command-line"></a>グループ タイプの関連アプリケーションのコマンドラインを使用してホストを作成するには  
  
1.  **[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。  
  
2.  **実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。  
  
3.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。  
  
4.  型**ssomanage – createapps \<AffApp.xml\>** AffApp.xml は xml ファイルの名前です。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
     サンプル ファイルは、以下に示します。  
  
    ```  
    <?xml version="1.0"?>  
    <SSO>  
      <application name="SSOApp_HostGroupApp1">  
        <description>A Group Type Affiliate Application for Host Initiated SSO associating multiple non-Windows user to a single Windows user account(DomainName\WindowsUserAccount1)</description>  
        <contact>someone@companyname.com</contact>  
        <windowsAccount>DomainName\WindowsUserAccount1</windowsAccount>  
        <appAdminAccount>DomainName\AppAdminGroup_HISSO</appAdminAccount>  
        <field ordinal="0" label="User ID" masked="no" />  
        <field ordinal="1" label="Password" masked="yes" />  
        <flags  enableApp="yes" />  
      </application>  
    </SSO>  
  
    ```  
  
### <a name="to-create-an-affiliate-application-supporting-both-windows-initiated-sso-and-host-initiated-sso-using-the-command-line"></a>両方の Windows をサポートしているアプリケーションが SSO を開始する、関連を作成して、ホスト側開始 SSO のコマンドラインを使用  
  
1.  **[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。  
  
2.  **実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。  
  
3.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。  
  
4.  型**ssomanage – createapps \<AffApp.xml\>** AffApp.xml は xml ファイルの名前です。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
     サンプル ファイルは、以下に示します。  
  
    ```  
    <?xml version="1.0" ?>   
    - <SSO>  
    - <application name="SSOApp1">  
      <description>An Individual Type Affiliate Application for both Host Initiated SSO and Windows Initiated SSO</description>   
      <contact>someone@companyname.com</contact>   
      <appUserAccount>DomainName\AppUserGroup</appUserAccount>   
      <appAdminAccount>DomainName\AppAdminGroup</appAdminAccount>   
      <field ordinal="0" label="User ID" masked="no" />   
      <field ordinal="1" label="Password" masked="yes" />   
      <flags  enableApp="yes" />   
      </application>  
      </SSO>  
  
    ```  
  
## <a name="see-also"></a>参照  
 [ホスト側開始 SSO](../core/host-initiated-sso.md)