---
title: TIBCO EMS 用の関連アプリケーションの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 191e5b56-dab9-4bf3-9f89-a900907d64e0
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 914f966f2a5de3acd6daeddbd1912eefc9aa2fb8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966019"
---
# <a name="create-affiliate-applications"></a>関連アプリケーションを作成します。
次の手順では、関連アプリケーションとシングル サインオン (SSO) の使用を開始する方法について説明します。  
  
> [!NOTE]
>  SSO エラーが発生した場合は、BizTalk Server の構成時にドメイン アカウントを使用したかどうかを確認してください。これは Enterprise SSO サービスの機能に影響します。 ドメイン アカウントでの SSO のみ関数  
  
## <a name="create-an-affiliate-application"></a>関連アプリケーションを作成します。  
  
1. コントロール パネルで、開く**サービス**、エンタープライズ シングル サインオン サービスが実行されていることを確認します。  
  
2. コマンド プロンプトでは、エンタープライズ シングル サインオン フォルダーにディレクトリを変更します。  
  
    以下に例を示します。  
  
    **C:\Program files \common files \enterprise でシングル サインオン >**  
  
3. エンタープライズ シングル サインオン コマンドを使用します。 コマンドの一覧は、使用、 **-ヘルプ**スイッチします。  
  
4. 使用して関連アプリケーションを作成する * です。開始、として XML では、次のコマンドを入力します。  
  
    `ssomanage.exe -createapps C:\SSOtest\AffiliateApplication.xml`  
  
    それぞれの文字の説明は次のとおりです。  
  
   - C:\SSOtest はアプリケーション XML を含むフォルダーです。  
  
   - AffiliateApplication.xml は、アプリケーションを作成したシングル サインオン情報を含む XML です。  
  
     以下に例を示します。  
  
   ```  
   <?xml version="1.0"?>  
   <SSO>  
       <application name="TIBCO EMS App">  
           <description>TIBCO EMS SSO Application</description>  
           <contact>someone@example.com</contact>  
           <appUserAccount>DomainName\AppUserGroup</appUserAccount>  
           <!—an existing group on the domain controller - >   
           <appAdminAccount>DomainName\AppAdminGroup</appAdminAccount>  
           <!-- an existing account in the domain group - >   
           <field ordinal="0" label="User ID" masked="no" />  
           <field ordinal="1" label="Password" masked="yes" />  
           <flags groupApp="no" allowTickets="yes" enableApp="yes"/>  
       </application>  
   </SSO>  
   ```  
  
   XML の例を使用する場合、関連アプリケーションである TIBCO EMS App には、コマンド プロンプトに表示される値が含まれています。  
  
## <a name="create-single-sign-on-tickets"></a>シングル サインオン チケットを作成します。  
  
1.  次のコマンドを入力し、SSO チケットの動作を制御します。  
  
     `ssomanage.exe -tickets yes yes`  
  
2.  次の質問に回答します。  
  
     `ssomanage -tickets <allowed yes | no> <validate yes | no>`  
  
     完了時に確認メッセージが表示されます。  
  
     **このコンピューターで使用中の SSO。操作が完了しました。**  
  
## <a name="enable-affiliate-application-xml"></a>関連アプリケーション XML を有効にします。  
  
1. 次のコマンドを入力します。  
  
    `ssomanage -enableapp TIBCO EMSApp`  
  
2. 次のコマンドを入力してアプリケーションを一覧表示し、アプリケーションが作成されたことを確認します。  
  
    `ssoclient.exe –listapps`  
  
    使用可能な関連アプリケーションが一覧に表示されます。  
  
    **Ibi \YOURID-TIBCO EMSApp に使用可能なアプリケーション**  
  
3. 関連アプリケーションの資格情報を設定するのには、次のコマンドを入力します。  
  
    `soclient.exe -setcredentials TIBCO EMSApp`  
  
4. プロンプトで、ユーザー名とパスワードを入力します。 TIBCO EMS App 関連アプリケーションのログオン資格情報を入力します。  
  
    たとえば、ユーザー id と、SSO サーバーを使用してシステムに入力するには、そのユーザーのパスワードを入力します。  
  
   - ユーザー ID:**ユーザー**  
  
   - パスワード: `******`  
  
   - 確認入力  パスワード: `******`  
  
     BizTalk adapter for TIBCO EMS の関連アプリケーションが表示されます**トランスポートのプロパティ** ダイアログ ボックス。  
  
## <a name="see-also"></a>参照  
[アダプターのセキュリティ保護](../core/security-in-biztalk-adapter-for-tibco-ems.md)