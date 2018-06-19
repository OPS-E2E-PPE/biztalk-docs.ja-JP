---
title: ユーザー マッピングを有効にする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- enabling, user maps [SSO]
- maps [SSO], enabling
- managing [SSO maps], enabling
ms.assetid: 0f6448c9-944e-45f6-9436-87a4f3743498
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dfd87d300314616fe05a033360d84f5d2eb8b8cd
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970832"
---
# <a name="how-to-enable-a-user-mapping"></a>ユーザー マッピングを有効にする方法
シングル サインオン システムでマッピングを使用するには、ユーザー マッピングを有効にする必要があります。  
  
 ユーザー マッピングを有効にする場合は (E) として表示されます**\<ドメイン\>\\< ユーザー名\>** ユーザー マッピングを一覧表示します。  
  
 -setcredentials コマンドを使用して資格情報を設定した場合、マッピングは既に有効になっています。  
  
### <a name="to-enable-a-user-mapping-using-the-administration-utility"></a>管理ユーティリティを使用してユーザー マッピングを有効にするには  
  
1.  **開始** メニューのをクリックして**実行**、し、入力**cmd**です。  
  
2.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは**\<ドライブ\>**: \program files \common files \enterprise シングル サインオンします。  
  
3.  型**ssomanage – enablemapping\<ドメイン\>\\< ユーザー名\>\<アプリケーション名\>** ここで、  **\<ドメイン\>** は Windows ドメイン ユーザー アカウントを **\<username\>** 資格情報、およびを有効にするWindowsユーザー名は、**\<アプリケーション名\>** ユーザー マッピングを削除し、ENTER キーを押してする関連アプリケーションの名前を指定します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
### <a name="to-enable-a-user-mapping-using-the-client-utility"></a>クライアント ユーティリティを使用してユーザー マッピングを有効にするには  
  
1.  **開始** メニューのをクリックして**実行**、し、入力**cmd**です。  
  
2.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは**\<ドライブ\>**: \program files \common files \enterprise シングル サインオンします。  
  
3.  型**ssoclient – enablemapping\<アプリケーション名\>** ここで、 **\<アプリケーション名\>** する関連アプリケーションの名前を指定します。ユーザー マッピングを削除します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [ユーザー マッピングを作成する方法](../core/how-to-create-user-mappings.md)   
 [SSO マッピング](../core/sso-mappings.md)   
 [関連アプリケーションの管理](../core/managing-affiliate-applications.md)   
 [ユーザー マッピングの管理](../core/managing-user-mappings.md)