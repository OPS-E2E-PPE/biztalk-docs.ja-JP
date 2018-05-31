---
title: Applications3 関連の作成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- affiliate applications
- Single Sign-On, creating tickets
- tickets, creating Single Sign-On
- affiliate applications, creating
- SSO tickets
ms.assetid: 800644fd-2286-4e59-894b-260f584dd29f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 857ee7edd623332e72176ac09082f0ec9fc460f4
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "24015153"
---
# <a name="creating-affiliate-applications"></a>関連アプリケーションの作成
次の手順では、シングル サインオン (SSO) を使用して関連アプリケーションを利用する方法について説明します。  
  
> [!NOTE]
>  SSO エラーが発生した場合は、BizTalk Server を構成したときにドメイン アカウントを使用したことを確認してください。これは、そのことが ESSO サービスの機能に影響するからです。 SSO はドメイン アカウントでのみ機能します。  
  
## <a name="creating-an-affiliate-application"></a>関連アプリケーションの作成  
  
#### <a name="to-create-an-affiliate-application"></a>関連アプリケーションを作成するには  
  
1.  **コントロール パネルの** , 、開かれている **サービス**, 、エンタープライズ シングル サインオン サービスが実行されていることを確認します。  
  
2.  コマンド プロンプト では、エンタープライズ シングル サインオン フォルダーにディレクトリを変更します。  
  
     例:  
  
     **C:\Program files \common files files \common files \enterprise シングル サインオン >**  
  
3.  エンタープライズ シングル サインオン コマンドを使用します。 コマンドの一覧を表示するには、-help スイッチを使用します。  
  
     ![](../core/media/siebeladapter-23-sso-commands.gif "SiebelAdapter_23_SSO_Commands")  
  
4.  使用して関連アプリケーションを作成する、* します。XML の先頭としては、次のコマンドに入力します。  
  
     **ssomanage.exe-createapps C:\SSOtest\AffiliateApplication.xml**  
  
     それぞれの文字の説明は次のとおりです。  
  
     C:\SSOtest は、アプリケーション XML を含むフォルダーです。  
  
     AffiliateApplication.xml は、アプリケーションの作成した、サインオン情報を含む XML です。  
  
     例:  
  
    ```  
    <?xml version="1.0"?>  
    <SSO>  
         <application name="JDEdwardsApp">  
              <description>JDEdwards SSO Application</description>  
              <contact>someone@microsoft.com</contact>  
              <userGroup>ibi\Domain Users</userGroup>  
              <!—-an existing group on the domain controller - >   
              <appAdminGroup>ibi\YourID</appAdminGroup>  
              <!-- an existing account within the domain group - >   
              <field ordinal="0" label="User ID" masked="no" />  
              <field ordinal="1" label="Password" masked="yes" />  
              <flags groupApp="no" allowTickets="yes" enableApp="yes"/>  
         </application>  
    </SSO>  
    ```  
  
## <a name="creating-single-sign-on-tickets"></a>シングル サインオン チケットの作成  
  
#### <a name="to-create-sso-tickets"></a>SSO チケットを作成するには  
  
1.  次のコマンドを入力して、SSO チケットの動作を制御します。  
  
     `ssomanage.exe -tickets yes yes`  
  
2.  次の質問に回答します。  
  
     `ssomanage -tickets <allowed yes | no> <validate yes | no>`  
  
     完了すると、次の確認メッセージが表示されます。  
  
     **このコンピューターで使用中の SSO。操作が正常に完了しました。**  
  
## <a name="enabling-the-affiliate-application-xml"></a>関連アプリケーション XML の有効化  
  
#### <a name="to-enable-affiliate-application-xml"></a>関連アプリケーション XML を有効にするには  
  
1.  次のコマンドを入力します。  
  
     `ssomanage -enableapp JDEdwardsApp`  
  
2.  アプリケーションを一覧表示し、アプリケーションが作成されたことを確認するのには、次のコマンドを入力します。  
  
     `ssoclient.exe –listapps`  
  
     関連アプリケーションが使用可能なは、一覧に表示されます。  
  
     **Ibi \yourid-jdedwardsapp に使用可能なアプリケーション**  
  
3.  次のコマンドを入力して、関連アプリケーションの資格情報を設定します。  
  
     `ssoclient.exe -setcredentials JDEdwardsApp`  
  
4.  プロンプトで、ユーザー名とパスワードを入力します。 JDEdwardsApp 関連アプリケーションのログオン資格情報を入力します。 たとえば、ユーザーの識別と SSO サーバーを経由してシステムに入力するには、そのユーザーのパスワードを入力します。  
  
    -   **ユーザー ID:** ユーザー  
  
    -   **パスワード:** ******  
  
    -   **パスワードのパスワード:** ******  
  
5.  関連アプリケーションが [BizTalk Adapter for JD Edwards OneWorld トランスポートのプロパティ] ダイアログ ボックスのドロップダウン リストに表示されます。  
  
## <a name="see-also"></a>参照  
 [アダプターのセキュリティ](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)