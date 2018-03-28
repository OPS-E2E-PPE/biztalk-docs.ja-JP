---
title: ユーザー マッピングを作成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maps [SSO], creating
- managing [SSO maps], creating user maps
ms.assetid: c2e9f0db-920b-4d89-8e1e-5dc92805fd23
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 019adf0cd41c643ac77790c96a3450bb967ddd6b
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
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
  
1.  **開始** ] メニューのをクリックして **実行**, 、し、入力 **cmd**します。  
  
2.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは\<*ドライブ*\>: \program files \common files \enterprise シングル サインオンします。  
  
3.  型 * * ssomanage – createmappings *\<マッピング ファイル名\>* * *、どこで*\<マッピング ファイル名\>*を作成するユーザー マッピングが格納されているファイルの名前を指定します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
### <a name="to-create-user-mappings-using-the-client-utility"></a>クライアント ユーティリティを使用してユーザー マッピングを作成するには  
  
1.  **開始** ] メニューのをクリックして **実行**, 、し、入力 **cmd**します。  
  
2.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは\<*ドライブ*\>: \program files \common files \enterprise シングル サインオンします。  
  
3.  型 * * ssoclient – setcredentials *\<アプリケーション名\>* * *、どこで*\<アプリケーション名\>*ユーザーがマッピングを作成する関連アプリケーションの名前を指定します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [SSO マッピング](../core/sso-mappings.md)   
 [関連アプリケーションの管理](../core/managing-affiliate-applications.md)   
 [ユーザー マッピングの管理](../core/managing-user-mappings.md)