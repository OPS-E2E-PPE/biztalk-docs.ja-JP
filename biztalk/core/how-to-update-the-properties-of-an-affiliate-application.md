---
title: 関連アプリケーションのプロパティを更新する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [SSO applications], updating properties
- applications [SSO], properties
ms.assetid: b06eefdd-a5ca-4a32-93d7-72246e31a2e4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6c50664fcf9e87ed6980a031fed980bf1e01301
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333662"
---
# <a name="how-to-update-the-properties-of-an-affiliate-application"></a>関連アプリケーションのプロパティを更新する方法
MMC スナップインまたはこのコマンドを使用して、XML ファイルで指定したとおり、1 つまたは複数のアプリケーション プロパティを更新することができます。 このタスクを実行する関連管理者があります。 次に更新するフィールドを表示する XML ファイルの例を示します。  
  
```  
<SSO>  
<application name="SSOApplication">  
<description>An SSO Application</description>  
<contact>someone@companyname.com</contact>  
<appUserAccount>DomainName\AppUserGroup</appUserAccount>  
<appAdminAccount>DomainName\AppAdminGroup</appAdminAccount>  
<flags allowTickets="no" validateTickets="yes"  timeoutTickets="yes" enableApp="no" />  
</application>  
</SSO>  
  
```  
  
 関連アプリケーションを作成した後は、次のプロパティを変更できません。  
  
-   関連アプリケーションの名前  
  
-   関連アプリケーションに関連付けられたフィールド  
  
-   関連アプリケーションの種類 (ホスト グループ、単独、構成ストア)  
  
-   関連管理者グループと同じ管理者アカウント (このフラグを指定すると、この関連アプリケーションの管理者アカウントとして常に関連管理者グループが使用されます)  
  
> [!IMPORTANT]
>  allowLocalAccounts フラグを yes に設定すると、管理アカウントとユーザー アカウントにローカル アカウントを使用できます。 ただし、このフラグは、1 台のコンピューターのシナリオでのみ使用できます。  
  
> [!IMPORTANT]
>  SSO 管理者、SSO 関連管理者、またはアプリケーション管理者にこのタスクを実行する必要があります。  
  
> [!IMPORTANT]
>  チケット フラグ (validateTickets と timeoutTickets) を変更する SSO 管理者である必要があります。  
  
> [!IMPORTANT]
>  SSO 関連アプリケーションの管理アカウントを変更するには管理者または SSO 管理者があります。  
  
### <a name="to-update-the-properties-of-an-affiliate-application-using-the-mmc-snap-in"></a>MMC スナップインを使用して関連アプリケーションのプロパティを更新するには  
  
1.  **開始** メニューのをクリックして**プログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、 をクリックし、 **SSO 管理**。  
  
2.  ENTSSO MMC スナップインの [スコープ] ウィンドウで、**エンタープライズ シングル サインオン**ノード。  
  
3.  関連アプリケーションを右クリックし、 **Update**します。  
  
### <a name="to-update-the-properties-of-an-affiliate-application-using-the-command-line"></a>コマンドラインを使用して関連アプリケーションのプロパティを更新するには  
  
1.  **開始** メニューのをクリックして**実行**、し、入力**cmd**します。  
  
2.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは**\<ドライブ\>**: \Program Files\Common \enterprise シングル サインオンします。  
  
3.  型**ssomanage – updateapps\<アプリケーション ファイル名\>** アプリケーション ファイル名は、XML ファイルです。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [SSO 関連アプリケーション](../core/sso-affiliate-applications.md)   
 [関連アプリケーションを有効にする方法](../core/how-to-enable-an-affiliate-application.md)   
 [ユーザー マッピングの管理](../core/managing-user-mappings.md)   
 [関連アプリケーションの管理](../core/managing-affiliate-applications.md)