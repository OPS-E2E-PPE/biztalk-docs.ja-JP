---
title: ユーザー マッピングを有効にする方法 |Microsoft Docs
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
ms.openlocfilehash: 917f3eb2d1438bb53b9a8a583e3985b0843f09b4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385141"
---
# <a name="how-to-enable-a-user-mapping"></a>ユーザー マッピングを有効にする方法
ユーザーを有効にする必要がありますでシングル サインオン システムでマッピングを使用する前にマッピングすることができます。  
  
 ユーザー マッピングを有効にすると (E) として表示されます **\<ドメイン\>\\< ユーザー名\>** ユーザー マッピングの一覧を表示する場合。  
  
 -Setcredentials コマンドを使用して資格情報を設定した場合、マッピングは既に有効にするに注意してください。  
  
### <a name="to-enable-a-user-mapping-using-the-administration-utility"></a>管理ユーティリティを使用してユーザー マッピングを有効にするには  
  
1.  **開始** メニューのをクリックして**実行**、し、入力**cmd**します。  
  
2.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは **\<ドライブ\>** : \Program Files\Common \enterprise シングル サインオンします。  
  
3.  型**ssomanage – enablemapping\<ドメイン\>\\< ユーザー名\>\<アプリケーション名\>** ここで、  **\<ドメイン\>** が Windows ドメイン ユーザー アカウントの **\<username\>** 資格情報、およびを有効にするWindowsユーザー名は、 **\<アプリケーション名\>** ユーザー マッピングを削除し、enter する関連アプリケーションの名前を指定します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
### <a name="to-enable-a-user-mapping-using-the-client-utility"></a>クライアント ユーティリティを使用してユーザー マッピングを有効にするには  
  
1.  **開始** メニューのをクリックして**実行**、し、入力**cmd**します。  
  
2.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは **\<ドライブ\>** : \Program Files\Common \enterprise シングル サインオンします。  
  
3.  型**ssoclient – enablemapping\<アプリケーション名\>** ここで、 **\<アプリケーション名\>** する関連アプリケーションの名前を指定しますユーザー マッピングを削除します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [ユーザー マッピングを作成する方法](../core/how-to-create-user-mappings.md)   
 [SSO マッピング](../core/sso-mappings.md)   
 [関連アプリケーションの管理](../core/managing-affiliate-applications.md)   
 [ユーザー マッピングの管理](../core/managing-user-mappings.md)