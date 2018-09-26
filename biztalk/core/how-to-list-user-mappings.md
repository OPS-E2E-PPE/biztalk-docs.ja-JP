---
title: ユーザー マッピングを一覧表示する方法 |Microsoft Docs
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
ms.openlocfilehash: cef1fbe44c9c3ddbe5458a92644f9ea39534789e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974107"
---
# <a name="how-to-list-user-mappings"></a>ユーザー マッピングを一覧表示する方法
ここで示すコマンドを使用すると、指定したユーザーの既存のマッピングすべてを一覧表示できます。  
  
 この作業を行うには、SSO 管理者、アプリケーション管理者、SSO 関連管理者、またはユーザーである必要があります。  
  
 有効なユーザー マッピングは、(e) が表示されます\<*ドメイン*\>\\*\<username\>* 無効になっているときに、(D)としてユーザーマッピングが表示されます\<*ドメイン*\>\\*\<username\>* します。  
  
### <a name="to-list-user-mappings-using-the-administration-utility"></a>管理ユーティリティを使用してユーザー マッピングを一覧表示するには  
  
1. **開始** メニューのをクリックして**実行**、し、入力**cmd**します。  
  
2. コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは\<*ドライブ*\>: \Program Files\Common \enterprise シングル サインオンします。  
  
3. 次のいずれかの操作を行います。  
  
   - 型**ssomanage – listmappings *\<ドメイン\>\\< ユーザー名\>*** 関連アプリケーションでの特定のユーザーがすべてのマッピングを一覧表示where に自分が属している*\<ドメイン\>* は Microsoft Windows ドメイン ユーザー アカウントと*\<username\>* が、Windows ユーザー名のユーザー マッピングを一覧表示します。 ユーザーが関連管理者または SSO 管理者である場合にこのコマンドを実行すると、すべての関連アプリケーションを対象に、そのユーザーのすべてのマッピングが一覧表示されます。  
  
      スイッチまたは  
  
   - 型**ssomanage – listmappings *\<アプリケーション名\>*** 特定のアプリケーションのすべてのユーザー マッピングを一覧表示します。  
  
      スイッチまたは  
  
   - アプリケーション管理者の場合は、入力**ssomanage – listmappings *\<ドメイン\>\\< ユーザー名\>*  *\<アプリケーション名\>*** 管理者は、関連アプリケーションで特定のユーザーをすべてのマッピングを一覧表示します。  
  
   > [!NOTE]
   >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
### <a name="to-list-user-mappings-using-the-client-utility"></a>クライアント ユーティリティを使用してユーザー マッピングを一覧表示するには  
  
1.  **開始** メニューのをクリックして**実行**、し、入力**cmd**します。  
  
2.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは\<*ドライブ*\>: \Program Files\Common \enterprise シングル サインオンします。  
  
3.  型**ssoclient – listmappings**があるすべてのマッピングを一覧表示します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [ユーザー マッピングを作成する方法](../core/how-to-create-user-mappings.md)   
 [SSO マッピング](../core/sso-mappings.md)   
 [関連アプリケーションの管理](../core/managing-affiliate-applications.md)   
 [ユーザー マッピングの管理](../core/managing-user-mappings.md)