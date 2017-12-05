---
title: "関連アプリケーションを一覧表示する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [SSO applications], listing applications
- applications [SSO], listing applications
ms.assetid: b51ff597-824e-4488-a47f-3a9b3d4437c6
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f6c4d4e4118bfe5f5cab7a9c44e770dd12656c7
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-list-affiliate-applications"></a>関連アプリケーションを一覧表示する方法
ここで示すコマンドを使用すると、関連アプリケーションをすべて一覧表示できます。 ユーザーがアプリケーション管理者アカウントのメンバーである場合、このコマンドを実行すると、そのユーザーが管理者であるアプリケーションだけが表示されます。  
  
### <a name="to-list-affiliate-applications-using-the-administration-utility"></a>管理ユーティリティを使用して関連アプリケーションを一覧表示するには  
  
1.  **開始** メニューのをクリックして**実行**、し、入力**cmd**です。  
  
2.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは\<*ドライブ*\>: \program files \common files \enterprise シングル サインオンします。  
  
3.  型**ssomanage-listapps [all]**場所**すべて**省略可能なパラメーターで、構成ストアの機能を使用してアプリケーションにも表示されます。 このコマンドを実行するユーザーがアプリケーション管理者である場合、そのユーザーが管理者であるアプリケーションだけが一覧表示されます。 このコマンドを実行するユーザーが関連管理者または SSO 管理者である場合、すべての関連アプリケーションが一覧表示されます。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
### <a name="to-list-affiliate-applications-using-the-client-utility"></a>クライアント ユーティリティを使用して関連アプリケーションを一覧表示するには  
  
1.  **開始** メニューのをクリックして**実行**、し、入力**cmd**です。  
  
2.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは\<*ドライブ*\>: \program files \common files \enterprise シングル サインオンします。  
  
3.  型**ssoclient – listapps**関連アプリケーションを一覧表示します。 これによって一覧表示されるのは、このタスクを実行しているユーザーがメンバーである関連アプリケーションだけです。つまり、ユーザーは一覧表示する関連アプリケーションのアプリケーション ユーザー グループ アカウントに属している必要があります。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [SSO 関連アプリケーション](../core/sso-affiliate-applications.md)   
 [関連アプリケーションを作成する方法](../core/how-to-create-an-affiliate-application.md)   
 [ユーザー マッピングを管理します。](../core/managing-user-mappings.md)   
 [関連アプリケーションの管理](../core/managing-affiliate-applications.md)