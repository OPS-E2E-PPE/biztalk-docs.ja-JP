---
title: PeopleSoft Enterprise の関連アプリケーションの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 95151163-5aaf-4683-afb7-02949ccda3e1
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca67c8637f3738169e9818795eebefd9faeabe70
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390007"
---
# <a name="creating-affiliate-applications"></a>関連アプリケーションの作成
次の手順では、関連アプリケーションとシングル サインオン (SSO) の使用を開始する方法を示します。  
  
> [!NOTE]
>  SSO エラーが発生した場合は、ときに使用したドメイン アカウントを BizTalk Server を構成するように、エンタープライズ SSO サービスの機能に影響を確認します。 ドメイン アカウントでの SSO のみ機能します。  
  
## <a name="create-an-affiliate-application"></a>関連アプリケーションを作成します。  
  
1. コントロール パネルで、開く**サービス**、エンタープライズ シングル サインオン サービスが実行されていることを確認します。  
  
2. コマンド プロンプトでは、エンタープライズ シングル サインオン フォルダーにディレクトリを変更します。  
  
    例 :  
  
    **C:\Program Files\Common Files\Enterprise Single Sign-On>**  
  
3. エンタープライズ シングル サインオン コマンドを使用します。 コマンドの一覧は、使用、 **-ヘルプ**スイッチします。  
  
    ![](../core/media/siebeladapter-23-sso-commands.gif "SiebelAdapter_23_SSO_Commands")  
  
4. 使用して関連アプリケーションを作成する * です。開始、として XML では、次のコマンドを入力します。  
  
    `ssomanage.exe -createapps C:\SSOtest\AffiliateApplication.xml`  
  
    それぞれの文字の説明は次のとおりです。  
  
   - C:\SSOtest はアプリケーション XML を含むフォルダーです。  
  
   - AffiliateApplication.xml は、アプリケーションを作成したシングル サインオン情報を含む XML です。  
  
     以下に例を示します。  
  
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
  
## <a name="create-single-sign-on-tickets"></a>シングル サインオン チケットを作成します。  
  
1.  SSO チケットの動作を制御する次のコマンドを入力します。  
  
     `ssomanage.exe -tickets yes yes`  
  
2.  質問に答えます。  
  
     `ssomanage -tickets <allowed yes | no> <validate yes | no>`  
  
     完了時に確認メッセージが表示されます。  
  
     **このコンピューターでは、SSO サーバーを使用します。操作が完了しました。**  
  
## <a name="enable-the-affiliate-application-xml"></a>関連アプリケーション XML を有効にします。  
  
1.  次のコマンドを入力します。  
  
     `ssomanage -enableapp PeopleSoftApp`  
  
2.  アプリケーションを一覧表示し、アプリケーションが作成されたことを確認するのには、次のコマンドを入力します。  
  
     `ssoclient.exe –listapps`  
  
     使用可能な関連アプリケーションは、一覧に表示されます。  
  
     **Ibi \yourid-peoplesoftapp に使用可能なアプリケーション**  
  
3.  関連アプリケーションの資格情報を設定するのには、次のコマンドを入力します。  
  
     `ssoclient.exe -setcredentials PeopleSoftApp`  
  
4.  ユーザー名と、プロンプトでパスワードを入力します。 PeopleSoftApp 関連アプリケーションのログオン資格情報を入力します。  
  
     たとえば、ユーザー id と、SSO サーバーを使用してシステムに入力するには、そのユーザーのパスワードを入力します。  
  
    -   **ユーザー ID:** `user`  
  
    -   **パスワード:** `******`  
  
    -   **確認しますか。パスワード:** `******`  
  
5.  関連アプリケーションは、BizTalk Adapter for PeopleSoft Enterprise トランスポートのプロパティ ダイアログ ボックスに表示されます。  
  
## <a name="see-also"></a>参照  
 [アダプターのセキュリティ保護](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)