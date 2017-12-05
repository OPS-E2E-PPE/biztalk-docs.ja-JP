---
title: "ユーザー マッピングの資格情報を設定する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- maps [SSO], credentials
- managing [SSO maps], configuring credentials
ms.assetid: 75b29114-56b6-4db0-8666-61cf6c675401
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4853499dbfd85cd5114212e37f4d22770d64a22
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-set-credentials-for-a-user-mapping"></a>ユーザー マッピングの資格情報を設定する方法
ここで示すコマンドを使用すると、ユーザーが特定のアプリケーションにアクセスするための資格情報を設定できます。  
  
 このコマンドでは、入力したパスワードは表示されません。  
  
 ユーザー マッピングが既に存在する場合、このコマンドは、その既存のマッピングに対して資格情報を設定します。 ユーザー マッピングを作成していない場合、SSO システムからアプリケーションのユーザー ID を入力するよう要求されます。  
  
### <a name="to-set-credentials-for-a-user-mapping"></a>ユーザー マッピングの資格情報を設定するには  
  
1.  **開始** メニューのをクリックして**実行**、し、入力**cmd**です。  
  
2.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは**\<ドライブ\>**: \program files \common files \enterprise シングル サインオンします。  
  
3.  型**ssomanage – setcredentials\<ドメイン\>\\< ユーザー名\> \<applicationname\>**ここで、  **\<ドメイン\>**は Windows ドメイン ユーザー アカウントを **\<username\>** は、Windows ユーザー名と **\<applicationname\>** は、特定のアプリケーションの資格情報を設定します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
4.  SSO システムからユーザーの資格情報が要求されたら、指定したアプリケーションのユーザー パスワードを入力します。  
  
5.  ユーザー マッピングを作成していない場合、SSO システムからアプリケーションのユーザー ID を入力するよう要求されます。  
  
### <a name="to-set-credentials-for-a-user-mapping-from-the-client-utility"></a>クライアント ユーティリティを使用してユーザー マッピングの資格情報を設定するには  
  
1.  **開始** メニューのをクリックして**実行**、し、入力**cmd**です。  
  
2.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは**\<ドライブ\>**: \program files \common files \enterprise シングル サインオンします。  
  
3.  型**ssoclient-setcredentials\<アプリケーション名\>**ここで、 **\<アプリケーション名\>**関連アプリケーションの名前を指定します。ユーザー マッピングを削除します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [ユーザー マッピングを作成する方法](../core/how-to-create-user-mappings.md)   
 [SSO マッピング](../core/sso-mappings.md)   
 [関連アプリケーションの管理](../core/managing-affiliate-applications.md)   
 [ユーザー マッピングの管理](../core/managing-user-mappings.md)