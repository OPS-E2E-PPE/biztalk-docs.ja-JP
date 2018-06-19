---
title: ユーザー マッピングを削除する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82c4cdff-b82d-4cfd-8e20-220a2fe78656
caps.latest.revision: 3
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: a9d0a31c3dbc9d5980f59d9f30d20ec15f603a38
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "30251086"
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
  
 ユーザーは、アプリケーション ユーザー アカウントのメンバーではないか、Active Directory に存在しない場合、は、資格情報データベースからのユーザー マッピングを削除するこのコマンドを使用する必要があります。  
  
 ユーザー アカウントを変更する場合は、このコマンドを使用して、古いユーザー マッピングを削除してから、新しいユーザー アカウントのマッピングを作成する必要があります。 マッピングを作成する詳細については、次を参照してください。[ユーザー マッピングを作成する方法](../esso/how-to-create-user-mappings.md)です。  
  
### <a name="to-delete-user-mappings-using-the-administration-utility"></a>管理ユーティリティを使用してユーザー マッピングを削除するには  
  
1.  をクリックして **開始**, 、 をクリックして **実行**, 、型 `cmd`, 、ENTER キーを押します。  
  
2.  コマンド プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。  
  
     既定のインストール ディレクトリは\<*ドライブ*>: \program files \common files \enterprise シングル サインオンします。  
  
3.  型`ssomanage –deletemappings <mappings file name>`ここで、 \<*マッピング ファイル名*> を削除するユーザー マッピングを格納しているファイルの名前を指定します。  
  
### <a name="to-delete-a-specific-user-mapping-using-the-administration-utility"></a>管理ユーティリティを使用して特定のユーザー マッピングを削除するには  
  
1.  をクリックして **開始**, 、 をクリックして **実行**, 、型 `cmd`, 、ENTER キーを押します。  
  
2.  コマンド プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。  
  
     既定のインストール ディレクトリは*\<ドライブ >*: \program files \common files \enterprise シングル サインオンします。  
  
3.  型`ssomanage –deletemapping <domain>\<username> <application name>`ここで、 *\<ドメイン >* は Windows ドメイン ユーザー アカウントを*\<ユーザー名 >* は、Windows ユーザー名と\< *アプリケーション名*> は、特定のユーザー マッピングを削除するアプリケーション。  
  
### <a name="to-delete-a-user-mapping-using-the-client-utility"></a>クライアント ユーティリティを使用してユーザー マッピングを削除するには  
  
1.  をクリックして **開始**, 、 をクリックして **実行**, 、型 `cmd`, 、ENTER キーを押します。  
  
2.  コマンド プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。  
  
     既定のインストール ディレクトリは*\<ドライブ >*: \program files \common files \enterprise シングル サインオンします。  
  
3.  型`ssoclient –deletemapping <application name>`ここで、 *\<アプリケーション名 >* ユーザー マッピングを削除する関連アプリケーションの名前を指定します。  
  
## <a name="see-also"></a>参照  
 [SSO マッピング](../esso/sso-mappings.md)   
 [関連アプリケーションの管理](../esso/managing-affiliate-applications.md)   
 [ユーザー マッピングの管理](../esso/managing-user-mappings.md)