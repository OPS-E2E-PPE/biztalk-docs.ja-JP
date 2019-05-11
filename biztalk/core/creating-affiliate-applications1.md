---
title: 関連の TIBCO Rendezvous のアプリケーションを作成する |Microsoft Docs
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
ms.openlocfilehash: ba94161fa534187392e64e6138b6f8ae18920377
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354022"
---
# <a name="creating-affiliate-applications"></a>関連アプリケーションの作成
次の手順では、関連アプリケーションとシングル サインオン (SSO) の使用を開始する方法について説明します。 エンタープライズ シングル サインオンを使用する方法については、Microsoft のドキュメントを参照してください。  
  
> [!NOTE]
>  SSO エラーが発生した場合は、あるアカウントを使用したドメイン、BizTalk Server を構成したときに、これは、エンタープライズ SSO サービスの機能に影響を確認します。 ドメイン アカウントでの SSO のみ機能します。  
  
## <a name="create-an-affiliate-application"></a>関連アプリケーションを作成します。  
  
1.  コントロール パネルで、開く**サービス**、エンタープライズ シングル サインオン サービスが実行されていることを確認します。  
  
2.  コマンド プロンプトでは、エンタープライズ シングル サインオン フォルダーにディレクトリを変更します。 以下に例を示します。  
  
     **C:\Program Files\Common Files\Enterprise Single Sign-On>**  
  
3.  エンタープライズ シングル サインオン コマンドを使用します。 コマンドの一覧は、使用、 **-ヘルプ**スイッチします。  
  
4.  使用して関連アプリケーションを作成する * です。開始、として XML では、次のコマンドを入力します。  
  
     `ssomanage.exe -createapps C:\SSOtest\AffiliateApplication.xml`  
  
     各要素の説明は次のとおりです。  
  
     C:\SSOtest はアプリケーション XML を含むフォルダーです。  
  
     AffiliateApplication.xml は、アプリケーションを作成したシングル サインオン情報を含む XML です。  
  
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
  
1.  SSO チケットの動作を制御する次のコマンドを入力します。  
  
     `ssomanage.exe -tickets yes yes`  
  
2.  ように、次の質問に回答します。  
  
     `ssomanage -tickets <allowed yes | no> <validate yes | no>`  
  
3.  完了時に、次の確認メッセージが表示されます。  
  
     **このコンピューターでは、SSO サーバーを使用します。操作が完了しました。**  
  
## <a name="enable-affiliate-application-xml"></a>関連アプリケーション XML を有効にします。  
  
1.  次のコマンドを入力します。  
  
     `ssomanage -enableapp TIBCO RendezvousApp`  
  
2.  アプリケーションを一覧表示し、アプリケーションが作成されたことを確認するのには、次のコマンドを入力します。  
  
     `ssoclient.exe –listapps`  
  
     使用可能な関連アプリケーションは、一覧に表示されます。  
  
     **Ibi \YOURID-TIBCO RendezvousApp に使用可能なアプリケーション**  
  
3.  関連アプリケーションの資格情報を設定するのには、次のコマンドを入力します。  
  
     `ssoclient.exe -setcredentials TIBCO RendezvousApp`  
  
4.  ユーザー名と、プロンプトでパスワードを入力します。  
  
5.  TIBCO RendezvousApp 関連アプリケーションのログオン資格情報を入力します。  
  
     たとえば、ユーザー id と、SSO サーバーを使用してシステムに入力するユーザーのパスワードを入力します。  
  
    -   ユーザー ID: ユーザー  
  
    -   パスワード: * * *  
  
    -   パスワードの確認入力: * * *  
  
6.  BizTalk adapter for TIBCO Rendezvous の関連アプリケーションが表示されます**トランスポートのプロパティ** ダイアログ ボックス。  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter for TIBCO Rendezvous のセキュリティ](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md)   