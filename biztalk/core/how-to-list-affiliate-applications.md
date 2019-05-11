---
title: 関連アプリケーションの一覧を表示する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [SSO applications], listing applications
- applications [SSO], listing applications
ms.assetid: b51ff597-824e-4488-a47f-3a9b3d4437c6
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b254be21078a53f7efa7291606bdd0038466bb3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336930"
---
# <a name="how-to-list-affiliate-applications"></a>関連アプリケーションの一覧を表示する方法
このコマンドを使用して、すべての関連アプリケーションの一覧します。 ユーザーがアプリケーション管理者アカウントのメンバーである場合は、このコマンドは、ユーザーが管理者アプリケーションをしか表示されません。  
  
### <a name="to-list-affiliate-applications-using-the-administration-utility"></a>管理ユーティリティを使用して関連アプリケーションの一覧表示する  
  
1.  **開始** メニューのをクリックして**実行**、し、入力**cmd**します。  
  
2.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは\<*ドライブ*\>: \Program Files\Common \enterprise シングル サインオンします。  
  
3.  型**ssomanage-listapps [all]** 場所**すべて**省略可能なパラメーターで、構成ストアの機能を使用してアプリケーションにも表示されます。 このコマンドを実行しているユーザーがアプリケーション管理者である場合は、それらが管理者アプリケーションのみが一覧されます。 このコマンドを実行しているユーザーが関連管理者または SSO 管理者の場合は、すべての関連アプリケーションが一覧表示します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
### <a name="to-list-affiliate-applications-using-the-client-utility"></a>クライアント ユーティリティを使用して関連アプリケーションの一覧表示する  
  
1.  **開始** メニューのをクリックして**実行**、し、入力**cmd**します。  
  
2.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは\<*ドライブ*\>: \Program Files\Common \enterprise シングル サインオンします。  
  
3.  型**ssoclient – listapps**を関連アプリケーションを一覧表示します。 つまりに、このタスクを実行するユーザーのメンバーである関連アプリケーションのみを一覧表示これは、その関連アプリケーションのアプリケーション ユーザー グループ アカウントが所属する必要があります。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [SSO 関連アプリケーション](../core/sso-affiliate-applications.md)   
 [関連アプリケーションを作成する方法](../core/how-to-create-an-affiliate-application.md)   
 [ユーザー マッピングの管理](../core/managing-user-mappings.md)   
 [関連アプリケーションの管理](../core/managing-affiliate-applications.md)