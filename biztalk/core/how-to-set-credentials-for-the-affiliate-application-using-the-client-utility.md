---
title: "クライアント ユーティリティを使用して関連アプリケーションの資格情報を設定する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [SSO applications], configuring credentials
- SSOClient [SSO], configuring credentials
- applications [SSO], credentials
ms.assetid: 454b6257-3538-40be-840c-00172a2c1dce
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 31ba167bc35d01907166bb6610720e03be654c4d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-set-credentials-for-the-affiliate-application-using-the-client-utility"></a>クライアント ユーティリティを使用して関連アプリケーションの資格情報を設定する方法
ここで示すコマンドを使用すると、ユーザーが特定のアプリケーションにアクセスできるようにユーザーの資格情報を設定できます。 また、このコマンドにより、マッピングが自動的に有効になります。  
  
 このコマンドでは、入力したパスワードは表示されません。  
  
 ユーザー マッピングが既に存在する場合、このコマンドにより、その既存のマッピングに対して資格情報が設定されます。 ユーザー マッピングを作成していない場合、SSO システムからアプリケーションのユーザー ID を入力するよう要求されます。  
  
### <a name="to-set-credentials-for-the-affiliate-application-using-the-client-utility"></a>クライアント ユーティリティを使用して関連アプリケーションに資格情報を設定するには  
  
1.  **開始** メニューのをクリックして**実行**、し、入力**cmd**です。  
  
2.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは*\<ドライブ >*: \program files \common files \enterprise シングル サインオンします。  
  
3.  型**ssoclient – setcredentials\<アプリケーション名 >**ここで、 **\<アプリケーション名 >**は、特定のアプリケーションの資格情報を設定します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
4.  ユーザーの資格情報を要求されたら、このアプリケーションのユーザー パスワードを入力します。  
  
5.  ユーザー マッピングを作成していない場合、SSO システムからアプリケーションのユーザー ID を入力するよう要求されます。  
  
## <a name="see-also"></a>参照  
 [SSO 関連アプリケーション](../core/sso-affiliate-applications.md)   
 [関連アプリケーションの管理](../core/managing-affiliate-applications.md)