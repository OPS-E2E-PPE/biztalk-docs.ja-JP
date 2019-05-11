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
ms.openlocfilehash: 325b663f569b9cfce6fab8a65cc8b1f400d9d263
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353929"
---
# <a name="create-affiliate-applications"></a>関連アプリケーションを作成します。
次の手順では、関連アプリケーションとシングル サインオン (SSO) の使用を開始する方法について説明します。  
  
> [!NOTE]
>  SSO エラーが発生した場合は、BizTalk Server を構成したときに、ドメイン アカウントを使用したことを確認します。これは、エンタープライズ SSO サービスの機能に影響します。 ドメイン アカウントでの SSO のみ関数  
  
## <a name="create-an-affiliate-application"></a>関連アプリケーションを作成します。  
  
1. コントロール パネルで、開く**サービス**、エンタープライズ シングル サインオン サービスが実行されていることを確認します。  
  
2. コマンド プロンプトでは、エンタープライズ シングル サインオン フォルダーにディレクトリを変更します。  
  
    以下に例を示します。  
  
    **C:\Program Files\Common Files\Enterprise Single Sign-On>**  
  
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
  
   XML の例を使用すると、関連アプリケーションは、TIBCO EMS のアプリは、コマンド プロンプトで示すように値を格納します。  
  
## <a name="create-single-sign-on-tickets"></a>シングル サインオン チケットを作成します。  
  
1.  SSO チケットの動作を制御する次のコマンドを入力します。  
  
     `ssomanage.exe -tickets yes yes`  
  
2.  質問に答えます。  
  
     `ssomanage -tickets <allowed yes | no> <validate yes | no>`  
  
     完了時に確認メッセージが表示されます。  
  
     **このコンピューターでは、SSO サーバーを使用します。操作が完了しました。**  
  
## <a name="enable-affiliate-application-xml"></a>関連アプリケーション XML を有効にします。  
  
1. 次のコマンドを入力します。  
  
    `ssomanage -enableapp TIBCO EMSApp`  
  
2. アプリケーションを一覧表示し、アプリケーションが作成されたことを確認するのには、次のコマンドを入力します。  
  
    `ssoclient.exe –listapps`  
  
    使用可能な関連アプリケーションは、一覧に表示されます。  
  
    **Ibi \YOURID-TIBCO EMSApp に使用可能なアプリケーション**  
  
3. 関連アプリケーションの資格情報を設定するのには、次のコマンドを入力します。  
  
    `soclient.exe -setcredentials TIBCO EMSApp`  
  
4. ユーザー名と、プロンプトでパスワードを入力します。 TIBCO EMS App 関連アプリケーションのログオン資格情報を入力します。  
  
    たとえば、ユーザー id と、SSO サーバーを使用してシステムに入力するには、そのユーザーのパスワードを入力します。  
  
   - ユーザー ID:**ユーザー**  
  
   - パスワード: `******`  
  
   - 確認しますか。 パスワード: `******`  
  
     BizTalk adapter for TIBCO EMS の関連アプリケーションが表示されます**トランスポートのプロパティ** ダイアログ ボックス。  
  
## <a name="see-also"></a>参照  
[アダプターのセキュリティ保護](../core/security-in-biztalk-adapter-for-tibco-ems.md)