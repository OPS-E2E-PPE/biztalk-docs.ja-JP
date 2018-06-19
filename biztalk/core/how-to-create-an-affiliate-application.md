---
title: 関連アプリケーションを作成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [SSO applications], creating
- applications [SSO], creating
- creating, applications [SSO]
ms.assetid: d0967c4b-6201-416a-9d3a-23b5de5b83d6
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2f621faef7694a3dba7885bab5641e0baa58e8f
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "25969024"
---
# <a name="how-to-create-an-affiliate-application"></a>関連アプリケーションを作成する方法
MMC スナップインまたはここで示すコマンドを使用すると、XML ファイルで指定された 1 つ以上のアプリケーションを作成できます。 Windows 側開始 SSO の XML ファイルの例を次に示します。  
  
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
  
-   関連アプリケーションの名前  
  
-   関連アプリケーションに関連付けられたフィールド  
  
-   関連アプリケーションの種類 (ホスト グループ、単独、構成ストア)  
  
-   関連管理者グループと同じ管理者アカウント (このフラグを指定すると、この関連アプリケーションの管理者アカウントとして常に関連管理者グループが使用されます)  
  
> [!IMPORTANT]
>  allowLocalAccounts フラグを yes に設定すると、管理アカウントとユーザー アカウントにローカル アカウントを使用できます。 ただし、このフラグは 1 台のコンピューターのシナリオ以外では使用できません。  
  
> [!IMPORTANT]
>  この作業を実行するには、SSO 管理者または SSO 関連管理者である必要があります。  
  
 関連アプリケーションは作成した後で有効にする必要があります。 詳細については、次を参照してください。[関連アプリケーションを有効にする方法](../core/how-to-enable-an-affiliate-application.md)です。  
  
### <a name="to-create-an-affiliate-application-using-the-mmc-snap-in"></a>MMC スナップインを使用して関連アプリケーションを作成するには  
  
1.  **開始**  メニューのをクリックして **プログラム**, 、 をクリックして **Microsoft エンタープライズ シングル サインオン**, 、 をクリックし、 **SSO 管理**します。  
  
2.  ENTSSO MMC スナップインのスコープ ペインで、展開、 **エンタープライズ シングル サインオン** ノードです。  
  
3.  右クリック **関連アプリケーション**, 、クリックして **アプリケーションの作成**します。  
  
4.  指示に従って、 **エンタープライズ シングル サインオン アプリケーション ウィザード**します。  
  
### <a name="to-create-an-affiliate-application-using-the-command-line"></a>コマンド ラインを使用して関連アプリケーションを作成するには  
  
1.  **開始**  メニューのをクリックして **実行**, 、し、入力 **cmd**します。  
  
2.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは*\<ドライブ\>*: \program files \common files \enterprise シングル サインオンします。  
  
3.  型 * * ssomanage – createapps」と入力 *\<アプリケーション ファイル名\>* * *、どこで*\<アプリケーション ファイル名\>* XML ファイルです。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [SSO 関連アプリケーション](../core/sso-affiliate-applications.md)   
 [関連アプリケーションを有効にする方法](../core/how-to-enable-an-affiliate-application.md)   
 [関連アプリケーションを削除する方法](../core/how-to-delete-an-affiliate-application.md)   
 [ユーザー マッピングを管理します。](../core/managing-user-mappings.md)   
 [関連アプリケーションの管理](../core/managing-affiliate-applications.md)