---
title: 関連アプリケーションを作成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3be483f8-2617-459e-9081-aab886c75d93
caps.latest.revision: ''
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: 5145111b2c585edab92cc10c3e3614e8bb91a85d
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-create-an-affiliate-application"></a>関連アプリケーションを作成する方法
MMC スナップインを使用することができます、または**createapps」と入力**XML ファイルで指定された、1 つまたは複数のアプリケーションを作成するコマンド。 XML ファイルの Windows-Initiated シングル サインオン (SSO) の例を次に示します。  
  
```  
<sso>  
<application name="SAP">  
<description>The SAP application</description>   
<contact>someone@example.com</contact>   
<appuserAccount>domain\AppUserAccount</appuserAccount>   
<appAdminAccount>domain\AppAdminAccount</appAdminAccount>   
<field ordinal="0" label="User Id" masked="no" />   
<field ordinal="1" label="Password" masked="yes" />   
<flags groupApp="no" configStoreApp="no" allowTickets="no" validateTickets="yes" allowLocalAccounts="no" timeoutTickets="yes" adminAccountSame="no" enableApp="no" />  
</application>  
</sso>  
  
```  
  
 関連アプリケーションを作成した後は、次のプロパティを変更できません。  
  
-   関連アプリケーションの名前。  
  
-   関連アプリケーションに関連付けられているフィールドです。  
  
-   関連アプリケーションの種類 (ホスト グループ、個人の場合、または構成ストア)。  
  
-   関連管理者グループと同じ管理者アカウント (このフラグを指定するは常に使用関連管理者グループ アカウントの administrator としてこの関連アプリケーションの)。  
  
> [!IMPORTANT]
>  allowLocalAccounts フラグを yes に設定すると、管理アカウントとユーザー アカウントにローカル アカウントを使用できます。 ただし、このフラグは 1 台のコンピューターのシナリオ以外では使用できません。  
  
> [!IMPORTANT]
>  この作業を実行するには、SSO 管理者または SSO 関連管理者である必要があります。  
  
> [!NOTE]
>  ドメイン コント ローラーで、構成を実行して、ドメイン ローカル スコープのグループが関連アプリケーションの作成中にアプリケーションの管理者またはアプリケーションのユーザーの指定された場合は、ローカル アカウントのフラグを有効にすることをお勧めします。 これを行うには :  
  
-   MMC スナップインでは、作成プロセス中にアクセス アカウントを許可するローカル アカウントを選択します。  
  
-   コマンドラインから指定 allowLocalAccounts 関連アプリケーションの作成用の XML ファイルで = [はい] です。  
  
 関連アプリケーションは作成した後で有効にする必要があります。 詳細については、次を参照してください。[関連アプリケーションを有効にする方法](../esso/how-to-enable-an-affiliate-application.md)です。  
  
### <a name="to-create-an-affiliate-application-using-the-microsoft-management-console-mmc-snap-in"></a>Microsoft 管理コンソール (MMC) スナップインを使用して関連アプリケーションを作成するには  
  
1.  をクリックして**開始**、 をポイント**プログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、順にクリック**SSO 管理**です。  
  
2.  ENTSSO MMC スナップインのスコープ ペインで、展開、 **エンタープライズ シングル サインオン** ノードです。  
  
3.  右クリック**関連アプリケーション**、クリックして**新規**です。  
  
4.  指示に従って、**新しい関連アプリケーションの作成**ウィザード。  
  
### <a name="to-create-an-affiliate-application-using-the-command-line"></a>コマンド ラインを使用して関連アプリケーションを作成するには  
  
1.  をクリックして **開始**, 、 をクリックして **実行**, 、型 `cmd`, 、ENTER キーを押します。  
  
2.  コマンド プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。  
  
     既定のインストール ディレクトリは*\<ドライブ >*: \program files \common files \enterprise シングル サインオンします。  
  
3.  型`ssomanage –createapps <application file name>`ここで、 *\<アプリケーション ファイル名 >* XML ファイルです。  
  
## <a name="see-also"></a>参照  
 [SSO 関連アプリケーション](../esso/sso-affiliate-applications.md)   
 [関連アプリケーションを有効にする方法](../esso/how-to-enable-an-affiliate-application.md)   
 [関連アプリケーションを削除する方法](../esso/how-to-delete-an-affiliate-application.md)   
 [ユーザー マッピングを管理します。](../esso/managing-user-mappings.md)   
 [関連アプリケーションの管理](../esso/managing-affiliate-applications.md)