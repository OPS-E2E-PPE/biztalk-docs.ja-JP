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
ms.openlocfilehash: ec9faad19d695d43476e60e87acbd067d7e66896
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008155"
---
# <a name="how-to-back-up-the-master-secret"></a>マスター シークレットをバックアップする方法
マスター シークレットは、マスター シークレット サーバーから NTFS ファイル システムまたはリムーバブル メディア (フロッピー ディスクなど) にバックアップできます。  
  
 この作業を実行するには、シングル サインオン管理者および Windows 管理者である必要があります。 SSO システムによってパスワードの入力を求められます。 バックアップしたマスター シークレットを復元する際は、同じパスワードを指定してください。  
  
> [!CAUTION]
>  マスター シークレット サーバーに障害が発生してキーが失われたり、キーが破損したりすると、SSO データベースに格納されているデータを取得できなくなります。 マスター シークレットは必ずバックアップしてください。そうしないと、SSO データベースのデータが消失する危険性があります。  
  
### <a name="to-back-up-the-master-secret-using-the-mmc-snap-in"></a>MMC スナップインを使用してマスター シークレットをバックアップするには  
  
1.  **開始** メニューのをクリックして**すべてのプログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、 をクリックし、 **SSO 管理**。  
  
2.  ENTSSO MMC スナップインの [スコープ] ウィンドウで、**エンタープライズ シングル サインオン**ノード。  
  
3.  右クリックして**システム**、 をクリックし、**シークレットのバックアップ**します。  
  
### <a name="to-back-up-the-master-secret-using-the-command-line"></a>コマンド ラインを使用してマスター シークレットをバックアップするには  
  
1. **開始** メニューのをクリックして**すべてのプログラム**、順にクリックします**アクセサリ**します。 右クリックして**コマンド プロンプト**、 をクリックし、**として実行しています**。  
  
2. 適切な管理者を選択し、クリックして**OK**します。  
  
3. コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは*\<ドライブ\>*: \Program Files\Common \enterprise シングル サインオンします。  
  
4. 型 * * ssoconfig – backupSecret *\<バックアップ ファイル\>**<em>ここで、*\<バックアップ ファイル\></em>をマスター シークレットをバックアップ、ファイルの名前とパスです。 たとえば、A:\ssobackup.bak と指定します。  
  
   > [!NOTE]
   >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
5. パスワードを指定してこのファイルを保護します。 パスワードの確認入力と、このパスワードを思い出すのに役立つパスワードのヒントの指定を求められます。  
  
> [!IMPORTANT]
>  バックアップ ファイルは、セキュリティで保護された場所に保存および格納してください。  
  
## <a name="see-also"></a>参照  
 [マスター シークレットを生成する方法](../core/how-to-generate-the-master-secret.md)   
 [マスター シークレットを復元する方法](../core/how-to-restore-the-master-secret.md)   
 [マスター シークレット サーバー](../core/master-secret-server.md)   
 [マスター シークレットの管理](../core/managing-the-master-secret.md)