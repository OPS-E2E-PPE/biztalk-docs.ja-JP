---
title: マスター シークレットをバックアップする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0841c52a-7b15-45f8-9900-f5c9e3abd90b
caps.latest.revision: 3
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: 124c077d7a15a4938f94239518ad02c8268074a4
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "30250998"
---
# <a name="how-to-back-up-the-master-secret"></a>マスター シークレットをバックアップする方法
マスター シークレットは、マスター シークレット サーバーから NTFS ファイル システムまたはリムーバブル メディア (フロッピー ディスクなど) にバックアップできます。  
  
 このタスクを実行するには、シングル サインオン管理者および Windows 管理者でなければなりません。 シングル サインオン (SSO) システムでは、パスワードを求められます。 バックアップしたマスター シークレットを復元する際は、同じパスワードを指定してください。  
  
> [!CAUTION]
>  マスター シークレット サーバーがクラッシュした場合と、キーを紛失したまたは資格情報データベースに格納されたデータを取得できませんでキーが破損した場合。 マスター シークレットは、または資格情報データベースからデータが失われるリスクをバックアップする必要があります。  
  
### <a name="to-back-up-the-master-secret-using-the-mmc-snap-in"></a>MMC スナップインを使用してマスター シークレットをバックアップするには  
  
1.  をクリックして**開始**、 をポイント**プログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、順にクリック**SSO 管理**です。  
  
2.  ENTSSO Microsoft 管理コンソール (MMC) スナップインの [スコープ] ウィンドウで、展開、**エンタープライズ シングル サインオン**ノード。  
  
3.  右クリック**システム**、クリックして**マスター シークレットをバックアップ**です。  
  
### <a name="to-back-up-the-master-secret-using-the-command-line"></a>コマンド ラインを使用してマスター シークレットをバックアップするには  
  
1.  **開始** メニューのをクリックして**プログラム**、クリックして**アクセサリ**です。 右クリック **コマンド プロンプト**, 、クリックして **実行付けて**します。  
  
2.  適切な管理者を選択し、クリックして **OK**します。  
  
3.  コマンド プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。  
  
     既定のインストール ディレクトリは*\<ドライブ >*: \program files \common files \enterprise シングル サインオンします。  
  
4.  型`ssoconfig –backupsecret <backup file>`ここで、 *\<バックアップ ファイル >* マスター シークレットがバックアップ先、たとえば、ファイルの名前とパスは、`A:\ssobackup.bak`です。  
  
5.  このファイルを保護するためにパスワードを指定します。  
  
     パスワードの確認入力と、このパスワードを思い出すのに役立つパスワードのヒントの指定を求められます。  
  
> [!IMPORTANT]
>  バックアップ ファイルは、セキュリティで保護された場所に保存および格納してください。  
  
## <a name="see-also"></a>参照  
 [マスター シークレットを生成する方法](../esso/how-to-generate-the-master-secret.md)   
 [マスター シークレットを復元する方法](../esso/how-to-restore-the-master-secret.md)   
 [マスター シークレット サーバー](../esso/master-secret-server.md)   
 [マスター シークレットの管理](../esso/managing-the-master-secret.md)