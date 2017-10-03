---
title: "Applications2 関連の作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Single Sign-On, creating tickets
- creating affiliate applications
- tickets, SSO
- affiliate applications, enabling XML
- affiliate applications, creating
- SSO tickets
ms.assetid: 95151163-5aaf-4683-afb7-02949ccda3e1
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f39fbbfb62a9081937891b98e2b01a5e7f046e2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="creating-affiliate-applications"></a>関連アプリケーションの作成
次の手順では、関連アプリケーションとシングル サインオン (SSO) の使用を開始する方法を示します。  
  
> [!NOTE]
>  SSO エラーが発生した場合は、ときに使用したドメイン アカウント BizTalk Server を構成するように、エンタープライズ SSO サービスの機能に影響を確認します。 SSO はドメイン アカウントでのみ機能します。  
  
### <a name="to-create-an-affiliate-application"></a>関連アプリケーションを作成するには  
  
1.  コントロール パネルで、開く**Services**、エンタープライズ シングル サインオン サービスが実行されていることを確認してください。  
  
2.  コマンド プロンプトで、エンタープライズ シングル サインオン フォルダーにディレクトリを変更します。  
  
     例:  
  
     **C:\Program files \common files \enterprise でのシングル サインオン >**  
  
3.  エンタープライズ シングル サインオン コマンドを使用します。 コマンドの一覧は、使用、 **-ヘルプ**スイッチします。  
  
     ![](../core/media/siebeladapter-23-sso-commands.gif "SiebelAdapter_23_SSO_Commands")  
  
4.  使用して関連アプリケーションを作成する * です。スタート、として XML では、次のコマンドを入力します。  
  
     `ssomanage.exe -createapps C:\SSOtest\AffiliateApplication.xml`  
  
     それぞれの文字の説明は次のとおりです。  
  
    -   C:\SSOtest はアプリケーション XML を含むフォルダーです。  
  
    -   AffiliateApplication.xml は、自分で作成した、サインオン情報を含むアプリケーション XML です。  
  
     例:  
  
    ```  
    <?xml version="1.0"?>  
    <SSO>  
         <application name="PeopleSoftApp">  
              <description>PeopleSoft SSO Application</description>  
              <contact>someone@microsoft.com</contact>  
             <appUserAccount>DomainName\AppUserGroup</appUserAccount>  
              <!—-an existing group on the domain controller - >   
              <appAdminAccount>DomainName\AppAdminGroup<appAdminAccount>   
              <!-- an existing account in the domain group - >   
              <field ordinal="0" label="User ID" masked="no" />  
              <field ordinal="1" label="Password" masked="yes" />  
              <flags groupApp="no" allowTickets="yes" enableApp="yes"/>  
         </application>  
    </SSO>  
    ```  
  
## <a name="creating-single-sign-on-tickets"></a>シングル サインオン チケットの作成  
  
#### <a name="to-create-sso-tickets"></a>SSO チケットを作成するには  
  
1.  次のコマンドを入力し、SSO チケットの動作を制御します。  
  
     `ssomanage.exe -tickets yes yes`  
  
2.  次の質問に回答します。  
  
     `ssomanage -tickets <allowed yes | no> <validate yes | no>`  
  
     完了時に、確認メッセージが表示されます。  
  
     **このコンピューターで使用中の SSO。操作が完了しました。**  
  
## <a name="enabling-the-affiliate-application-xml"></a>関連アプリケーション XML の有効化  
  
#### <a name="to-enable-affiliate-application-xml"></a>関連アプリケーション XML を有効にするには  
  
1.  次のコマンドを入力します。  
  
     `ssomanage -enableapp PeopleSoftApp`  
  
2.  次のコマンドを入力してアプリケーションを一覧表示し、アプリケーションが作成されたことを確認します。  
  
     `ssoclient.exe –listapps`  
  
     使用可能な関連アプリケーションが一覧内に表示されます。  
  
     **Ibi \yourid-peoplesoftapp に使用可能なアプリケーション**  
  
3.  関連アプリケーションの資格情報を設定するには、次のコマンドを入力します。  
  
     `ssoclient.exe -setcredentials PeopleSoftApp`  
  
4.  プロンプトで、ユーザー名とパスワードを入力します。 PeopleSoftApp 関連アプリケーションのログオン資格情報を入力します。  
  
     たとえば、ユーザー id と、SSO サーバーにより、システムに入力するには、そのユーザーのパスワードを入力します。  
  
    -   **ユーザー ID:**`user`  
  
    -   **パスワード:**`******`  
  
    -   **パスワードのパスワード:**`******`  
  
5.  関連アプリケーションが [BizTalk Adapter for PeopleSoft Enterprise トランスポートのプロパティ] ダイアログ ボックスに表示されます。  
  
## <a name="see-also"></a>参照  
 [シングル サインオンを使用します。](../core/using-single-sign-on2.md)