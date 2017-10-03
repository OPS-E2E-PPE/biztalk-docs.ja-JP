---
title: "関連アプリケーションを削除する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applications [SSO], deleting
- managing [SSO applications], deleting
- deleting, applications [SSO]
ms.assetid: c7ec065e-ef10-49ff-a350-105dd08dc4a9
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ddb40109ff402f1c1794a90e591a43e11407fba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-delete-an-affiliate-application"></a>関連アプリケーションを削除する方法
MMC スナップインまたはコマンド ラインを使用して、指定した関連アプリケーションを SSO データベースから削除することができます。  
  
> [!IMPORTANT]
>  関連アプリケーションを削除すると、そのアプリケーションに関連付けられたすべてのマッピングが自動的に削除されます。  
  
> [!IMPORTANT]
>  この作業を実行するには、SSO 管理者または SSO 関連管理者である必要があります。  
  
### <a name="to-delete-an-affiliate-application-using-the-mmc-snap-in"></a>MMC スナップインを使用して関連アプリケーションを削除するには  
  
1.  **開始** メニューのをクリックして**プログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、クリックして**SSO 管理**です。  
  
2.  MMC スナップインの [スコープ] ウィンドウで、展開、**エンタープライズ シングル サインオン**ノード。  
  
3.  関連アプリケーションを右クリックし、をクリックして**削除**です。  
  
### <a name="to-delete-an-affiliate-application-using-the-command-line"></a>コマンド ラインを使用して関連アプリケーションを削除するには  
  
1.  **開始** メニューのをクリックして**実行**、し、入力**cmd**です。  
  
2.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは*\<ドライブ >*: \program files \common files \enterprise シングル サインオンします。  
  
3.  型**ssomanage – deleteapp *\<アプリケーション名 >***ここで、 *\<アプリケーション名 >*関連アプリケーションの名前を指定します。SSO データベースから削除します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [SSO 関連アプリケーション](../core/sso-affiliate-applications.md)   
 [関連アプリケーションを有効にする方法](../core/how-to-enable-an-affiliate-application.md)   
 [ユーザー マッピングを管理します。](../core/managing-user-mappings.md)   
 [関連アプリケーションの管理](../core/managing-affiliate-applications.md)