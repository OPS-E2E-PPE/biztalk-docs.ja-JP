---
title: TIBCO Rendezvous 用のアプリケーションを作成する関連 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f3603fcb-3594-460b-b74a-618e22d9c4e0
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a286a80ef2c867dd196fcdce414f2d0ff3c8255c
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "24013641"
---
# <a name="creating-affiliate-applications"></a>関連アプリケーションの作成
次の手順では、関連アプリケーションとシングル サインオン (SSO) の使用方法を説明します。 エンタープライズ シングル サインオンの使用方法の詳細については、Microsoft のドキュメントを参照してください。  
  
> [!NOTE]
>  SSO エラーが発生した場合を使用したドメイン アカウント、BizTalk Server を構成したときにこれは、エンタープライズ SSO サービスの機能に影響を確認します。 SSO はドメイン アカウントでのみ機能します。  
  
## <a name="create-an-affiliate-application"></a>関連アプリケーションを作成します。  
  
1.  コントロール パネルで、開く **サービス**, 、エンタープライズ シングル サインオン サービスが実行されていることを確認します。  
  
2.  コマンド プロンプト では、エンタープライズ シングル サインオン フォルダーにディレクトリを変更します。 例:  
  
     **C:\Program files \common files files \common files \enterprise シングル サインオン >**  
  
3.  エンタープライズ シングル サインオン コマンドを使用します。 コマンドの一覧を表示するには、使用、 **-ヘルプ** 切り替えます。  
  
4.  使用して関連アプリケーションを作成する * します。XML の開始としては、次のコマンドを入力します。  
  
     `ssomanage.exe -createapps C:\SSOtest\AffiliateApplication.xml`  
  
     各要素の説明は次のとおりです。  
  
     C:\SSOtest はアプリケーション XML を含むフォルダーです。  
  
     AffiliateApplication.xml は、アプリケーションを作成した、サインオン情報を含む XML です。  
  
     以下に例を示します。  
  
    ```  
    <?xml version="1.0"?>  
    <SSO>  
        <application name="TIBCO RendezvousApp">  
            <description> TIBCO Rendezvous SSO Application</description>  
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
  
## <a name="create-single-sign-on-tickets"></a>シングル サインオン チケットを作成します。  
  
1.  次のコマンドを入力し、SSO チケットの動作を制御します。  
  
     `ssomanage.exe -tickets yes yes`  
  
2.  表示される次の質問に応答します。  
  
     `ssomanage -tickets <allowed yes | no> <validate yes | no>`  
  
3.  完了時に、次の確認メッセージが表示されます。  
  
     **このコンピューターで使用中の SSO。操作が正常に完了しました。**  
  
## <a name="enable-affiliate-application-xml"></a>関連アプリケーション XML を有効にします。  
  
1.  次のコマンドを入力します。  
  
     `ssomanage -enableapp TIBCO RendezvousApp`  
  
2.  次のコマンドを入力してアプリケーションを一覧表示し、アプリケーションが作成されたことを確認します。  
  
     `ssoclient.exe –listapps`  
  
     使用可能な関連アプリケーションが一覧内に表示されます。  
  
     **Ibi \YOURID-TIBCO RendezvousApp に使用可能なアプリケーション**  
  
3.  関連アプリケーションの資格情報を設定するのには、次のコマンドを入力します。  
  
     `ssoclient.exe -setcredentials TIBCO RendezvousApp`  
  
4.  ユーザー名とパスワードのプロンプトで入力します。  
  
5.  TIBCO RendezvousApp 関連アプリケーションのログオン資格情報を入力します。  
  
     たとえば、そのユーザーが SSO サーバーを経由してシステムに入力するユーザー ID とパスワードを入力します。  
  
    -   ユーザー ID: user  
  
    -   パスワード: ******  
  
    -   パスワードの確認入力: ******  
  
6.  TIBCO Rendezvous の BizTalk アダプターに関連アプリケーションが表示される **トランスポートのプロパティ**  ダイアログ ボックス。  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter for TIBCO Rendezvous のセキュリティ](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md)   