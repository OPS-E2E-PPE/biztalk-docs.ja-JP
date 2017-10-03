---
title: "ユーザー マッピングを作成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- maps [SSO], creating
- managing [SSO maps], creating user maps
ms.assetid: c2e9f0db-920b-4d89-8e1e-5dc92805fd23
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ffbcc0cb5ca00eb0b461f77c36397179f5c91f7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-user-mappings"></a>ユーザー マッピングを作成する方法
ここで示すコマンドを使用すると、XML ファイルで指定された 1 つ以上のユーザー マッピングを作成できます。 XML ファイルの例を次に示します。  
  
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
  
 ユーザー アカウントが変更された場合は、このコマンドを使用して、新しいユーザー アカウントのマッピングを作成する必要があります。 また、古いユーザー マッピングを削除する必要もあります。 マッピングの削除の詳細については、次を参照してください。[ユーザー マッピングを削除する方法](../core/how-to-delete-user-mappings.md)です。  
  
 作成したユーザー マッピングを SSO システムで使用するには、ユーザー マッピングを有効にする必要があります。 詳細については、次を参照してください。[ユーザー マッピングを有効にする方法](../core/how-to-enable-a-user-mapping.md)です。  
  
> [!IMPORTANT]
>  ユーザー マッピングでは、ドメイン グループのみがサポートされています。  
  
### <a name="to-create-user-mappings-using-the-administration-utility"></a>管理ユーティリティを使用してユーザー マッピングを作成するには  
  
1.  **開始** メニューのをクリックして**実行**、し、入力**cmd**です。  
  
2.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは\<*ドライブ*>: \program files \common files \enterprise シングル サインオンします。  
  
3.  型**ssomanage – createmappings *\<マッピング ファイル名 >***ここで、 *\<マッピング ファイル名 >*を含むファイルの名前を指定します、ユーザーのマッピングを作成します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
### <a name="to-create-user-mappings-using-the-client-utility"></a>クライアント ユーティリティを使用してユーザー マッピングを作成するには  
  
1.  **開始** メニューのをクリックして**実行**、し、入力**cmd**です。  
  
2.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは\<*ドライブ*>: \program files \common files \enterprise シングル サインオンします。  
  
3.  型**ssoclient – setcredentials *\<アプリケーション名 >***ここで、 *\<アプリケーション名 >*関連アプリケーションの名前を指定しますユーザーがのマッピングを作成します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [SSO マッピング](../core/sso-mappings.md)   
 [関連アプリケーションの管理](../core/managing-affiliate-applications.md)   
 [ユーザー マッピングを管理します。](../core/managing-user-mappings.md)