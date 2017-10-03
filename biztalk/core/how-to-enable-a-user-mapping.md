---
title: "ユーザー マッピングを有効にする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- enabling, user maps [SSO]
- maps [SSO], enabling
- managing [SSO maps], enabling
ms.assetid: 0f6448c9-944e-45f6-9436-87a4f3743498
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af4679d277a12335f8a9776695cd829473df460d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-enable-a-user-mapping"></a>ユーザー マッピングを有効にする方法
シングル サインオン システムでマッピングを使用するには、ユーザー マッピングを有効にする必要があります。  
  
 ユーザー マッピングを有効にする場合は (E) として表示されます**\<ドメイン >\\< ユーザー名\>**ユーザー マッピングを一覧表示します。  
  
 -setcredentials コマンドを使用して資格情報を設定した場合、マッピングは既に有効になっています。  
  
### <a name="to-enable-a-user-mapping-using-the-administration-utility"></a>管理ユーティリティを使用してユーザー マッピングを有効にするには  
  
1.  **開始** メニューのをクリックして**実行**、し、入力**cmd**です。  
  
2.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは**\<ドライブ >**: \program files \common files \enterprise シングル サインオンします。  
  
3.  型**ssomanage – enablemapping\<ドメイン >\\< ユーザー名\>\<アプリケーション名 >**ここで、 **\<ドメイン >**はWindows ドメイン ユーザー アカウントを**\<ユーザー名 >**は、資格情報を有効にする Windows ユーザー名と**\<アプリケーション名 >**ユーザー マッピングを削除し、ENTER キーを押してする関連アプリケーションの名前を指定します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
### <a name="to-enable-a-user-mapping-using-the-client-utility"></a>クライアント ユーティリティを使用してユーザー マッピングを有効にするには  
  
1.  **開始** メニューのをクリックして**実行**、し、入力**cmd**です。  
  
2.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは**\<ドライブ >**: \program files \common files \enterprise シングル サインオンします。  
  
3.  型**ssoclient – enablemapping\<アプリケーション名 >**ここで、 **\<アプリケーション名 >**ユーザー マッピングを削除する関連アプリケーションの名前を指定します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [ユーザー マッピングを作成する方法](../core/how-to-create-user-mappings.md)   
 [SSO マッピング](../core/sso-mappings.md)   
 [関連アプリケーションの管理](../core/managing-affiliate-applications.md)   
 [ユーザー マッピングを管理します。](../core/managing-user-mappings.md)