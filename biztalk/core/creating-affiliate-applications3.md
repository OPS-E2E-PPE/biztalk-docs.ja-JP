---
title: Applications3 を関連の作成 |Microsoft Docs
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
ms.openlocfilehash: 48aaf4d7cd6df05d99f31a9ddce7c6ccb6e7ae68
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353947"
---
# <a name="creating-affiliate-applications"></a>関連アプリケーションの作成
次の手順では、シングル サインオン (SSO) を使用して関連アプリケーションを開始する方法について説明します。  
  
> [!NOTE]
>  SSO エラーが発生した場合は、あるアカウントを使用したドメイン、BizTalk Server を構成したときに、ESSO サービスの機能に影響するためを確認します。 ドメイン アカウントでの SSO のみ機能します。  
  
## <a name="creating-an-affiliate-application"></a>関連アプリケーションの作成  
  
#### <a name="to-create-an-affiliate-application"></a>関連アプリケーションを作成するには  
  
1.  **コントロール パネル**オープン**サービス**、エンタープライズ シングル サインオン サービスが実行されていることを確認します。  
  
2.  コマンド プロンプトでは、エンタープライズ シングル サインオン フォルダーにディレクトリを変更します。  
  
     例 :  
  
     **C:\Program Files\Common Files\Enterprise Single Sign-On>**  
  
3.  エンタープライズ シングル サインオン コマンドを使用します。 コマンドの一覧は、使用には、ヘルプ スイッチ。  
  
     ![](../core/media/siebeladapter-23-sso-commands.gif "SiebelAdapter_23_SSO_Commands")  
  
4.  使用して関連アプリケーションを作成する、*。次のコマンドで、先頭として XML を入力します。  
  
     **ssomanage.exe -createapps C:\SSOtest\AffiliateApplication.xml**  
  
     それぞれの文字の説明は次のとおりです。  
  
     C:\SSOtest は、アプリケーション XML を含むフォルダーです。  
  
     AffiliateApplication.xml は、アプリケーションにサインオンしている情報を含む、作成した XML です。  
  
     以下に例を示します。  
  
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
  
## <a name="creating-single-sign-on-tickets"></a>シングル サインオン チケットを作成します。  
  
#### <a name="to-create-sso-tickets"></a>SSO チケットを作成するには  
  
1.  SSO チケットの動作を制御する次のコマンドを入力します。  
  
     `ssomanage.exe -tickets yes yes`  
  
2.  質問に答えます。  
  
     `ssomanage -tickets <allowed yes | no> <validate yes | no>`  
  
     完了時に確認メッセージが表示されます。  
  
     **このコンピューターでは、SSO サーバーを使用します。操作が完了しました。**  
  
## <a name="enabling-the-affiliate-application-xml"></a>関連アプリケーション XML を有効にします。  
  
#### <a name="to-enable-affiliate-application-xml"></a>関連アプリケーション XML を有効にするには  
  
1.  次のコマンドを入力します。  
  
     `ssomanage -enableapp JDEdwardsApp`  
  
2.  アプリケーションを一覧表示し、アプリケーションが作成されたことを確認するのには、次のコマンドを入力します。  
  
     `ssoclient.exe –listapps`  
  
     関連アプリケーションが使用可能なは、一覧に表示されます。  
  
     **Ibi \yourid-jdedwardsapp に使用可能なアプリケーション**  
  
3.  関連アプリケーションの資格情報を設定するのには、次のコマンドを入力します。  
  
     `ssoclient.exe -setcredentials JDEdwardsApp`  
  
4.  ユーザー名と、プロンプトでパスワードを入力します。 JDEdwardsApp 関連アプリケーションのログオン資格情報を入力します。 たとえば、ユーザー id と、SSO サーバーを使用してシステムに入力するには、そのユーザーのパスワードを入力します。  
  
    -   **ユーザー ID:** ユーザー  
  
    -   **パスワード:** ******  
  
    -   **確認しますか。パスワード:** ******  
  
5.  関連アプリケーションは、BizTalk Adapter for JD Edwards OneWorld トランスポートのプロパティ ダイアログ ボックスのドロップダウン リストに表示されます。  
  
## <a name="see-also"></a>参照  
 [アダプターのセキュリティ](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)