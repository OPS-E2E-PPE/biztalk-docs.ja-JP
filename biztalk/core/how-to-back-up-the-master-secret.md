---
title: マスター シークレットをバックアップする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [Master Secret server], backing up
- backing up, Master Secret server
- Master Secret server, backing up
ms.assetid: 22c23f66-b7df-4379-8a9f-065406ba8aa8
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1e38ebeb861d26bfdb31819ea1d94d830bf58fe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387092"
---
# <a name="how-to-back-up-the-master-secret"></a>マスター シークレットをバックアップする方法
ことができます、NTFS にマスター シークレット サーバーからマスター シークレットをバックアップするファイル システムまたはフロッピー ディスクなどのリムーバブル メディア。  
  
 シングル サインオン管理者および Windows 管理者は、このタスクを実行する必要があります。 SSO システムでは、パスワードを求められます。 後で、シークレットを復元するには、同じパスワードを指定する必要があります。  
  
> [!CAUTION]
>  マスター シークレット サーバーが失敗し、キーを紛失した場合、または、キーが破損している場合は、SSO データベースに格納されているデータを取得することができなきます。 マスター シークレットは、または SSO データベースからデータが失われるリスクをバックアップする必要があります。  
  
### <a name="to-back-up-the-master-secret-using-the-mmc-snap-in"></a>MMC スナップインを使用してマスター シークレットをバックアップするには  
  
1.  **開始** メニューのをクリックして**すべてのプログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、 をクリックし、 **SSO 管理**。  
  
2.  ENTSSO MMC スナップインの [スコープ] ウィンドウで、**エンタープライズ シングル サインオン**ノード。  
  
3.  右クリックして**システム**、 をクリックし、**シークレットのバックアップ**します。  
  
### <a name="to-back-up-the-master-secret-using-the-command-line"></a>コマンドラインを使用してマスター シークレットをバックアップするには  
  
1. **開始** メニューのをクリックして**すべてのプログラム**、順にクリックします**アクセサリ**します。 右クリックして**コマンド プロンプト**、 をクリックし、**として実行しています**。  
  
2. 適切な管理者を選択し、クリックして**OK**します。  
  
3. コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは*\<ドライブ\>*: \Program Files\Common \enterprise シングル サインオンします。  
  
4. 型 * * ssoconfig – backupSecret *\<バックアップ ファイル\>**<em>ここで、*\<バックアップ ファイル\></em>をマスター シークレットをバックアップ、ファイルの名前とパスです。 たとえば、A:\ssobackup.bak  
  
   > [!NOTE]
   >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
5. このファイルを保護するパスワードを提供します。 このパスワードを思い出すのに役立つパスワードのヒントを提供して、パスワードの確認を求められます。  
  
> [!IMPORTANT]
>  保存し、安全な場所にバックアップ ファイルを保存する必要があります。  
  
## <a name="see-also"></a>参照  
 [マスター シークレットを生成する方法](../core/how-to-generate-the-master-secret.md)   
 [マスター シークレットを復元する方法](../core/how-to-restore-the-master-secret.md)   
 [マスター シークレット サーバー](../core/master-secret-server.md)   
 [マスター シークレットの管理](../core/managing-the-master-secret.md)