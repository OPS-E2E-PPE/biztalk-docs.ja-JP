---
title: "ユーザー マッピングを一覧表示する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [SSO maps], listing maps
- maps [SSO], listing maps
ms.assetid: f9b73785-3a59-45c8-9e88-d2d16b5a46aa
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f6041b40c2b6a3fa468462478754079d41881bc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-list-user-mappings"></a>ユーザー マッピングを一覧表示する方法
ここで示すコマンドを使用すると、指定したユーザーの既存のマッピングすべてを一覧表示できます。  
  
 この作業を行うには、SSO 管理者、アプリケーション管理者、SSO 関連管理者、またはユーザーである必要があります。  
  
 (E) として表示される有効なユーザー マッピング\<*ドメイン*>\\*\<ユーザー名 >*無効になっているときに、(D) として表示されるユーザー マッピング\<*ドメイン*>\\*\<ユーザー名 >*です。  
  
### <a name="to-list-user-mappings-using-the-administration-utility"></a>管理ユーティリティを使用してユーザー マッピングを一覧表示するには  
  
1.  **開始** メニューのをクリックして**実行**、し、入力**cmd**です。  
  
2.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは\<*ドライブ*>: \program files \common files \enterprise シングル サインオンします。  
  
3.  次のいずれかの操作を行います。  
  
    -   型**ssomanage – listmappings *\<ドメイン >\\< ユーザー名\>*** 特定のユーザーが登録したが属している関連アプリケーションがすべてのマッピングを一覧表示where を*\<ドメイン >*は、Microsoft Windows ドメイン ユーザー アカウントと*\<ユーザー名 >*を一覧表示する Windows ユーザー名には、ユーザーのマッピング。 ユーザーが関連管理者または SSO 管理者である場合にこのコマンドを実行すると、すべての関連アプリケーションを対象に、そのユーザーのすべてのマッピングが一覧表示されます。  
  
         または  
  
    -   型**ssomanage – listmappings *\<アプリケーション名 >*** 特定のアプリケーションのすべてのユーザー マッピングを一覧表示します。  
  
         または  
  
    -   アプリケーション管理者の場合は、入力**ssomanage – listmappings *\<ドメイン >\\< ユーザー名\>* *\<アプリケーション名 >*** 特定のユーザーが管理者になっている関連アプリケーションがすべてのマッピングを一覧表示します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
### <a name="to-list-user-mappings-using-the-client-utility"></a>クライアント ユーティリティを使用してユーザー マッピングを一覧表示するには  
  
1.  **開始** メニューのをクリックして**実行**、し、入力**cmd**です。  
  
2.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは\<*ドライブ*>: \program files \common files \enterprise シングル サインオンします。  
  
3.  型**ssoclient – listmappings**があるすべてのマッピングを一覧表示します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [ユーザー マッピングを作成する方法](../core/how-to-create-user-mappings.md)   
 [SSO マッピング](../core/sso-mappings.md)   
 [関連アプリケーションの管理](../core/managing-affiliate-applications.md)   
 [ユーザー マッピングを管理します。](../core/managing-user-mappings.md)