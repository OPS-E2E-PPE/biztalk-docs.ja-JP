---
title: クライアント ユーティリティを使用して関連アプリケーションの資格情報を設定する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [SSO applications], configuring credentials
- SSOClient [SSO], configuring credentials
- applications [SSO], credentials
ms.assetid: 454b6257-3538-40be-840c-00172a2c1dce
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: abc8c329b46e5eab5f04f5082064f1dea63505bd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334520"
---
# <a name="how-to-set-credentials-for-the-affiliate-application-using-the-client-utility"></a>クライアント ユーティリティを使用して関連アプリケーションの資格情報を設定する方法
このコマンドを使用して、ユーザーが特定のアプリケーションにアクセスできるように、ユーザーの資格情報を設定します。 このコマンドも自動的にマッピングを有効にします。  
  
 このコマンドでは、入力すると、パスワードは表示されません。  
  
 ユーザー マッピングが既に存在する場合、このコマンドはその既存のマッピングの資格情報を設定します。 ユーザー マッピングを作成していない場合、SSO システムのアプリケーションのユーザー ID を求められます。  
  
### <a name="to-set-credentials-for-the-affiliate-application-using-the-client-utility"></a>クライアント ユーティリティを使用して関連アプリケーションの資格情報を設定するには  
  
1.  **開始** メニューのをクリックして**実行**、し、入力**cmd**します。  
  
2.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは*\<ドライブ\>*: \Program Files\Common \enterprise シングル サインオンします。  
  
3.  型**ssoclient – setcredentials\<アプリケーション名\>** ここで、 **\<アプリケーション名\>** 対象となる特定のアプリケーションには資格情報を設定します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
4.  ユーザーの資格情報が表示されたら、このアプリケーションのユーザーのパスワードを入力します。  
  
5.  ユーザー マッピングを作成していない場合、SSO システムのアプリケーションのユーザー ID を求められます。  
  
## <a name="see-also"></a>参照  
 [SSO 関連アプリケーション](../core/sso-affiliate-applications.md)   
 [関連アプリケーションの管理](../core/managing-affiliate-applications.md)