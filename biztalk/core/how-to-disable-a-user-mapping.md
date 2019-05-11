---
title: ユーザー マッピングを無効にする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- disabling, maps
- managing [SSO maps], disabling
- maps [SSO], disabling
ms.assetid: 9b6eaff2-674b-49f7-8d5c-3e040a7dc7f8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 14d1715268630f4eed26f8004fc3d61cde15830b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338116"
---
# <a name="how-to-disable-a-user-mapping"></a>ユーザー マッピングを無効にする方法
指定したマッピングに関連付けられているすべての操作をオフにする場合に、ユーザーのマッピングを無効にすることができます。 削除する前に、ユーザーのマッピングを無効にする必要があります。  
  
 ユーザー マッピングを無効にすると、(D) として表示されます*\<ドメイン\>\\< ユーザー名\>* ユーザー マッピングの一覧を表示する場合。  
  
### <a name="to-disable-a-user-mapping-using-the-administration-utility"></a>管理ユーティリティを使用してユーザー マッピングを無効にするには  
  
1. **開始** メニューのをクリックして**実行**、し、入力**cmd**します。  
  
2. コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは*\<ドライブ\>*: \Program Files\Common \enterprise シングル サインオンします。  
  
3. 型**ssomanage – disablemapping *\<ドメイン\>*\\*\<username\> \<アプリケーション名\>** <em>ここで、*\<ドメイン\></em>ユーザー アカウントの Windows ドメインと*\<username\>* が、資格情報を無効にする Windows ユーザー名と*\<アプリケーション名\>* ユーザー マッピングを削除する関連アプリケーションの名前を指定します。  
  
   > [!NOTE]
   >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
### <a name="to-disable-a-user-mapping-using-the-client-utility"></a>クライアント ユーティリティを使用してユーザー マッピングを無効にするには  
  
1. **開始** メニューのをクリックして**実行**、し、入力**cmd**します。  
  
2. コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは*\<ドライブ\>*: \Program Files\Common \enterprise シングル サインオンします。  
  
3. 型 * * ssoclient – disablemapping *\<アプリケーション名\>**<em>ここで、*\<アプリケーション名\></em>を削除する関連アプリケーションの名前を指定しますユーザーのマッピング。  
  
   > [!NOTE]
   >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [SSO マッピング](../core/sso-mappings.md)   
 [関連アプリケーションの管理](../core/managing-affiliate-applications.md)   
 [ユーザー マッピングの管理](../core/managing-user-mappings.md)