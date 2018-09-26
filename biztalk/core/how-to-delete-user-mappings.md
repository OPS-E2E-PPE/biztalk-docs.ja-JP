---
title: ユーザー マッピングを削除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maps [SSO], deleting
- managing [SSO maps], deleting user maps
ms.assetid: de511113-b0b0-4920-91dc-4c9e380fda58
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 034f587d8c7d87f5fa6aa7e5e33ca4ef147d9f9b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014387"
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
  
 ユーザー アカウントを変更する場合は、このコマンドを使用して、古いユーザー マッピングを削除してから、新しいユーザー アカウントのマッピングを作成する必要があります。 マッピングを作成する詳細については、次を参照してください。[ユーザー マッピングを作成する方法](../core/how-to-create-user-mappings.md)します。  
  
### <a name="to-delete-user-mappings-using-the-administration-utility"></a>管理ユーティリティを使用してユーザー マッピングを削除するには  
  
1. **開始** メニューのをクリックして**実行**、し、入力**cmd**します。  
  
2. コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは\<*ドライブ*\>: \Program Files\Common \enterprise シングル サインオンします。  
  
3. 型<strong>ssomanage – deletemappings *\<ファイル名をマッピング\></strong><em>ここで、 \<</em>ファイル名をマッピング*\>は削除するユーザー マッピングを格納しているファイルの名前。  
  
   > [!NOTE]
   >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
### <a name="to-delete-a-specific-user-mapping-using-the-administration-utility"></a>管理ユーティリティを使用して特定のユーザー マッピングを削除するには  
  
1. **開始** メニューのをクリックして**実行**、し、入力**cmd**します。  
  
2. コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは*\<ドライブ*\>: \Program Files\Common \enterprise シングル サインオンします。  
  
3. 型 **ssomanage – deletemapping *\<ドメイン\>*\\*\<username\> *   *\<アプリケーション名\>**<em>ここで、 *\<ドメイン\></em>が Windows ドメイン ユーザー アカウントの *\<ユーザー名\>* は、Windows ユーザー名と\<* アプリケーション名*\>はユーザー マッピングを削除する特定のアプリケーションです。  
  
   > [!NOTE]
   >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
### <a name="to-delete-a-user-mapping-using-the-client-utility"></a>クライアント ユーティリティを使用してユーザー マッピングを削除するには  
  
1. **開始** メニューのをクリックして**実行**、し、入力**cmd**します。  
  
2. コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは*\<ドライブ*\>: \Program Files\Common \enterprise シングル サインオンします。  
  
3. 型 * * ssoclient – deletemapping *\<アプリケーション名\>**<em>ここで、*\<アプリケーション名\></em>を削除する関連アプリケーションの名前を指定しますユーザーのマッピング。  
  
   > [!NOTE]
   >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [SSO マッピング](../core/sso-mappings.md)   
 [関連アプリケーションの管理](../core/managing-affiliate-applications.md)   
 [ユーザー マッピングの管理](../core/managing-user-mappings.md)