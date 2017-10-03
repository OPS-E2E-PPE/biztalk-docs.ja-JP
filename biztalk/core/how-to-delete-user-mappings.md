---
title: "ユーザー マッピングを削除する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- maps [SSO], deleting
- managing [SSO maps], deleting user maps
ms.assetid: de511113-b0b0-4920-91dc-4c9e380fda58
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a4c8cb8766080a715ba309f2aa2736957b6ff54
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-delete-user-mappings"></a>ユーザー マッピングを削除する方法
以下のコマンドを使用して、XML ファイルで指定された 1 つ以上のユーザー マッピングを削除できます。 XML ファイルの例を次に示します。  
  
```  
<sso>  
<mapping>  
<windowsDomain>domain</windowsDomain>   
<windowsUserId>WindowsUserName</windowsUserId>   
<externalApplication>Application name1</externalApplication>   
<externalUserId>App1UserName</externalUserId>   
</mapping>  
<mapping>  
<windowsDomain>domain</windowsDomain>   
<windowsUserId>WindowsUserName</windowsUserId>   
<externalApplication>Application name2</externalApplication>   
<externalUserId>App2UserName</externalUserId>   
</mapping>  
</sso>  
```  
  
 ユーザーが、アプリケーション ユーザー アカウントのメンバーでないか Active Directory に登録されていない場合、このコマンドを使用してユーザー マッピングを SSO データベースから削除します。  
  
 ユーザー アカウントを変更する場合は、このコマンドを使用して、古いユーザー マッピングを削除してから、新しいユーザー アカウントのマッピングを作成する必要があります。 マッピングを作成する詳細については、次を参照してください。[ユーザー マッピングを作成する方法](../core/how-to-create-user-mappings.md)です。  
  
### <a name="to-delete-user-mappings-using-the-administration-utility"></a>管理ユーティリティを使用してユーザー マッピングを削除するには  
  
1.  **開始** メニューのをクリックして**実行**、し、入力**cmd**です。  
  
2.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは\<*ドライブ*>: \program files \common files \enterprise シングル サインオンします。  
  
3.  型**ssomanage – deletemappings *\<マッピング ファイル名 >***ここで、 \<*マッピング ファイル名*> を含むファイルの名前を指定しますユーザー マッピングを削除します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
### <a name="to-delete-a-specific-user-mapping-using-the-administration-utility"></a>管理ユーティリティを使用して特定のユーザー マッピングを削除するには  
  
1.  **開始** メニューのをクリックして**実行**、し、入力**cmd**です。  
  
2.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは*\<ドライブ*>: \program files \common files \enterprise シングル サインオンします。  
  
3.  型 **ssomanage – deletemapping *\<ドメイン >*\\*\<ユーザー名 >*  *\<アプリケーション名 >***ここで、 *\<ドメイン >*は Windows ドメイン ユーザー アカウントを*\<ユーザー名 >*は、Windows ユーザー名と\<*アプリケーション名*> はユーザー マッピングを削除する特定のアプリケーションです。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
### <a name="to-delete-a-user-mapping-using-the-client-utility"></a>クライアント ユーティリティを使用してユーザー マッピングを削除するには  
  
1.  **開始** メニューのをクリックして**実行**、し、入力**cmd**です。  
  
2.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは*\<ドライブ*>: \program files \common files \enterprise シングル サインオンします。  
  
3.  型**ssoclient – deletemapping *\<アプリケーション名 >***ここで、 *\<アプリケーション名 >*関連の名前を指定します。ユーザー マッピングを削除するアプリケーション。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [SSO マッピング](../core/sso-mappings.md)   
 [関連アプリケーションの管理](../core/managing-affiliate-applications.md)   
 [ユーザー マッピングを管理します。](../core/managing-user-mappings.md)