---
title: ユーザー マッピングを作成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eb91879c-73f4-4e9e-9e5b-534f48cd5584
caps.latest.revision: ''
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: 89fd7ab2ca83d23a37944447997becd2d3f008c2
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-create-user-mappings"></a>ユーザー マッピングを作成する方法
使用して、 **createmappings** XML ファイルで指定された、1 つまたは複数のユーザー マッピングを作成するコマンド。 XML ファイルの例を次に示します。  
  
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
  
 ユーザー アカウントが変更された場合は、このコマンドを使用して、新しいユーザー アカウントのマッピングを作成する必要があります。 また、古いユーザー マッピングを削除する必要もあります。 マッピングの削除の詳細については、次を参照してください。[ユーザー マッピングを削除する方法](../esso/how-to-delete-user-mappings.md)です。  
  
 ユーザー マッピングを作成した後に、シングル サインオン (SSO) システムでこのマッピングを使用する前に有効にあります。 詳細については、次を参照してください。[ユーザー マッピングを有効にする方法](../esso/how-to-enable-a-user-mapping.md)です。  
  
> [!IMPORTANT]
>  ユーザー マッピングでは、ドメイン グループのみがサポートされています。  
  
### <a name="to-create-user-mappings-using-the-administration-utility"></a>管理ユーティリティを使用してユーザー マッピングを作成するには  
  
1.  をクリックして **開始**, 、 をクリックして **実行**, 、型 `cmd`, 、ENTER キーを押します。  
  
2.  コマンド プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。  
  
     既定のインストール ディレクトリは\<*ドライブ*>: \program files \common files \enterprise シングル サインオンします。  
  
3.  型`ssomanage –createmappings <mappings file name>`ここで、 *\<マッピング ファイル名 >*を作成するユーザー マッピングを格納しているファイルの名前を指定します。  
  
### <a name="to-create-user-mappings-using-the-client-utility"></a>クライアント ユーティリティを使用してユーザー マッピングを作成するには  
  
1.  をクリックして **開始**, 、 をクリックして **実行**, 、型 `cmd`, 、ENTER キーを押します。  
  
2.  コマンド プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。  
  
     既定のインストール ディレクトリは\<*ドライブ*>: \program files \common files \enterprise シングル サインオンします。  
  
3.  型`ssoclient –setcredentials <application name >`ここで、 *\<アプリケーション名 >*ユーザーがマッピングを作成する関連アプリケーションの名前を指定します。  
  
## <a name="see-also"></a>参照  
 [SSO マッピング](../esso/sso-mappings.md)   
 [関連アプリケーションの管理](../esso/managing-affiliate-applications.md)   
 [ユーザー マッピングの管理](../esso/managing-user-mappings.md)