---
title: 関連アプリケーションを削除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications [SSO], deleting
- managing [SSO applications], deleting
- deleting, applications [SSO]
ms.assetid: c7ec065e-ef10-49ff-a350-105dd08dc4a9
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b24dc6a17f6bbe30af7354b88be822cf7dcb7c08
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338624"
---
# <a name="how-to-delete-an-affiliate-application"></a>関連アプリケーションを削除する方法
MMC スナップインまたはコマンドラインを使用すると、指定された関連アプリケーションを SSO データベースから削除します。  
  
> [!IMPORTANT]
>  関連アプリケーションを削除すると、SSO システムは自動的に関連付けられているすべてのマッピングを削除します。  
  
> [!IMPORTANT]
>  この作業を実行するには、SSO 管理者または SSO 関連管理者である必要があります。  
  
### <a name="to-delete-an-affiliate-application-using-the-mmc-snap-in"></a>MMC スナップインを使用して関連アプリケーションを削除するには  
  
1.  **開始** メニューのをクリックして**プログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、 をクリックし、 **SSO 管理**。  
  
2.  MMC スナップインの [スコープ] ウィンドウで、**エンタープライズ シングル サインオン**ノード。  
  
3.  関連アプリケーションを右クリックし、をクリックし、**削除**します。  
  
### <a name="to-delete-an-affiliate-application-using-the-command-line"></a>コマンドラインを使用して関連アプリケーションを削除するには  
  
1. **開始** メニューのをクリックして**実行**、し、入力**cmd**します。  
  
2. コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは *\<ドライブ\>* : \Program Files\Common \enterprise シングル サインオンします。  
  
3. 型 * * ssomanage – deleteapp *\<アプリケーション名\>**<em>ここで、*\<アプリケーション名\></em>から削除する関連アプリケーションの名前を指定しますSSO データベース。  
  
   > [!NOTE]
   >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [SSO 関連アプリケーション](../core/sso-affiliate-applications.md)   
 [関連アプリケーションを有効にする方法](../core/how-to-enable-an-affiliate-application.md)   
 [ユーザー マッピングの管理](../core/managing-user-mappings.md)   
 [関連アプリケーションの管理](../core/managing-affiliate-applications.md)