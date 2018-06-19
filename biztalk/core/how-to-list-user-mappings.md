---
title: ユーザー マッピングを一覧表示する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [SSO maps], listing maps
- maps [SSO], listing maps
ms.assetid: f9b73785-3a59-45c8-9e88-d2d16b5a46aa
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04f988e9f63cccf27c42a33727d86452d34915aa
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972152"
---
# <a name="how-to-list-user-mappings"></a>ユーザー マッピングを一覧表示する方法
ここで示すコマンドを使用すると、指定したユーザーの既存のマッピングすべてを一覧表示できます。  
  
 この作業を行うには、SSO 管理者、アプリケーション管理者、SSO 関連管理者、またはユーザーである必要があります。  
  
 (E) として表示される有効なユーザー マッピング\<*ドメイン*\>\\*\<username\>* 無効になっているときに、(D)としてユーザーマッピングが表示されます\<*ドメイン*\>\\*\<username\>* です。  
  
### <a name="to-list-user-mappings-using-the-administration-utility"></a>管理ユーティリティを使用してユーザー マッピングを一覧表示するには  
  
1.  **開始** メニューのをクリックして**実行**、し、入力**cmd**です。  
  
2.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは\<*ドライブ*\>: \program files \common files \enterprise シングル サインオンします。  
  
3.  次のいずれかの操作を行います。  
  
    -   型**ssomanage – listmappings *\<ドメイン\>\\< ユーザー名\>*** 関連アプリケーション内の特定のユーザーがすべてのマッピングを一覧表示登録したが属している、where *\<ドメイン\>* は、Microsoft Windows ドメイン ユーザー アカウントと *\<username\>* は、ユーザー マッピングを一覧表示する Windows ユーザー名。 ユーザーが関連管理者または SSO 管理者である場合にこのコマンドを実行すると、すべての関連アプリケーションを対象に、そのユーザーのすべてのマッピングが一覧表示されます。  
  
         または  
  
    -   型**ssomanage – listmappings *\<アプリケーション名\>*** 特定のアプリケーションのすべてのユーザー マッピングを一覧表示します。  
  
         または  
  
    -   アプリケーション管理者の場合は、入力**ssomanage – listmappings *\<ドメイン\>\\< ユーザー名\>*  *\<アプリケーション名\>*** 特定のユーザーが管理者になっている関連アプリケーションがすべてのマッピングを一覧表示します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
### <a name="to-list-user-mappings-using-the-client-utility"></a>クライアント ユーティリティを使用してユーザー マッピングを一覧表示するには  
  
1.  **開始** メニューのをクリックして**実行**、し、入力**cmd**です。  
  
2.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは\<*ドライブ*\>: \program files \common files \enterprise シングル サインオンします。  
  
3.  型**ssoclient – listmappings**があるすべてのマッピングを一覧表示します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [ユーザー マッピングを作成する方法](../core/how-to-create-user-mappings.md)   
 [SSO マッピング](../core/sso-mappings.md)   
 [関連アプリケーションの管理](../core/managing-affiliate-applications.md)   
 [ユーザー マッピングの管理](../core/managing-user-mappings.md)