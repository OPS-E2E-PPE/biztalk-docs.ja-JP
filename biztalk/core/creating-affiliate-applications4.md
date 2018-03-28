---
title: Applications4 関連の作成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tickets, Single Sign-On
- affiliate applications, setting credentials
- affiliate applications
- Single Sign-On, creating tickets
- SSO tickets
ms.assetid: 790fbe21-8081-4d57-803f-23014c8a3135
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87aa9be716e437e80c0e85bd9e462713e48090ad
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="creating-affiliate-applications"></a>関連アプリケーションの作成
次の手順では、SSO を使用して関連アプリケーションを利用する方法について説明します。  
  
> [!NOTE]
>  SSO エラーが発生した場合を使用したドメイン アカウント、BizTalk Server を構成したときにこれは、エンタープライズ SSO サービスの機能に影響を確認します。 SSO はドメイン アカウントでのみ機能します。  
  
### <a name="to-create-an-affiliate-application"></a>関連アプリケーションを作成するには  
  
1.  コントロール パネルで、開く **サービス**, 、エンタープライズ シングル サインオン サービスが実行されていることを確認します。  
  
2.  コマンド プロンプトで、ディレクトリをエンタープライズ シングル サインオン フォルダーに変更します。  
  
     例:  
  
     **C:\Program files \common files files \common files \enterprise シングル サインオン >**  
  
3.  エンタープライズ シングル サインオン コマンドを使用します。 コマンドの一覧を表示するには、使用、 **-ヘルプ** 切り替えます。  
  
4.  *.XML を基にして関連アプリケーションを作成するには、次のコマンドを入力します。  
  
     `ssomanage.exe -createapps C:\SSOtest\AffiliateApplication.xml`  
  
     それぞれの文字の説明は次のとおりです。  
  
    -   C:\SSOtest はアプリケーション XML を含むフォルダーです。  
  
    -   AffiliateApplication.xml は、アプリケーションを作成した、サインオン情報を含む XML です。  
  
     例:  
  
    ```  
    <?xml version="1.0"?>  
    <SSO>  
        <application name="JDEdwardsApp">  
            <description>JDEdwards SSO Application</description>  
            <contact>someone@microsoft.com</contact>  
            <userGroup>ibi\Domain Users</userGroup>  
            <!—an existing group on the domain controller - >   
            <appAdminGroup>ibi\YourID</appAdminGroup>  
            <!-- an existing account within the domain group - >   
  
            <field ordinal="0" label="User ID" masked="no" />  
            <field ordinal="1" label="Password" masked="yes" />  
            <flags groupApp="no" allowTickets="yes" enableApp="yes"/>  
  
        </application>  
    </SSO>  
    ```  
  
### <a name="to-create-single-sign-on-tickets"></a>シングル サインオン チケットを作成するには  
  
1.  次のコマンドを入力し、SSO チケットの動作を制御します。  
  
     `ssomanage.exe -tickets yes yes`  
  
2.  表示される次の質問に応答します。  
  
     `ssomanage -tickets <allowed yes | no> <validate yes | no>`  
  
     完了時に、次の確認メッセージが表示されます。  
  
     **このコンピューターで使用中の SSO。操作が正常に完了しました。**  
  
### <a name="to-enable-affiliate-application-xml"></a>関連アプリケーション XML を有効にするには  
  
1.  次のコマンドを入力します。  
  
     `ssomanage -enableapp JDEdwardsApp`  
  
2.  次のコマンドを入力してアプリケーションを一覧表示し、アプリケーションが作成されたことを確認します。  
  
     `ssoclient.exe –listapps`  
  
     利用可能な関連アプリケーションは、リストの表示を使用します。  
  
     **Ibi \yourid-jdedwardsapp に使用可能なアプリケーション**  
  
3.  関連アプリケーションの資格情報を設定するのには、次のコマンドを入力します。  
  
     `ssoclient.exe -setcredentials JDEdwardsApp`  
  
4.  プロンプトで、ユーザー名とパスワードを入力します。 JDEdwardsApp 関連アプリケーションのログオン資格情報を入力します。  
  
     たとえば、ユーザーの識別と SSO サーバーを経由してシステムに入力するには、そのユーザーのパスワードを入力します。  
  
    -   ユーザー ID: **ユーザー**  
  
    -   パスワード: `******`  
  
    -   確認入力 パスワード: `******`  
  
     BizTalk adapter for JD Edwards EnterpriseOne の関連アプリケーションが表示されます **トランスポートのプロパティ**  ダイアログ ボックス。  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter for JD Edwards EnterpriseOne のセキュリティ](../core/security-in-biztalk-adapter-for-jd-edwards-enterpriseone.md)