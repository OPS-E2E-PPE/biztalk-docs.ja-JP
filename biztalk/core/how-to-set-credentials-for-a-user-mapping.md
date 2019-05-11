---
title: ユーザー マッピングの資格情報を設定する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maps [SSO], credentials
- managing [SSO maps], configuring credentials
ms.assetid: 75b29114-56b6-4db0-8666-61cf6c675401
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 228661c4e35175cf5f2e05c86bb0e10123f8e468
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383959"
---
# <a name="how-to-set-credentials-for-a-user-mapping"></a>ユーザー マッピングの資格情報を設定する方法
このコマンドを使用すると、特定のアプリケーションにアクセスするのにユーザーの資格情報を設定できます。  
  
 このコマンドでは、入力すると、パスワードは表示されません。  
  
 ユーザー マッピングが既に存在する場合、このコマンドは、その既存のマッピングの資格情報を設定します。 ユーザー マッピングを作成していない場合、SSO システムのアプリケーションのユーザー ID を求められます。  
  
### <a name="to-set-credentials-for-a-user-mapping"></a>ユーザー マッピングの資格情報を設定するには  
  
1.  **開始** メニューのをクリックして**実行**、し、入力**cmd**します。  
  
2.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは**\<ドライブ\>**: \Program Files\Common \enterprise シングル サインオンします。  
  
3.  型**ssomanage – setcredentials\<ドメイン\>\\< ユーザー名\> \<applicationname\>** ここで、  **\<ドメイン\>** が Windows ドメイン ユーザー アカウントの**\<username\>** は、Windows ユーザー名と**\<applicationname\>** は特定のアプリケーションの資格情報を設定します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
4.  SSO システムでは、ユーザーの資格情報の入力を求められたらは、このアプリケーションのユーザーのパスワードを入力します。  
  
5.  ユーザー マッピングを作成していない場合、SSO システムのアプリケーションのユーザー ID を求められます。  
  
### <a name="to-set-credentials-for-a-user-mapping-from-the-client-utility"></a>クライアント ユーティリティからのユーザー マッピングの資格情報を設定するには  
  
1.  **開始** メニューのをクリックして**実行**、し、入力**cmd**します。  
  
2.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは**\<ドライブ\>**: \Program Files\Common \enterprise シングル サインオンします。  
  
3.  型**ssoclient-setcredentials\<アプリケーション名\>** ここで、 **\<アプリケーション名\>** 関連アプリケーションの名前を指定します。ユーザー マッピングを削除します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [ユーザー マッピングを作成する方法](../core/how-to-create-user-mappings.md)   
 [SSO マッピング](../core/sso-mappings.md)   
 [関連アプリケーションの管理](../core/managing-affiliate-applications.md)   
 [ユーザー マッピングの管理](../core/managing-user-mappings.md)