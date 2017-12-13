---
title: "マスター シークレットをバックアップする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [Master Secret server], backing up
- backing up, Master Secret server
- Master Secret server, backing up
ms.assetid: 22c23f66-b7df-4379-8a9f-065406ba8aa8
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 185f3ea674015e02cac2bdaa785c2ee06e67db65
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-back-up-the-master-secret"></a>マスター シークレットをバックアップする方法
マスター シークレットは、マスター シークレット サーバーから NTFS ファイル システムまたはリムーバブル メディア (フロッピー ディスクなど) にバックアップできます。  
  
 この作業を実行するには、シングル サインオン管理者および Windows 管理者である必要があります。 SSO システムによってパスワードの入力を求められます。 バックアップしたマスター シークレットを復元する際は、同じパスワードを指定してください。  
  
> [!CAUTION]
>  マスター シークレット サーバーに障害が発生してキーが失われたり、キーが破損したりすると、SSO データベースに格納されているデータを取得できなくなります。 マスター シークレットは必ずバックアップしてください。そうしないと、SSO データベースのデータが消失する危険性があります。  
  
### <a name="to-back-up-the-master-secret-using-the-mmc-snap-in"></a>MMC スナップインを使用してマスター シークレットをバックアップするには  
  
1.  **開始** メニューのをクリックして**すべてのプログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、クリックして**SSO 管理**です。  
  
2.  ENTSSO MMC スナップインの [スコープ] ウィンドウで、展開、**エンタープライズ シングル サインオン**ノード。  
  
3.  右クリック**システム**、クリックして**シークレットのバックアップ**です。  
  
### <a name="to-back-up-the-master-secret-using-the-command-line"></a>コマンド ラインを使用してマスター シークレットをバックアップするには  
  
1.  **開始** メニューのをクリックして**すべてのプログラム**、クリックして**アクセサリ**です。 右クリック**コマンド プロンプト**、クリックして**として実行しています...**.  
  
2.  適切な管理者の場合を選択し、クリックして**OK**です。  
  
3.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは*\<ドライブ\>*: \program files \common files \enterprise シングル サインオンします。  
  
4.  型**ssoconfig – backupSecret *\<バックアップ ファイル\>***ここで、 *\<バックアップ ファイル\>*の名前とパスにはマスター シークレットがバックアップ先ファイルです。 たとえば、A:\ssobackup.bak と指定します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
5.  パスワードを指定してこのファイルを保護します。 パスワードの確認入力と、このパスワードを思い出すのに役立つパスワードのヒントの指定を求められます。  
  
> [!IMPORTANT]
>  バックアップ ファイルは、セキュリティで保護された場所に保存および格納してください。  
  
## <a name="see-also"></a>参照  
 [マスター シークレットを生成する方法](../core/how-to-generate-the-master-secret.md)   
 [マスター シークレットを復元する方法](../core/how-to-restore-the-master-secret.md)   
 [マスター シークレット サーバー](../core/master-secret-server.md)   
 [マスター シークレットの管理](../core/managing-the-master-secret.md)