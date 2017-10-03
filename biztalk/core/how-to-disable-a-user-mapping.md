---
title: "ユーザー マッピングを無効にする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- disabling, maps
- managing [SSO maps], disabling
- maps [SSO], disabling
ms.assetid: 9b6eaff2-674b-49f7-8d5c-3e040a7dc7f8
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 417a28dd117a51d0bb1d45238f0efc96417c391a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-disable-a-user-mapping"></a>ユーザー マッピングを無効にする方法
指定したマッピングに関連付けられたすべての操作を無効にするときに、ユーザー マッピングを無効にすることができます。 ユーザー マッピングは、削除する前に無効にする必要があります。  
  
 ユーザー マッピングを無効にする場合は (D) として表示されます*\<ドメイン >\\< ユーザー名\>*ユーザー マッピングを一覧表示します。  
  
### <a name="to-disable-a-user-mapping-using-the-administration-utility"></a>管理ユーティリティを使用してユーザー マッピングを無効にするには  
  
1.  **開始** メニューのをクリックして**実行**、し、入力**cmd**です。  
  
2.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは*\<ドライブ >*: \program files \common files \enterprise シングル サインオンします。  
  
3.  型 **ssomanage – disablemapping *\<ドメイン >*\\*\<ユーザー名 >\<アプリケーション名 >*** ここで、 *\<ドメイン >*ユーザー アカウントの Windows ドメインと*\<ユーザー名 >* Windows ユーザー名が無効にするには、資格情報、および*\<アプリケーション名 >*ユーザー マッピングを削除する関連アプリケーションの名前を指定します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
### <a name="to-disable-a-user-mapping-using-the-client-utility"></a>クライアント ユーティリティを使用してユーザー マッピングを無効にするには  
  
1.  **開始** メニューのをクリックして**実行**、し、入力**cmd**です。  
  
2.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは*\<ドライブ >*: \program files \common files \enterprise シングル サインオンします。  
  
3.  型**ssoclient – disablemapping *\<アプリケーション名 >***ここで、 *\<アプリケーション名 >*関連の名前を指定します。ユーザー マッピングを削除するアプリケーション。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [SSO マッピング](../core/sso-mappings.md)   
 [関連アプリケーションの管理](../core/managing-affiliate-applications.md)   
 [ユーザー マッピングを管理します。](../core/managing-user-mappings.md)